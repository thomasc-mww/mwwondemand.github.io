```java
import java.io.IOException;
import org.apache.http.client.fluent.*;

public class SendRequest {
  
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Get Validate token (GET )

    try {

      // Create request
      Content content = Request.Get("https://api.mwwondemand.com/api/validate_token")

      // Add headers
      .addHeader("Content-Type", "application/vnd.api+json")
      .addHeader("Authorization", "application/vnd.api+json; version=1")
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
