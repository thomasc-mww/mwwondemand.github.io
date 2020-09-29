```java
import java.io.IOException;
import org.apache.http.client.fluent.*;

public class SendRequest {
  
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Delete Webhook (DELETE )

    try {

      // Create request
      Content content = Request.Delete("https://api.mwwondemand.com/api/webhooks/")

      // Add headers
      .addHeader("Content-Type", "application/vnd.api+json")
      .addHeader("Authorization", "<BEARER_TOKEN>")
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
