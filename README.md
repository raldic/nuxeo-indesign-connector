# nuxeo-indesign-connector
<img src="Screen-Shot.png"/>  
The nuxeo Connector for InDesign enables designers to import assets into an InDesign layout directly from nuxeo.
The connector is divided into 2 parts, a server side and a client side.

## Server side plugin

**How to build**  
Go to the sub-folder **nuxeo-indesign-connector-server** and build the marketplace package using the following command line:
```
mvn install
```

**How to install**  
You will end up with a zip containing the marketplace package located here:  ***/marketplace-nuxeo-indesign-connector/target/marketplace-nuxeo-indesign-connector-1.0-SNAPSHOT.zip***.
Once you installed the package into your nuxeo instance, you need to select the folders to which you want the ***Guest User*** to have a read-only access (This is done under nuxeo instance directly).


## Client side Plugin

**How to build**  
Go to the **nuxeo-indesign-connector-client** folder and run the following command line:
```
mvn install
```
This will copy all the necessary files for the inDesign plugin under the **package** folder.

**How to install**  
Step 1  
 Copy the folder "org.nuxeo.indesignconnector" that you'll find under the **package** folder :
```
On Mac, into ~/Library/Application\ Support/Adobe/CEP/extensions
```
```
On Windows, into %APPDATA%\Adobe\CEP\extensions
```
Step 2  
On Mac
- Double click on the file **EnableUnsignedExtensions.command** that you will find under the "package/Scripts" folder.

On Windows
- Open the registry key **HKEY_CURRENT_USER/Software/Adobe/CSXS.4** and add a key named PlayerDebugMode, of type String, and value 1.

Step 3  
Restart inDesign and go to **Window > Extensions > nuxeo InDesign Connector**.  
Once there click on the settings icon and fill in the following informations:
- url of your nuxeo instance
- login
- password  

If everything went well you should end up having a list of assets displayed.
Once there, if you want to add an asset into your inDesign document you just need to click on the thumbnail.

## Link persistency
Now, anytime your asset is modified within nuxeo you'll get a badge notification beside the reload icon. All you need to do is click on it and the
new version of the asset will be imported.
You then need to display the links panel (**Window > links**) and double click on the alert icon to replace the old version by the new one.

## About Nuxeo

Nuxeo provides a modular, extensible Java-based [open source software platform for enterprise content management](http://www.nuxeo.com/en/products/ep) and packaged applications for [document management](http://www.nuxeo.com/en/products/document-management), [digital asset management](http://www.nuxeo.com/en/products/dam) and [case management](http://www.nuxeo.com/en/products/case-management). Designed by developers for developers, the Nuxeo platform offers a modern architecture, a powerful plug-in model and extensive packaging capabilities for building content applications.

More information at <http://www.nuxeo.com/>
