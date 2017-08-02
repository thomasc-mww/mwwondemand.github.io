```java
import java.io.IOException;
import org.apache.http.client.fluent.*;

public class SendRequest
{
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Get Line Items By Order (GET )

    try {

      // Create request
      Content content = Request.Get("https://api.mwwondemand.com/api/orders/647372455787562562/line-items")

      // Add headers
      .addHeader("Authorization", "auth-key=YOUR_API_KEY")
      .addHeader("Accept", "application/vnd.api+json; version=1")

      // Fetch request and return content
      .execute().returnContent();

      // Print content
      System.out.println(content);
    }
    catch (IOException e) { System.out.println(e); }
  }
}
```
