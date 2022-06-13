# IIS Windows Server Deploy


**Create Windows Server Instance** 

* Create Windows Server Instance on your uses Cloud `GCP, Azure, AWS` or anything else
* Minimum Server Configuration 2 Core, 4 GB Ram and 50GB SSD
* Create User With Password to remotely access the server
* Configure Firewall & Enable Port what you want you use in your Apps


**Configure Windows server**
* Install `Web Server (IIS)` in Windows Server
* [Install](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-aspnetcore-6.0.5-windows-hosting-bundle-installer) `Dont NET Hosting Bundle`
* [Install](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-aspnetcore-6.0.5-windows-x64-installer) Dot NET Core 6.0 Runtime SDK
* [Install](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16) `Microsoft SQL Server`
* [Install](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16)`SQL Server Management Studio (SSMS)`
* Restore `IPD` and `EHR.PoPReg` both database

**Publish App**

Open Project with Visual Studio & Publish Apps one by one. Make sure to `Solution Configure` should be `Release`. 

* Publish API 
* Publish WEB
* Publish Admin

**Here is screen shot ...**

![image](https://user-images.githubusercontent.com/92359442/173416161-8c48e502-f58a-4888-9586-15b1dd57f20c.png)

**Find Release**
* Brows Project `bin\Release\net6.0\publish` path to find the release files

![image](https://user-images.githubusercontent.com/92359442/173420505-af93421b-f11a-45a2-b216-f40e2990b2e4.png)

**Create Folder in root**

* Brows server directory  `C:\inetpub\wwwroot` 
* Create three folder `ipd_api`, `ipd_web` and `ipd_admin` in wwwroot directory 
* Copy All Release files one by one which we already publish in our projects path `bin\Release\net6.0\publish`
* Now Past it created folder one by one 

![image](https://user-images.githubusercontent.com/92359442/173422503-54ee69f4-04a8-4ad3-9ad8-a943b730d02b.png)

**Create Site In IIS Manager**

Make sure to select file path properly for every site. such as `ipd-api` for `C:\inetpub\wwwroot\ipd_api`. Now same as define `ipd-web` & `ipd-admin`.
Add port for every site which port you want to use. 

**NOTE:** Make Sure to all port are enable from your server firewall which you are used in your application 

* ipd-api 
* ipd-web
* ipd-admin

**Here is screen shot ...**

![image](https://user-images.githubusercontent.com/92359442/173423379-c91dbe44-106f-4ec8-8f9e-3ffc349aefb2.png)

**Configure App settings**

* Change Database Connection URL with your server database credential from `ipd_api` folder in `appsettings.json` file.
* Change Base URL from `ipd_web` in `appsettings.json` file.
* Change Database Connection URL with your server database credential from `ipd_admin` folder in `appsettings.json` file.

**Restart All Sites**

* Now Brows `WEB Apps` And `Admin Apps` with `Brows Website URL` which we already define at creation of site. 

**WEB APPS**

![image](https://user-images.githubusercontent.com/92359442/173426696-859cee2c-dca1-4e96-b902-6ee51fe336e1.png)

**Admin Apps**

![image](https://user-images.githubusercontent.com/92359442/173426831-e630a4ff-9463-4bc8-846e-b36b6289413d.png)


## Congratulations!! you have successfully done everything

Thank you so much. Please leave a comment if you find an issue I'm always open to solve
