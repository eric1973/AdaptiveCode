# Chapter 5 - Single Responsibility Principle

**Setup the Database**

	1. Modifiy ConnectionString in AdoNetTradeStorage.cs

	   original: 
				   using (var connection = new System.Data.SqlClient.SqlConnection("Data Source=(local);Initial Catalog=TradeDatabase;Integrated Security=True;"))

			

	   In my case my DB instance is running at .\\SQLEXPRESS2012. Therefore I substitute the (local) with it.
	   
	   modified:   using (var connection = new System.Data.SqlClient.SqlConnection("Data Source=.\\SQLEXPRESS2012;Initial 		
				   Catalog=TradeDatabase;Integrated Security=True;"))

				   
	2. In Project Database right-click -> Properties -> Project Settings -> Select your SQL Server Plattform. In my case
	   I selected "SQL Server 2012".

	3. Recompile the whole solution.

	4. In Project Database right-click -> Publish
	   The Database is named "TradeDatabase" in the connection string.
	   Choose "TradeDatabase" instead of "Database" in the Database field or change the Initial Catalog in the connection
	   string to "Database".
	   Click on "Edit...". Here select the Server instance (in my case .\SQLEXPRESS2012) and click OK.
	   Then click on "Generate Script" (or Publish, but I prefer to execute the script by myself.)
	   
	   The script gets generated and opened in Visual Studio. Here you can click on the green Run Script button in the toolbar.
	   The database gets generated.
	   
	5. Now run the "SingleResponsibilityPrinciple" console app and it should work. If not take a look into MS SQL Server Explorer
	   if the "TradeDatabase" is properly created.