# MySqlConnection
Learning and having a bit of trouble with my code.  



  package Movies;
      import java.sql.Connection;
      import java.sql.*;
      import java.sql.DriverManager;
      
      public class Director {
    
      public static void main(String[] args) {
          
      
      String myUrl = "jdbc:mysql://localhost:3306/practice_schema"; 
      Connection conn = null;
      try { 
     
      conn = DriverManager.getConnection(myUrl, "root", "password");
        if (conn != null) { 
        System.out.println("Connection established!");
        }
      Statement st = conn.createStatement();
      ResultSet rs = st.executeQuery("SELECT * FROM Directors");
       
      while(rs.next()) {
      int id = rs.getInt("id"); 
      String first_name = rs.getString("first_name");
      String last_name = rs.getString("last_name");
          System.out.printf("%s %s %s\n", id, first_name, last_name);
      }
      st.close();
      }
      catch(Exception e) {
          System.err.println("Error! Error!");
          e.printStackTrace();
         } finally {
          System.out.println("Keep Working On It!!\n\n");
          }
    
        }
    
      }
    
    //The output that I get is:
    
    
    Error! Error!
    java.sql.SQLException: No suitable driver found for jdbc:mysql://localhost:3306/practice_schema
            at java.sql.DriverManager.getConnection(DriverManager.java:689)
            at java.sql.DriverManager.getConnection(DriverManager.java:247)
            at Movies.Director.main(Director.java:15)
    Keep Working On It!!

     //Any help is greatly appreciated.  Thanks


