```java
import java.io.IOException;
import org.apache.http.client.fluent.*;
import org.apache.http.entity.ContentType;

public class SendRequest {
  
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Create Webhook (POST )

    try {

      // Create request
      Content content = Request.Post("https://api.mwwondemand.com/api/webhooks")

      // Add headers
      .addHeader("Content-Type", "application/vnd.api+json")
      .addHeader("Authorization", "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo2NDgzODcyODM1Njg4MjE1MjYsImV4cCI6MTQ4MDUxNzcyOX0.SijY04z68CwqQ6AV2N3cWSng6fQAl06zodWicym_uuY")
      .addHeader("Accept", "application/vnd.api+json;version=1")

      // Add body
      .bodyString("{\n  \\ndata\\n: {\n    \\ntype\\n: \\nwebhooks\\n,\n    \\nattributes\\n: {\n      \\nurl\\n: \\nhttp://test\\n\n    }\n  }\n}", ContentType.DEFAULT_TEXT)

      // Fetch request and return content
      .execute().returnContent();

      // Print content
      System.out.println(content);
    }
    catch (IOException e) { System.out.println(e); }
  }
}
```
