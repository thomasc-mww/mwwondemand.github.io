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
        // Create Order (POST )

        try {
            // Create request
            URL obj = new URL("https://api.mwwondemand.com/api/orders");
            HttpURLConnection con = (HttpURLConnection) obj.openConnection();


            con.setRequestMethod("POST");

            // // Add headers
            con.setRequestProperty("Accept", "application/vnd.api+json; version=1");
            con.setRequestProperty("Authorization", "auth-key=YOUR_API_KEY");
            con.setRequestProperty("Content-Type", "application/vnd.api+json");

            // Add body
            String urlParams = "{"+
              "\"data\": {"+
                "\"type\": \"orders\","+
                "\"attributes\":"+
                "{"+
                  "\"vendor-po\": \"146798810923\","+
                  "\"shipping-method\": \"SAMPLE\","+
                  "\"shipping-account-number\": \"1234\","+
                  "\"test-order\": \"test\""+
                "}"+
              "},"+
              "\"included\": [{"+
                  "\"type\": \"shipping-address\","+
                  "\"attributes\":"+
                  "{"+
                    "\"name\": \"Phillip J. Fry\","+
                    "\"address1\": \"123 Green St.\","+
                    "\"address2\": \"Suite 321\","+
                    "\"city\": \"New New York\","+
                    "\"state\": \"NY\","+
                    "\"country\": \"US\","+
                    "\"postal-code\": \"10012\","+
                    "\"email\": \"bob@dobalina.net\","+
                    "\"phone\": \"8288888888\""+
                  "}"+
                "},"+
                "{"+
                  "\"type\": \"billing-address\","+
                  "\"attributes\":"+
                  "{"+
                    "\"name\": \"Hubert Farnsworth\","+
                    "\"address1\": \"123 Green St.\","+
                    "\"address2\": \"Suite 321\","+
                    "\"city\": \"New New York\","+
                    "\"state\": \"NY\","+
                    "\"country\": \"US\","+
                    "\"postal-code\": \"10012\","+
                    "\"email\": \"bob@dobalina.net\","+
                    "\"phone\": \"8288888888\""+
                  "}"+
                "},"+
                "{"+
                  "\"type\": \"line-items\","+
                  "\"attributes\": {"+
                    "\"line-number\": 1,"+
                    "\"quantity\": 2,"+
                    "\"description\": \"It's not sò fluffy!\","+
                    "\"product-code\": \"PRT-GEN-SLG16S\","+
                    "\"customer-product-code\": \"YOUR_UPC/SKU_NUMBER\","+
                    "\"item-properties\":"+
                    "{"+
                      "\"thread-color\": \"white\","+
                      "\"hs-code\": \"1234.56.789\""+
                    "},"+
                    "\"designs\": ["+
                      "{"+
                        "\"image-remote-url\": \"https://static.pexels.com/photos/39803/pexels-photo-39803.jpeg\""+
                      "}"+
                    "]"+
                  "}"+
                "},"+
                "{"+
                  "\"type\": \"line-items\","+
                  "\"attributes\": {"+
                    "\"line-number\": 2,"+
                    "\"quantity\": 5,"+
                    "\"description\": \"Velour Vest\","+
                    "\"product-code\": \"PRT-GEN-SLPGP8\","+
                    "\"customer-product-code\": \"YOUR_UPC/SKU_NUMBER\","+
                    "\"item-properties\":"+
                    "{"+
                      "\"thread-color\": \"white\""+
                    "},"+
                    "\"designs\": ["+
                      "{"+
                        "\"image-remote-url\": \"http://www.publicdomainpictures.net/pictures/10000/velka/orange-871282749123hSB3.jpg\""+
                      "}"+
                    "]"+
                  "}"+
                "},"+
                "{"+
                  "\"type\": \"packing-list\","+
                  "\"attributes\":"+
                  "{"+
                    "\"url\": \"https://dllc.appstate.edu/sites/dllc.appstate.edu/files/SearchCCimages.pdf\""+
                  "}"+
                "},"+
                "{"+
                  "\"type\": \"shipping-label\","+
                  "\"attributes\":"+
                  "{"+
                    "\"url\": \"https://upload.wikimedia.org/wikipedia/commons/0/04/Einschreiben-Label_Deutsche_Post_2011.jpg\""+
                  "}"+
                "}"+
              "]"+
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
