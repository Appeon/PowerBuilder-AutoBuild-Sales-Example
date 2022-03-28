# PowerBuilder-AutoBuild-Sales-Example

This GitHub repository contains the example files of the PBAutoBuild210 feature.
This example demonstrates how to use PBAutoBuild210.exe to download source code from the source code control sever, merge it into PBL, and auto build and deploy the traditional C/S project, the PowerClient project, and the PowerServer project based on the configurations in the JSON file.
Before you use this Example, it’s suggested that you learn the details about using PBAutoBuild210 through the site below:
https://docs.appeon.com/pb2021/whats_new/automated_CI_CD_for_projects.html  

### Sample Project Structure

The project is structured as follows.

```
|—— PowerBuilder-AutoBuild-sales-Example Repository 
	|—— AutoBuild_PowerBuilder.Bat		Auto build and deploy the traditional C/S project
	|—— AutoBuild_PowerClient.Bat		Auto build and deploy the PowerClient project
	|—— AutoBuild_PowerServer.Bat		Auto build and deploy the PowerServer project
	|—— Command_DeleteFolder.bat		Delete the downloaded folder
	|—— Command_StartLocalWebAPI.bat	Compile and run PowerServer Web API
	|—— pb_salesdemo.json			Auto build and deploy the JSON file required by the traditional C/S project
        |—— pc_salesdemo.json			Auto build and deploy the JSON file required by the PowerClient project
	|—— ps_salesdemo.json			Auto build and deploy the JSON file required by the PowerServer project
```

### Setting Up the Project

Download this PowerBuilder AutoBuild Sales Example, and then:

1. Open the pb_salesdemo.json file. Find User and Password under the BuildPlan -> SourceControl -> GIT node and replace them with your GitHub User and Password.
   Note: The Password here should be the encrypted one which you can get by running pbautobuild210.exe /p yourpassword in CMD.
2. Follow the same way in step #1 to change the GitHub User and Password in the pc_salesdemo.json and ps_salesdemo.json files.
3. Open the ps_salesdemo.json file. Go to Projects -> ps_salesdemo -> WebAPIs -> LicenseSettings and set the SpecifyThePowerServerLicense to your PowerServer License.
4. Execute the PowerBuilder AutoBuild feature according to the instructions below:
     -If you want to auto build and deploy as a traditional C/S project, please run the AutoBuild_PowerBuilder.Bat file. It will automatically download the SalesDemo source code, merge it into PBL, and then build and deploy as a traditional C/S project.
     -If you want to auto build and deploy as a PowerClient project, please run the AutoBuild_PowerClient.Bat file. It will automatically download the SalesDemo source code, merge it into PBL, and then build and deploy as a PowerClient project.
     -If you want to auto build and deploy as a PowerServer project, please run the AutoBuild_PowerServer.Bat file. It will automatically download the SalesDemo source code, merge it into PBL, and then build and deploy as a PowerServer project.

Note: When you run this Example, it will download the source files of Sales Demo from https://github.com/Appeon/PowerBuilder-AutoBuild-Sales-SourceCode, so you need to have your own GitHub User and Password and provide them as instructed in step#1 and step #2.
