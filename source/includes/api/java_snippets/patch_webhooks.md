```java
import java.io.IOException;
import org.apache.http.client.fluent.*;
import org.apache.http.entity.ContentType;

public class SendRequest {
  
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Patch Webhook (PATCH )

    try {

      // Create request
      Content content = Request.Patch("https://api.mwwondemand.com/api/webhooks/")

      // Add headers
      .addHeader("Content-Type", "application/vnd.api+json")
      .addHeader("Authorization", "<BEARER_TOKEN>")
      .addHeader("Accept", "application/vnd.api+json; version=1")

      // Add body
      .bodyString("{\n  \\ndata\\n: {\n    \\nid\\n: \\n\\n,\n    \\ntype\\n: \\nwebhooks\\n,\n    \\nattributes\\n: {\n      \\nurl\\n: \\nhttp://localhost:3001/mwwondemand-order-notifications\\n,\n      \\nprinted\\n: true,\n      \\npressed\\n: true,\n      \\ncut\\n: true,\n      \\nsewn\\n: true,\n      \\nturned\\n: true,\n      \\npacked\\n: true\n    }\n  }\n}", ContentType.DEFAULT_TEXT)

      // Fetch request and return content
      .execute().returnContent();

      // Print content
      System.out.println(content);
    }
    catch (IOException e) { System.out.println(e); }
  }
}
```
