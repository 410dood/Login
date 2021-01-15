# Mendix React Native Login with SSO

**DEPENDENCIES:**

-   NANOFLOW COMMONS
-   NATIVE MOBILE ACTIONS
-   COMMUNITY COMMONS
-   JWT

Mendix React Native SSO Login Setup

**1)** **AZURE**

1.	Set up an app registration in Azure for your app. It should include 
a.	In the implicit grant section select both the access and id token options - ? I only have id token selected 
b.	In the Redirect URI section set the callback to yourappname:// 
c.	Set the api permissions for MicrosoftGraph as follows 
	>	 email 
		Mail.Read 
		offline_access 
		profile 
 
4.	In the Expose Api section set the api permissions to https://{yourappname}-{environment}/user_impersonation  


**2)** **SETUP**

-   Add "ConfigurationOverview" page to Navigation (Web)
-   Add the "Login.Native_Anonymous" page as the home screen for Anonymous users Only.
    -   (Make sure to check security)
-   Add the "SNIP_OnResume" to all page templates (except the login page).

**3)** **DEPLOY YOUR APP TO THE CLOUD**

**4)** **CONFIGURATION**

-   Go to your app in the web and add the configuration variables in the configuration page
    

**5)** **RUN NATIVE BUILDER**

-   In order to redirect back to your application from a web browser, you must specify a unique URI to your app. This will be done in the new StudioPro Native Builder (8.16.0+).

1.  From StudioPro select  _Project → Build Native Mobile App_
2.  Select App Capabilities → DeepLink : Set value to your scheme (appname used in azure callback)

-  if you setup your callback in Step 1 the scheme should match that value without the  ://
	> ex:) If your callback =  _ssotest://_  then your scheme = **ssotest**





**6)** **ADD CERTIFICATES AND BUILD.**

