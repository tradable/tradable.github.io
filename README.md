tradable
========

You will find on the tradable repositories tab a set of educational/starting points projects. Each project includes code that performs some trivial tasks such as printing the user's account Id in an App.
The projects can be used both as an educational purpose (by simply reading the code and seeing what it does) and as starting points for your own Apps.

Whether you want to learn how it works by looking at code or start your own App using this code, here is how you go about doing so:

Cloning and opening the project in Eclipse
-------------------------------------------------------

1. Make sure you are running Eclipse Juno or a later version with the Maven and WindowBuilder plugins installed. If this is not the case, fear not. You can install them quite easily form within Eclipse. For Maven: 
  * Go to Help -> Install New Software...
  * If you don't have the juno realeases site set up as a repository. Click Add, name it however you wish, then in the location space write: http://download.eclipse.org/releases/juno. (Of course if you have a later version of Eclipse, the link will be adapted to the name of that version)
  * Now in the search bar, search for m2e. Once the results pop up, select the **m2e - Maven Integration for Eclipse** packages from the *General Purpose Tool* and *Collaboration* packages. Also select the **Xtend M2E extensions**. Then next -> next -> finish

 For WindowBuilder The procedure is similar:
  * Go to Help -> Install New Software...
  * Click Add, name the repository "WindoWBuilder" or the like. You will find the link to include [here](http://www.eclipse.org/windowbuilder/download.php). For instance, for Juno you might copy: http://download.eclipse.org/windowbuilder/WB/release/R201209281200/4.2/
  * Select all the packages, then click next -> next -> finish   
  

2. Now That you are all setup and that you have made sure that you have setup your eclipse platform to develop tradable apps as per [this](http://apps.tradable.com/files/tradable%20for%20dummies%20Java%20App%20Guide.pdf) link. Let's import the project to Eclipse.
 * Open up your Shell (or git Shell) then navigate to your Eclipse Workspace using:   

            $ cd path/to/your/worksapce
 * Then clone the git repository using:

            $ git clone https://github.com/tradable/tradable-start-[name_of_start].git [name_of_directory_to_copy_to]
 * Once the directory is cloned in your Worskpace, you will probably want to remove the origin remote from your local repo, as you probably will not want to be linked to this repository as no actual work is done on it:

            $ git remote rm origin
 * Open up Eclipse and import the project by doing File -> Import -> Maven -> Existing Maven Projects. Then Browse to the directory you just imported from github, select /pom.xml and then press Finish.

 That's it. The project should now be opened in Eclipse with the name tradable-start-[name_of_start].

3. You can now go about setting up appropriate names for your project: 
 * Update the JRE System Library the project uses by right-clicking on JRE System Library and using the latest version available. 
 * Right click the classes names to rename them by doing refactor -> rename.
 * You will have to edit the **src/main/resources/META-INF/MANIFEST.MF** and the **src/main/resources/META-INF/spring/app-context.xml** files as per the link mentioned in point 2 to reflect your project's and/or your company 's name (remember that the "*class=*" qualifier in the app-context file takes the inverse .com name of your factorie's class as an argument). It is particularly important to rename the *Plugin-SymbolicName* value in the *MANIFEST.MF* file, as this is the value that the container will test against to see if the App is already installed in your tradable platform.
 * **But most importantly, you will have to edit the *pom.xml* file (preferably using the xml view of Eclipse) and change the GroupId and ArtifactId values.** Remember that the GroupId value should be in inverse .com notation and should reflect the name of the entity you are doing the project for and ArtifactId is quite simply the name of your project.  
 * Last, in your factory class, update the *getDisplayName()* and *getFactoryId()* methods so that they return appropriate values.

This will allow you to quickly get acquainted with the presented tradable APIs by examining the functionalities implemented in the example projects. 

If you want to have an overall view of all our APIs, go [here](https://developer.tradable.com/dms/dev/apidocs/latest/reference/packages.html).
