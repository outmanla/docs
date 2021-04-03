# ontributing to github/docs
<html>
   <head>
      <title>Inwindow Outdoor</title>
      <meta http-equiv="content-type" content="text/html; charset=utf-8" />
      <meta name="description" content="" />
      <meta name="keywords" content="" />
      <link rel="stylesheet" href="styles.css">
    
      <script type="text/javascript" src="https://maps.googleapis.com/maps/api/js?v=3"></script>
      <script type="text/javascript" src="http://code.jquery.com/jquery-1.12.0.js"></script>
      
      <script type="text/javascript" src="geoMark.js"></script>
   </head>
   <body>
   <div id="menu" style="float:left;">
      <ul id="dock">	  
         <li id="addresses">
            <ul id="check">
               <li id="header" class="header"><a href="#" class="dock">Dock</a><a href="#" class="undock">Undock</a>Addresses</li>
               <li id="searchBox">  <input type="text" name="search" id="search" placeholder="type address to search for" style="width: 100%;"> </li>
               <li id="searchResult">
                  <div id="update" style="padding:10px; border-style: solid;"> </div>
               </li>
            </ul>
			<ul id="list" style="top:100px;"> </ul>
         </li>
         <li id="tours">
            <ul>
               <li class="header"><a href="#" class="dock">Dock</a><a href="#" class="undock">Undock</a>Tools</li>
               <li>
                  <div id="startDiv" style="padding:10px 0px;">
                     Add Location
                     <input type="text" name="locationStart" id="location" style="width: 100%;" onkeyup="javascript:setNextDivUp('imgMarker');"placeholder="Name">
                     <div id="imgMarker" class="previewImg" style="padding:10px 0px;visibility:hidden;">
					 <input type="file" class="hidden" id="uploadFile" onchange="previewFile()"><br>
					 <div class="button" id="uploadTrigger">Browse</div>
                        <img id="markerImage" src="" style="max-width:100%;max-height:100%;font-style:italic;color:#28597a;" alt=" Your Image will appear here"> 
					  </div>
					  <div id="markerLink" style="padding-top:60px;visibility:hidden;">
					   <a  href="#" onclick="javascript:pinPointMarker();"> Place a marker </a>
					   </div>
                  </div>
				   <div id="operation" style="padding:10px 0px;visibility:hidden;">
				     <input type="button" name="clear" value="Clear" class="button">
				     <input type="button" name="addLocation" value="Add Location" onclick="javascript:addLocation();" class="button">
                     <input type="button" name="createTour" value="Create Tour" onclick="javascript:createTour();" class="button">
                  </div>
               </li>
             
            </ul>
         </li>
      </ul>
	  </div>
      <div id="dvMap" style="height: 100%;margin-left:40px"></div>
   </body>
</html>
Check out our [contributing.md](../CONTRIBUTING.md) to see all the ways you can participate in the GitHub docs community :sparkling_heart:

Here, you'll find additional information that might be helpful as you work on a pull request in this repo.

- [development](./development.md) - steps for getting this app running on your local machine
- [content markup reference](./content-markup-reference.md) - how to use markup and features specific to the GitHub Docs site
- [content style guide](./content-style-guide.md) - style guidance specific to GitHub Docs content and additional resources for writing clear, helpful content
- [deployments](./deployments.md) - how our staging and production environments work
- [liquid helpers](./liquid-helpers.md) - using liquid helpers for versioning in our docs
- [localization checklist](./localization-checklist.md) - making sure your content is ready to be translated
- [node versions](./node-versions.md) - our site runs on Node.js
- [permalinks](./permalinks.md) - permalinks for article versioning
- [redirects](./redirects.md) - configuring redirects in the site
- [search](./search.md) - our search functionality is powered by [Algolia](https://www.algolia.com)
- [troubleshooting](./troubleshooting.md) - some help for troubleshooting failed and stalled status checks
