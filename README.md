# MQSpecturm-Assignment
This is the repository for the Java Assignment India.


-The source code is a Liferay Workspace in Ecplise IDE.

Installation
-------------

1. Install Liferay Plugin in the Ecplise IDE.
2. Import the zipped Liferay workspace
3. Create a new Liferay server:
     You can download the Liferay bundle using the link below:
     - Liferay Bundle: https://releases-cdn.liferay.com/portal/7.1.0-ga1/liferay-ce-portal-tomcat-7.1.0-ga1-20180703012531655.zip
     (Unzip the bundle in the bundles folder in the workspace)
4. Deploy the modules by dragging them down to the Liferay server or adding the modules in the "Add and remove" menu.
5. Open http://localhost:8080/ in your web browser.
6. You can find the portlets in the Category "Custom Portlets".

Contents and explanation
-------
There are totally three Portlets (modules), namely:
	-userWelcome : Displays the name of the currently logged in user and a greeting.
	-userDisplay : Displays all the users present in the Database.
	-userSearch : Searches if a user is present or not and displays the appropriate messages.

Explanation of the modules:
---------------------------------

-userWelcome : The name of the user is retrieved from the code : “PortletRequest.USER_INFO” and displayed in view.jsp.
-userDisplay : The list of users in the database is retrieved from the code below:
		
	       List<User> user_list = UserLocalServiceUtil.getUsers(QueryUtil.ALL_POS, QueryUtil.ALL_POS);

	       This list is then returned to the view.jsp file and displayed in the form of a table. 
-userSearch : An alloyUI form is rendered to get the name of the user to be searched. The name is retrieved in the Java class using the:

	   String name = ParamUtil.getString(request, "userName");
	
	   If the user exists, a success message is rendered using the "SessionMessages".
	   Else, a error message is returned to view.jsp.
