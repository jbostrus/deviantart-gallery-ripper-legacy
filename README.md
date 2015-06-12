# deviantart-gallery-ripper-legacy

# TOC 
* [Function](#function) - explanation of script
* [Usage](#usage) - detailed usage example
* [Known Issues](#known-issues) - list of known problems with script usage
* [Change Log](#change-log) - details of changes between versions

# Function <a name="function"></a>
Utility script to assist with downloading mass images from a DeviantArt gallery.
The script generates a textbox with direct image link urls at the top of a gallery page. Copy and paste the urls into download manager of choice. Tested and works best with [DownThemAll](https://addons.mozilla.org/en-US/firefox/addon/downthemall/) add-on for FireFox. Sample custom filter to select download links `[pre??.deviantart.net/,orig??.deviantart.net/,img??.deviantart.net/,www.deviantart.com/download/]`

# Usage <a name="usage"></a>
* Make sure that click through pagination is turned on and not scroll through or the script will malfunction.
  * ![img](https://dl.dropboxusercontent.com/u/29157236/006%20Click%20Through.png)
* Open a gallery page on DeviantArt website. There will be a small button under the gallery creator's profile image. Click it to start parsing out the direct image links. 
  * ![img](https://dl.dropboxusercontent.com/u/29157236/001%20Start.png)
* Depending on the number of gallery pages it may take some time to parse it all out.
  * ![img](https://dl.dropboxusercontent.com/u/29157236/002%20Scanning%20Gallery%20List.png)
* After loading all the gallery index pages it starts loading each image page to parse the download link. If it doesn't have one it finds the largest sized image url and gives you that.
  * ![img](https://dl.dropboxusercontent.com/u/29157236/003%20Loading%20Image%20Pages.png)
* Once completed there will be a textbox containing a list of direct download links for each of the images.
  * ![img](https://dl.dropboxusercontent.com/u/29157236/004%20Complete%20Success.png)
* In the case of problems you may get a failure. You would need to load the problem pages manually and save images yourself.
  * ![img](https://dl.dropboxusercontent.com/u/29157236/005%20Complete%20Failed%20with%20List.png)

# Known Issues  <a name="known-issues"></a>
* Download URLS are finicky. DA changed some back end code and the only known working download manager is DownThemAll. If you have issues and just want the best possible image urls change the "nodownloads: false" line to "nodownloads: true" in the global vars section after all the code comments.
* Download URLS in the form of www.deviantart.com/download/ will have a time limit on how long they are valid for. So while downloading a large content list they may expire and fail to download. This is not a bug in the script but a limitation placed by DeviantArt to prevent bots.  They also require the browser's cookies and a proper referer.
* When browsing a search/gallery and clicking a thumbnail to load full image on HTML5 browsers the GET button disappears. This is because DA hides the panel holding the button. Refreshing the page while viewing the single image will redraw the GET button allowing you to grab all images in the image artist's gallery.

# Change Log <a name="change-log"></a>
v1.1.13 Added boolean option in pages object to allow disabling the direct download link offering.