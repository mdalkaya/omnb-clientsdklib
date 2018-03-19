# omnb-clientsdklib
OpenMedia/NewsBoard ClientSDK Library


Copy the Client SDK Libraries to the output directory
This adds the OMWebPluginLib to the window object. Note that this is not UMD compatible.

```html
    <script src="path-to-LibFolder/OMWebPluginLib/common/index.js"></script>
    <script src="path-to-LibFolder/OMWebPluginLib/common/api.js"></script>
    <script src="path-to-LibFolder/OMWebPluginLib/host/channel.js"></script>
    <script src="path-to-LibFolder/OMWebPluginLib/host/api.js"></script>
    <script src="path-to-LibFolder/OMWebPluginLib/plugin/index.js"></script>
```

#Usage

``` index.js

var OMApi = OMWebPluginLib.OMApi;
var builder = WpLib.Plugin.SamePageBuilder.create(); //.onNotify(onClientNotify)
var plugin = WpLib.Plugin.createPlugin(builder);
var config = builder.getPluginConfig();
var api = plugin.getApi();


int templateId 	= 4104;   //OpenMedia Template ID
int folderLoId 	= 4096;   //OpenMedia Folder ID 
int poolId 		= 3;        //OpenMedia Pool ID
string systemId	= "";     //OpenMedia System ID or blank if current System

// Create Documents
   api.createDocument(templateId, folderLoId, poolId, systemId)
            .then(function (resultJSON) {
			
			console.log("Document successfully created: " + resultJSON.lowId);
			});
      
// Get the Document ID   
   api.getCurrentDocumentId()
            .then((docID) => {
        	console.log("Document successfully created: " + resultJSON.lowId);
      	});
    
