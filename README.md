# allianz-hsbc-admin
This project provides a working theme plugin for Liferay, as well as other necessary UI changes required by Allianz-HSBC.

## Setup
Download [Liferay Portal 6.2 bundled with Tomcat](http://sourceforge.net/projects/lportal/files/Liferay%20Portal/6.2.1%20GA2/liferay-portal-tomcat-6.2-ce-ga2-20140319114139101.zip/download?download=http%3A%2F%2Fsourceforge.net%2Fprojects%2Flportal%2Ffiles%2FLiferay%2520Portal%2F6.2.1%2520GA2%2Fliferay-portal-tomcat-6.2-ce-ga2-20140319114139101.zip%2Fdownload) for testing environment.

Download [Liferay Plugins SDK](http://sourceforge.net/projects/lportal/files/Liferay%20Portal/6.2.1%20GA2/liferay-plugins-sdk-6.2-ce-ga2-20140319114139101.zip/download?download=http%3A%2F%2Fsourceforge.net%2Fprojects%2Flportal%2Ffiles%2FLiferay%2520Portal%2F6.2.1%2520GA2%2Fliferay-plugins-sdk-6.2-ce-ga2-20140319114139101.zip%2Fdownload).

- Extract both Liferay Portal and its Plugins SDK.
- For first time usage, run your Liferay Portal using the bundled server (Tomcat):
 * Run the server:

    ```$ ./liferay-portal-6.2-ce-ga2/tomcat-7.0.42/bin/startup.sh```
  
 * Open your browser, and navigate to `http://localhost:8080`
 * Follow the installation wizard, and you are ready to use the Liferay CMS.

- Configure the Plugins SDK to start working on the theme:
 * Run the create script:

    `$ bash liferay-plugins-sdk-6.2/themes/create.sh test "Test"`

    This command will produce the basic file structure to develop a theme plugin (in this case *test-theme* folder will be created).
 * Open **build.xml** in /liferay-plugins-sdk-6.2/themes/test-theme/, modify the value of **theme.parent** to be `classic` (line 7).
 * Open **build.properties** in /liferay-plugins-sdk-6.2/. Make sure the value of **app.server.parent.dir** (line 29) points to the correct location of your Liferay Portal.
 * Place this cloned source in /liferay-plugins-sdk-6.2/themes/test-theme/docroot/.
 * Rename the folder name as **_diffs** replacing the existing _diffs.

## Deploy
- At /liferay-plugins-sdk-6.2/themes/test-theme/ deploy your theme by running:

  `$ ant deploy`

- Open your Liferay Portal, and you will see your newly-created theme in the Look and Feel section.

