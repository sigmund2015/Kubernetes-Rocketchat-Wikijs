
## IGT.NextGenServices is a project that aims to monitor a Windows service and perform actions based on the information obtained. 
-Altogether it consists of 5 projects:

### IGT.NextGenServices.Domain - .Net Standard 2.0 - Class Library
This project is the heart of the system containing all the business rules.

### IGT.NextGenServices.Data - .Net Standard 2.0 - Class Library
This project contains the implementation of a MongoDB repository and a SQL Server Repository (By default, the application now automatically connects to SQL Server.)

### IGT.NextGenServices.App - .Net Core 3.1 - Console App
This project was used basically to facilitate the validation of some methods that the service consumes.

### IGT.NextGenServices.Api - .Net Core 3.1 - Web Api
This project is a web API that serves to interact with the service through a No-SQL database.

- The API can be started using the dotnet run command by cli interface.
- Here is the list of endpoints:
   - The standard HTTPS port was maintained at 44359. Thus, the default address is:
   - https: // localhost: 44359
   - And each Endpoint has the following suffix:
   - / api / Healthcheck / v1
   - / api / Server / v1 
   - / api / ServerSettings / v1 
   - / api / EventLog / v1
- The collection of endpoints for POSTMAN can be obtained through the link below:
  https://www.getpostman.com/collections/2086b28a45fff933cc23

### IGT.NextGenServices.WindowsService - .Net Framework 4.7.2 - Windows Service Application  
A service created to check periodically if a specific windows service is running and restart it if necessary. This service has two timers.
- The first is configured by default to check every 5 seconds if the other service is running. This value is in milliseconds and can be modified through the Api.
- The second is configured by default to check every 5 minutes if the other service has a new status so that a specific action can be taken for it. This value is in milliseconds and can be modified via the API.
- The service is configured to save all operations to a MongoDB database.

#### Installing a Windows Service
1. First download / clone and compile the project.
2. Open “Command Prompt” and run as administrator
3. Fire the below command in the command prompt and press ENTER.
 
cd C:\Windows\Microsoft.NET\Framework\v4.0.30319 

4. Go to your project source folder > bin > Debug and copy the full path of your Windows Service exe file.
5. Use the syntax InstallUtil.exe + Your copied path + \your service name + .exe

Example: InstallUtil.exe C:\Users\MyUser\source\repos\WindowsServiceCheck\WindowsServiceCheck\bin\Debug\WindowsServiceCheck.exe

#### Initializing the service.
- By default the service will use the local system account. 
  - If necessary, use a different account
  [![Local System Account](https://i.imgur.com/TumrrJQ.png "Local System Account")](https://i.imgur.com/TumrrJQ.png "Local System Account")
  

#### Technical Requirements
 - [.NET Core 3.1](https://dotnet.microsoft.com/download/visual-studio-sdks?utm_source=getdotnetsdk&utm_medium=referral)
 - [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/visual-studio-sdks?utm_source=getdotnetsdk&utm_medium=referral)
 - [Visual Studio 2019](https://visualstudio.microsoft.com/pt-br/downloads/)
 - [Windows Operating System](https://www.microsoft.com/software-download/windows10)
 
