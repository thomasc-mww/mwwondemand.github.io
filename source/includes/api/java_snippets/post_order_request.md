```java
import java.io.IOException;
import org.apache.http.client.fluent.*;
import org.apache.http.entity.ContentType;

public class SendRequest
{
  public static void main(String[] args) {
    sendRequest();
  }

  private static void sendRequest() {

    // Create Order (POST )

    try {

      // Create request
      Content content = Request.Post("http://localhost:3000/api/orders")

      // Add headers
      .addHeader("Content-Type", "application/vnd.api+json")
      .addHeader("Authorization", "auth-key=S@mpl3!")
      .addHeader("Accept", "application/vnd.api+json; version=1")

      // Add body
      .bodyString("{ \n \\ndata\\n: {
                      \n    \\ntype\\n: \\norders\\n,\n    
                            \\nattributes\\n: {\n      
                                      \\nvendor-po\\n: \\n1480697772\\n,\n      \\nshipping-method\\n: \\nSAMPLE\\n,\n      \\nshipping-account-number\\n: \\n1234\\n\n  
                                }\n
                            },\n  
                            \\nincluded\\n: [\n    {\n      
                                      \\ntype\\n:   \\nshipping-address\\n,\n      \\nattributes\\n: {\n	
                                          \\nname\\n: \\nPhillip J. Fry\\n,\n     	\\naddress\\n: \\n123 Green St.\\nSuite 321\\n,\n      	\\ncity\\n: \\nNew New York\\n,\n
                                          \\nstate\\n: \\nNY\\n,\n
                                          \\npostal-code\\n: \\n10012\\n\n      
                                      }\n    
                                },\n    
                                {\n      
                                  \\ntype\\n: \\nbilling-address\\n,\n      
                                  \\nattributes\\n: {\n	
                                      \\nname\\n: \\nHubert Farnsworth\\n,\n       	\\naddress\\n: \\n123 Green St.\\nSuite 321\\n,\n      	\\ncity\\n: \\nNew New York\\n,\n             	\\nstate\\n: \\nNY\\n,\n                 	\\npostal-code\\n: \\n10012\\n\n                       }\n   
                                  },\n    
                                  {\n      
                                    \\ntype\\n: \\nreturn-address\\n,\n  
                                    \\nattributes\\n: {\n	
                                        \\nname\\n: \\nBender B. Rodriguez\\n,\n     	\\naddress\\n: \\n123 Green St.\\nSuite 321\\n,\n      	\\ncity\\n: \\nNew New York\\n,\n      	
                                        \\nstate\\n: \\nNY\\n,\n      	
                                        \\npostal-code\\n: \\n10012\\n\n      
                                      }\n
                                   },\n    
                                   {\n     
                                     \\ntype\\n: \\nline-items\\n,\n   
                                      \\nattributes\\n: {\n
                                              \\nline-number\\n: 1,\n        
                                              \\nquantity\\n: 2,\n        
                                              \\ndescription\\n: \\nIt's not so fluffy!\\n,\n        
                                              \\nproduct-code\\n: \\n3PF-PSY-SQPGZ2C\\n,\n        \\nitem-properties\\n:  
                                              {\n 
                                                  \\nthread-color\\n: \\nwhite\\n,\n
                                                  \\nblah\\n: 
                                                  \\nblah-2\\n\n        
                                              },\n      
                                              \\ndesigns\\n: [\n         
                                                 {\n            
                                                  \\nimage_remote_url\\n: \\nhttp://images.apple.com/v/home/cj/images/promos/ipad_pro_large.jpg\\n,\n            \\nposition\\n: \\ncentered\\n,\n            \\ncrop\\n: \\nleft\\n\n          }\n        ]\n      }\n    },\n    {\n      \\ntype\\n: \\nline-items\\n,\n      \\nattributes\\n: {\n        \\nline-number\\n: 2,\n        \\nquantity\\n: 5,\n        \\ndescription\\n: \\nIt's sò fluffy!\\n,\n        \\nproduct-code\\n: \\n3PF-PJT-SLPG4CW\\n,\n        \\nitem-properties\\n: {\n          \\nthread-color\\n: \\nwhite\\n,\n          \\nblah\\n: \\nblah-2\\n\n        },\n        \\ndesigns\\n: [\n          {\n            \\nimage_remote_url\\n: \\nhttp://images.apple.com/v/home/cj/images/heros/iphone-6s-change_xlarge.jpg\\n\n          }\n        ]\n      }\n    },\n    {	\n      \\ntype\\n: \\npacking-list\\n,\n       \\nattributes\\n: {\n	\\nurl\\n: \\nhttp://www.akapparel.com/assets/production-pdf/110-160511-050-2.pdf\\n\n       }\n      },\n      { \n         \\ntype\\n: \\nshipping-label\\n,\n   	  \\nattributes\\n: {\n	     \\nurl\\n: \\nhttps://hellofabric.com/assets/mww/orders/86667297/56d712af0897d-86667297-MWWA1411.png\\n\n	  }\n	\n      }\n  ]\n}", ContentType.DEFAULT_TEXT)

      // Fetch request and return content
      .execute().returnContent();

      // Print content
      System.out.println(content);
    }
    catch (IOException e) { System.out.println(e); }
  }
}
```
