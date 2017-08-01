```java
import java.io.IOException;
import org.apache.http.client.fluent.*;

public class SendRequest
{
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Get Order (GET )

    try {

      // Create request
      Content content = Request.Get("http://localhost:3000/api/orders/572425086284334684")

      // Add headers
      .addHeader("Content-Type", "application/vnd.api+json")
      .addHeader("Authorization", "auth-key=YOUR_API_KEY")
      .addHeader("Accept", "application/vnd.api+json;version=1")

      // Fetch request and return content
      .execute().returnContent();

      // Print content
      System.out.println(content);
    }
    catch (IOException e) { System.out.println(e); }
  }
}
```
