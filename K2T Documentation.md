# Kaizala to Teams Conversion Service

In April’19, it was [announced](https://techcommunity.microsoft.com/t5/microsoft-kaizala-blog/microsoft-kaizala-rolls-out-to-office-365-customers-globally-and/ba-p/394298) that Microsoft Kaizala capabilities will be integrated into Teams and the customers would need to eventually transition to Microsoft Teams. As a part of this customer promise, Kaizala to Teams Conversion Service was built to help them convert their custom Kaizala actions to Teams with minimal costs and at no additional investment from their end. This service can be used by tenant admins, developers, and business admins.

The conversion process can be completed by using the **Windows Command Line** tool. If you have a Kaizala Action Package file and need it to be converted to Teams app, then you can use the Command Line tool available on Windows for conversion process.  

Once the Teams app file is downloaded, the next step is to add it to Teams either through the Teams Admin portal, or by sideloading it from Teams desktop or web client. Ensure you have access to Azure Active Directory (AAD) account of the tenant you want to migrate the app to, and have permission to access Teams Admin Portal or can sideload the app from Teams client. 

This documentation helps you to understand how to convert custom Kaizala action package to Teams app:


**Prerequisites**

- Install [Node.js](https://nodejs.org/en/download/) locally on your machine. 
- Download Kaizala Package locally that you want to transform into teams app. If you don't have any Kaizala package, you can download zip from [Kaizala Management Portal](https://manage.kaiza.la/MiniApps/MiniApps).

**Conversion Steps**

1. Open Command Line on your machine.
2. Install *action-package-deploy* tool by running the below command: 
	
		npm install -g action-package-deploy 

3. To convert the Kaizala package to Teams app run the below command: 

		transform-kaizala-package -k <KaizalaPackageZipPath> -a <ActionPackageDownloadPath> [-t <TeamsAppDownloadPath>] [-p <ParameterJsonPath>] [--dn <DeveloperName> --dw <DeveloperWebsiteUrl> --dp <DeveloperPrivacyUrl> --dt <DeveloperTermsUrl>] 

	Parameters: 

		-k : Path of the kaizala package zip to transform. 
		-a : Path to download transformed action package. 
		-t : Path to download Teams app for sideloading on teams. 
		-p : Path of the json file that contains additional parameters. 

	Currently, JSON file supports additional parameters for developer details, which are absent in kaizala package and needed for creating a Teams app. It can be fed to the command by using a JSON file: 

		{​  ​  
		"developer":  
		{   ​  ​ 
			"name": "Contoso", 
			"websiteUrl": "https://www.contoso.com", 
			"privacyUrl": "https://www.contoso.com/privacy", 
			"termsOfUseUrl": "https://www.contoso.com/terms" 
		} 
		}​ 

	The user can also provide developer details by using the below parameters: 

		--dn : Developer name. 
		--dw : Developer website url. 
		--dp : Developer privacy url. 
		--dt : Developer terms of use url. 

	Sample Command: 

		transform-kaizala-package -k C:\Users\Contoso\Attendence\attendence.zip -a C:\Users\Contoso\Attendence -t C:\Users\Contoso\Attendence --dn Contoso --dw https://www.contoso.com –dp https://www.contoso.com/privacy --dt https://www.contoso.com/terms 

5. Once executed, the user will be asked to validate Azure AD credentials for conversion of Kaizala action package to Teams app zip file.  
5. An Azure AD custom app and Bot are programmatically created in your tenant to power the converted app in Teams. 
6. Converted Teams App file is available at the path provided in parameter `-t <TeamsAppDownloadPath>` in the above command. The user can sideload the app on Teams by using steps mentioned here. 
7. To modify the existing package, update the downloaded action package available at path `-a <ActionPackageDownloadPath>` and update the version field in the manifest. Ensure the latest version number is higher than the previous version number. Run the below command to download new Teams app file with the incorporated changes. 
	
		upload-action-package -z <ActionPackageZipPath> 

8. Once the Teams app is downloaded, follow the steps shared previously to install the app in Teams. 

9. Upload the app to Teams by going to **App Store > Upload a custom app** and then add it to a channel, group chat or a meeting chat. Alternatively, you may choose to upload it to Teams Admin Center and then enable it for selected teams. For more information, see [Upload your app in Teams](/microsoftteams/platform/concepts/deploy-and-publish/apps-upload).
	
	:::image type="content" source="Articles/Actions/K2T_Add_button.png" alt-text="This is K2T add button image.":::
	
10. Once the app is added to a team or group chat, you might need to create a Tab for the apps based on Form, Feedback and Attendance templates. Request to add a tab is prompted automatically when the app is added, or you may choose to do it manually by clicking on **+** button next to the tabs and picking the installed app from the list. For more information, see [Add an app to Microsoft Teams](https://support.microsoft.com/office/add-an-app-to-microsoft-teams-b2217706-f7ed-4e64-8e96-c413afd02f77).

	:::image type="content" source="Articles/Actions/K2T_Action_Logo.png" alt-text="This is K2T action logo image.":::

11. Once the tab is set up, the users can start responding by going to Messaging Extensions flyout and clicking on **…** button below compose box. 
12. The aggregated responses will either be available by clicking **View Details > Results** on the card, or by opening the tab as mentioned in step #9.

## FAQs

**What data is captured in Kaizala to Teams Conversion Service and how it is used?**

Kaizala to Teams Conversion Service requires user to upload custom Kaizala action package and requires the user to login with Azure AD account details. Once uploaded, Teams Conversion Service converts action package to Teams app by using Azure AD account for authentication. 
Additionally, the user also needs to provide necessary developer information, such as website, privacy URL, and terms of use URL, to be used for creating Teams app file.  

Once the converted Teams app is downloaded, the uploaded Kaizala Action package is deleted from the Teams Conversion Service.  

**Which Kaizala actions can be converted to Teams Apps using Kaizala to Teams Conversion Service?**

Kaizala to Teams Conversion Service supports conversion of all custom actions built by using Kaizala action designer, which includes survey, checklist, announcements, etc. 

**Will data also be migrated to Teams with actions?  Will it impact existing action being used in Kaizala?**

Kaizala to Teams Conversion Service only converts Kaizala Actions to Teams Apps and doesn't migrate any data or users to Teams. Moreover, the conversion has no impact on existing action being used in Kaizala. The converted action will behave as an independent app in Teams and the data will be collected afresh. 

**Why is conversion failing?**

There can be multiple reasons why app conversion could fail. Some of the known reasons along with their mitigation is shared below: 

- Kaizala actions could have app icons in different formats, such as .jpg, but Teams only accept PNG format as a valid app icon file throwing error in other cases. To mitigate this issue, update the icon to PNG before converting Kaizala Action to Teams app. 

- Kaizala actions can have long title, but length of Teams actions’ title can be only 32 characters. To mitigate this issue trim Kaizala action’s title to 32 characters before converting the package to Teams. 

**Which features might not work in the converted Teams app?** 

Conversion of action-designer based cards will be supported on KMP. Meaning, custom action cards cannot be convertible. Even within the supported **Action-designer based cards** some features might not work due to reasons, such as corresponding API not available on Teams platform, or capability not supported in Kaizala actions. 

The following capabilities are not supported in converted Teams app: 

- Send reminder 
- Duplicate a survey 
- Upload image from camera 
- Preview current location’s address and map image 
- Survey Action on Teams Desktop will not work if sharing current location is set to mandatory. This happens because required HTML5 API is not supported on Teams desktop client. 

### Privacy Statement  

This service is covered within the governance of Enterprise data usage policies. Find detailed Privacy statement of Microsoft here - [Microsoft Privacy Statement – Microsoft privacy](https://privacy.microsoft.com/privacystatement). 
