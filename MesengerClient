import java.net.*;
import java.io.*;
import java.util.*;
public class MesengerClient
{
   static Socket s; 
  public static void main(String[] args) throws Exception
  {
      Scanner in = new Scanner(System.in);
      System.out.print("Enter the Client IP :");
      String inpip=in.nextLine();
      s = new Socket(inpip, 5001); 
     BufferedReader kr = new BufferedReader(new InputStreamReader(System.in));
     OutputStream os = s.getOutputStream(); 
     PrintWriter pw = new PrintWriter(os, true);
     InputStream is = s.getInputStream();
     BufferedReader rr = new BufferedReader(new InputStreamReader(is));
     System.out.println("Client Ready");
     getmsg ob = new getmsg();
     ob.start();
     String rmsg, smsg;               
     while(true)
     {
        smsg = kr.readLine();
        pw.println(smsg);
        pw.flush(); 
      }                
    }                    
}        
class getmsg extends Thread
{
        public void run()
        {
            try
            {
                MesengerClient ob = new MesengerClient();
                 InputStream is = ob.s.getInputStream();
                 BufferedReader rr = new BufferedReader(new InputStreamReader(is));     
                String rmsg;    
                while(true)
                {
                    if((rmsg = rr.readLine()) != null) //receive from server
                    {
                        System.out.println(rmsg); // displaying at DOS prompt
                    }  
                }
            }
            catch(Exception e)
            {}
        }
}                
