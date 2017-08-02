```java
import java.io.IOException;
import org.apache.http.client.fluent.*;

public class SendRequest
{
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Get All Orders (GET )

    try {

      // Create request
      Content content = Request.Get("https://api.mwwondemand.com/api/orders")

      // Add headers
      .addHeader("Accept", "application/vnd.api+json; version=1")
      .addHeader("Authorization", "auth-key=S@mpl3!")
      .addHeader("Content-Type", "application/vnd.api+json")

      // Fetch request and return content
      .execute().returnContent();

      // Print content
      System.out.println(content);
    }
    catch (IOException e) { System.out.println(e); }
  }
}
```
