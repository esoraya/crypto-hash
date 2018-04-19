# crypto-hash
!!!NOTES!!!
Basic Key information
http://www.coinwarz.com/v1/api/apikeyinfo?apikey=YOUR_API_KEY
  'API Key Objects
    ApiKey
    AccessLevel
    DailyUsageAvailable
  
  
'Key Profitability 
http://www.coinwarz.com/v1/api/profitability/?apikey=YOUR_API_KEY&algo=all
  'API Profitability objects  
  ethashHashRate
  equihashHashRate
  scryptHashRate
  x11HashRate
  blake256HashRate
  neoscryptHashRate


import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.PrintStream;
import java.net.URL;
import java.net.URLConnection;

public class Rest {

    public static void main(String[] args) throws IOException {
        URL url = new URL(http://www.coinwarz.com/v1/api/apikeyinfo?apikey=);
        String query = DailyUsageAvailable,1;

        //make connection
        URLConnection urlc = url.openConnection();

        //use post mode
        urlc.setDoOutput(true);
        urlc.setAllowUserInteraction(false);

        //send query
        PrintStream ps = new PrintStream(urlc.getOutputStream());
        ps.print(query);
        ps.close();

        //get result
        BufferedReader br = new BufferedReader(new InputStreamReader(urlc
            .getInputStream()));
        String l = null;
        while ((l=br.readLine())!=null) {
            System.out.println(l);
        }
        br.close();
    }
}
