```java
import java.io.IOException;
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
public class SendRequest2
{
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Get All Orders (GET )

    try {

      // Create request
      URL obj = new URL("https://api.mwwondemand.com/api/orders/705517149988324623");
      HttpURLConnection con = (HttpURLConnection) obj.openConnection();

      con.setRequestMethod("GET");


      // Add headers
      con.setRequestProperty("Accept", "application/vnd.api+json; version=1");
      con.setRequestProperty("Authorization", "auth-key=S@mpl3!");
      con.setRequestProperty("Content-Type", "application/vnd.api+json");

      // Get response code (200 is good)
      int responseCode = con.getResponseCode();
      System.out.println("Response Code : " + responseCode);


      BufferedReader in = new BufferedReader(
		        new InputStreamReader(con.getInputStream()));
      String inLine;
      StringBuffer response = new StringBuffer();

      while ((inLine = in.readLine()) != null) {
	        response.append(inLine);
      }
      in.close();

      //print result
      System.out.println(response.toString());

   }
    catch (IOException e) { System.out.println(e); }
  }
}
```
