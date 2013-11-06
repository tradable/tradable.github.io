tradable example Apps
========

Each project listed on this page includes code that performs some task, ranging from 
trivial, like printing the user's account Id in an App to more involved like dealing with orders
sent by a user and monitoring positions or building an algo trading bot.

List of Examples:
--------------------------
You will find here a list of repositories containing educational/starting points projects. 

###Standard Apps:
   
  * [Hello World Example](https://github.com/tradable/tradable-start-HelloWorld)  
  Simple Hello World app to get started from a roughly empty project.
  * [Account ID](https://github.com/tradable/tradable-start-accountID)  
  Simple app which displays the use of the *com.tradable.api.services.account* to display the
  accountID in a JLabel.
  * [Account Metrics](https://github.com/tradable/tradable-start-useAccountMetrics)  
  App displaying the use of the *com.tradable.api.services.analytics* API to
  display the account Metrics in a few JLabels.
  * [Environment Service](https://github.com/tradable/tradable-start-useEnvironmentService)  
  Learn how to use the *com.tradable.api.services.environment.EnvironmentService* API to
  identify some information about the user.
  * [Historic Market Data](https://github.com/tradable/tradable-start-useHistoricMarketData)  
  App that prints all the historical times and prices (open, close etc...) for a certain
  Symbol (chosen arbitrarily) at a given frequency between two dates. this is done by using
  the *com.tradable.api.services.historicmarketdata* API.
  * [Market Depth & VWAP](https://github.com/tradable/tradable-start-useMarketDepth)  
  This app shows what recent volume moved the market and what the price associated to the move
  is. It also uses the service to display how to compute the [VWAP](http://en.wikipedia.org/wiki/Volume-weighted_average_price).
  * [Instruments](https://github.com/tradable/tradable-start-useInstruments)  
  This app uses the *com.tradable.api.services.instrument* API to show how one would update
  their list of instruments accessible to a user when instrument updates occur.
  * [JavaFX Browser](https://github.com/tradable/tradable-start-JavaFXBrowser)  
  A simple JavaFX browser project. You can use this as a starting point to integrate JavaFX in
  your app.
  * [Send and Manage Orders](https://github.com/tradable/tradable-start-np)  
  A longer example apps than most others. Follow the link and you will find a tutorial on how
  to send and manage orders in the tradable platform.
  * [tradable Standard Widgets](https://github.com/tradable/tradable-start-useWidgets)  
  This app displays in an app most of the widgets you can use from the tradable APIs.
  * [Order Entry pop-up Widget](https://github.com/tradable/tradable-start-OrderEntryWidget)
  This app quite simply pops up an order entry widget identical in look and behavior to the
  one in standard Order Entry app available by default in tradable

###Algo Apps:
  
  * [Williams Percent Range Indicator](https://github.com/tradable/tradable-algo-start-wprIndicator)  
  This App displays how one can use indicators by creating a WPR on for the platform.
  * [SMMA Indicator](https://github.com/tradable/tradable-algo-start-SMMA)  
  This is an implementation of the Smoothed Moving Average Indicator as defined [here](http://www.dailyfx.com/forex_forum/signal-strategy-fxcm-marketscope/237441-smoothed-moving-average-smma.html).
  * [Alligator Indicator](https://github.com/tradable/tradable-algo-start-alligatorIndicator)
  This project displays how to use a custom indicator (here the SMMA) as input data in another project.
  * [MACD automatic trading strategy](https://github.com/tradable/tradable-algo-start-macd)
  Use the algo API to create trading bots. This app uses the tradable algo API to implement a
  bot that uses a MACD trading strategy.


Whether you want to learn how it works by looking at code or start your own App using this code, here is how you go about doing so:

Cloning and opening the project in Eclipse
-------------------------------------------------------

1. Make sure you are running Eclipse Juno or a later version with the Maven and WindowBuilder plugins installed. If this is not the case, fear not. You can install them quite easily form within Eclipse. For Maven: 
  * Go to Help -> Install New Software...
  * If you don't have the juno realeases site set up as a repository. Click Add, name it however you wish, then in the location space write: http://download.eclipse.org/releases/juno. (Of course if you have a later version of Eclipse, the link will be adapted to the name of that version)
  * Now in the search bar, search for m2e. Once the results pop up, select the **m2e - Maven Integration for Eclipse** packages from the *General Purpose Tool* and *Collaboration* packages. Also select the **Xtend M2E extensions**. Then next -> next -> finish

 For WindowBuilder The procedure is similar:
  * Go to Help -> Install New Software...
  * Using the Juno (or later) repository as for installing the Maven plugin, search for *windowbuilder* and select the *General Purpose Tools* package
  * You will also need to make sure the SWT plugin is installed. This time search for *SWT* and select here too the *General Purpose Tools* package
  * Click next -> next -> finish. Then restart Eclipse.
  

2. Now That you are all setup and that you have made sure that you have setup your eclipse platform to develop tradable apps as per [this](http://apps.tradable.com/files/tradable%20for%20dummies%20Java%20App%20Guide.pdf) link. Let's import the project to Eclipse.
 * Open up your Shell (or git Shell) then navigate to your Eclipse Workspace using:   

            $ cd path/to/your/worksapce
 * Then clone the git repository using:

            $ git clone https://github.com/tradable/tradable-start-[name_of_start].git [name_of_directory_to_copy_to]
 * Once the directory is cloned in your Worskpace, you will probably want to remove the origin remote from your local repo, as you probably will not want to be linked to this repository as no actual work is done on it:

            $ git remote rm origin
 * Open up Eclipse and import the project by doing File -> Import -> Maven -> Existing Maven Projects. Then Browse to the directory you just imported from github, select /pom.xml and then press Finish.

 That's it. The project should now be opened in Eclipse with the name tradable-start-[name_of_start].

Note: for those of you who do not use or want to use git or github, you can just go to the project's github page: *https://github.com/tradable/tradable-start-[name_of_start].git* then on this page, click on the Zip button to download the project as a zip file on your computer. Then extract it and rename the extracted folder. You can now do the Eclipse step mentioned above.

3. You can now go about setting up appropriate names for your project: 
 * Update the JRE System Library the project uses by right-clicking on JRE System Library and using the latest version available. 
 * Right click the classes names to rename them by doing refactor -> rename.
 * You will have to edit the **src/main/resources/META-INF/MANIFEST.MF** and the **src/main/resources/META-INF/spring/app-context.xml** files as per the link mentioned in point 2 to reflect your project's and/or your company 's name (remember that the "*class=*" qualifier in the app-context file takes the inverse .com name of your factorie's class as an argument). It is particularly important to rename the *Plugin-SymbolicName* value in the *MANIFEST.MF* file, as this is the value that the container will test against to see if the App is already installed in your tradable platform.
 * **But most importantly, you will have to edit the *pom.xml* file (preferably using the xml view of Eclipse) and change the GroupId and ArtifactId values.** Remember that the GroupId value should be in inverse .com notation and should reflect the name of the entity you are doing the project for and ArtifactId is quite simply the name of your project.  
 * Last, in your factory class, update the *getDisplayName()* and *getFactoryId()* methods so that they return appropriate values.

This will allow you to quickly get acquainted with the presented tradable APIs by examining the functionalities implemented in the example projects. 

If you want to have an overall view of all our APIs, go [here](https://developer.tradable.com/dms/dev/apidocs/latest/reference/packages.html).
