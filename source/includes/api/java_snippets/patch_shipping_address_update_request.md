```java
import java.io.IOException;
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.DataOutputStream;


public class SubmitOrder {
    public static void main(String[] args) {
        sendRequest();
    }

    private static void sendRequest() {
        // Update Shipping Address (PATCH)

        try {
            // Create request
            URL obj = new URL("https://api.mwwondemand.com/api/shipping-addresses/1674068325472142392");
            HttpURLConnection con = (HttpURLConnection) obj.openConnection();


            con.setRequestMethod("PATCH");

            // // Add headers
            con.setRequestProperty("Accept", "application/vnd.api+json; version=1");
            con.setRequestProperty("Authorization", "auth-key=YOUR_API_KEY");
            con.setRequestProperty("Content-Type", "application/vnd.api+json");

            // Add body
            String urlParams = "{"+
              "\"data\": {"+
                "\"type\": \"shipping-addresses\","+
                  "\"attributes\":"+
                  "{"+
                    "\"name\": \"Test User\","+
                    "\"address1\": \"5757 Howard Gap Rd.\","+
                    "\"address2\": \"\","+
                    "\"city\": \"Hendersonville","+
                    "\"state\": \"NV\","+
                    "\"country\": \"US\","+
                    "\"postal-code\": \"28792\","+
                    "\"email\": \"user@mwwondemand.com\","+
                    "\"phone\": \"555-555-5555\""+
                  "}"+
                "},"+
            "}";


            System.out.println(urlParams);

            con.setDoOutput(true);

            DataOutputStream wr = new DataOutputStream(con.getOutputStream());
            wr.write(urlParams.getBytes("UTF-8"));
            wr.flush();
            wr.close();

            int responseCode = con.getResponseCode();
            System.out.println("Response Code : " + responseCode);
            System.out.println("POST Response Message : " + con.getResponseMessage());

            BufferedReader in = new BufferedReader(
                new InputStreamReader(con.getInputStream(), "UTF-8"));
            String inputLine;
            StringBuffer response = new StringBuffer();

            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();

            //print result
            System.out.println(response.toString());
        } catch (IOException e) {
            System.out.println(e);
        }
    }
}

```
