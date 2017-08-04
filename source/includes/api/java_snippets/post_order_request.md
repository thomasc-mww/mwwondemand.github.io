```java
import java.io.IOException;
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.DataOutputStream;


public class post_request
{
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


      // Add headers
      con.setRequestProperty("Accept", "application/vnd.api+json; version=1");
      con.setRequestProperty("Authorization", "auth-key=YOUR_API_KEY");
      con.setRequestProperty("Content-Type", "application/vnd.api+json");


      // Add body
      String urlParams = "{" +
        "'data': {" +
            "'type': 'orders'," +
            "'attributes': {" +
              "'vendor-po': '146798810923'," +
              "'shipping-method': 'SAMPLE'," +
              "'shipping-account-number': '1234'" +
            "}" +
          "}," +
          "'included': [" +
            "{" +
              "'type': 'shipping-address'," +
              "'attributes': { " +
              "'name': 'Phillip J. Fry', " +
              "'address: '123 Green St.\nSuite 321'," +
                "'city': 'New New York', " +
                "'state': 'NY'," +
                "'postal-code': '10012'" +
              "}" +
            "}," +
            "{" +
              "'type': 'billing-address'," +
              "'attributes': {" +
              "'name': 'Hubert Farnsworth'," +
              "'address': '123 Green St.\nSuite 321'," +
                "'city': 'New New York'," +
                "'state': 'NY'," +
                "'postal-code': '10012'" +
              "}" +
            "}," +
            "{" +
              "'type': 'return-address'," +
              "'attributes': { " +
              "'name': 'Bender B. Rodriguez'," +
              "'address': '123 Green St.\nSuite 321',"  +
                "'city': 'New New York', " +
                "'state': 'NY'," +
                "'postal-code': '10012' " +
              "}" +
            "}," +
            "{" +
              "'type': 'line-items', " +
              "'attributes': { " +
                "'line-number': 1, " +
                "'quantity': 2, "  +
                "'description': 'It\'s not so fluffy!', " +
                "'product-code': '3PF-SC6-SPFPI', " +
                "'customer-product-code': 'YOUR_UPC/SKU_NUMBER', " +
                "'item-properties': { " +
                  "'thread-color': 'white'" +
                "}," +
                "'designs': [" +
                  "{" +
                    "'image-remote-url': 'http://images.apple.com/v/home/cj/images/promos/ipad_pro_large.jpg'" +
                  "}" +
                "]" +
              "}" +
            "}," +
            "{" +
              "'type': 'line-items', " +
              "'attributes': { " +
                "'line-number': 2, " +
                "'quantity': 5, " +
                "'description': 'Velour Vest', "+
                "'product-code': '3PF-SC6-SPFPI'," +
                "'customer-product-code': 'YOUR_UPC/SKU_NUMBER', " +
                "'item-properties': { " +
                  "'thread-color': 'white'" +
                "}," +
                "'designs': ["  +
                  "{" +
                    "'image-remote-url': 'http://images.apple.com/v/home/cj/images/heros/iphone-6s-change_xlarge.jpg'" +
                  "}" +
                "]" +
              "}" +
            "}," +
            "{" +
              "'type': 'packing-list', " +
              "'attributes': { " +
                "'url': 'http://www.akapparel.com/assets/production-pdf/110-160511-050-2.pdf' " +
               "}" +
              "}," +
              "{" +
              "'type': 'shipping-label'," +
              "'attributes': { " +
               "'url': 'https://hellofabric.com/assets/mww/orders/86667297/56d712af0897d-86667297-MWWA1411.png'" +
              "}" +
            "}" +
          "]"+
        "};";
       con.setDoOutput(true);
       DataOutputStream wr = new DataOutputStream(con.getOutputStream());
		   wr.writeBytes(urlParams);
		   wr.flush();
		   wr.close();
       int responseCode = con.getResponseCode();
       System.out.println("Response Code : " + responseCode);

       BufferedReader in = new BufferedReader(
       		        new InputStreamReader(con.getInputStream()));
       		String inputLine;
       		StringBuffer response = new StringBuffer();

       		while ((inputLine = in.readLine()) != null) {
       			response.append(inputLine);
       		}
       		in.close();

       		//print result
       		System.out.println(response.toString());
    }
    catch (IOException e) { System.out.println(e); }
  }
}

```
