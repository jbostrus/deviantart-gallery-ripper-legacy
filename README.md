# deviantart-gallery-ripper-legacy

# TOC 
* [Function](#function) - explanation of script
* [Usage](#usage) - detailed usage example
* [Known Issues](#known-issues) - list of known problems with script usage
* [Change Log](#change-log) - details of changes between versions

# Function
Utility script to assist with downloading mass images from a DeviantArt gallery.
The script generates a textbox with direct image link urls at the top of a gallery page. Copy and paste the urls into download manager of choice. Tested and works best with [DownThemAll](https://addons.mozilla.org/en-US/firefox/addon/downthemall/) add-on for FireFox. Sample custom filter to select download links `[pre??.deviantart.net/,orig??.deviantart.net/,img??.deviantart.net/,www.deviantart.com/download/]`

# Usage
* Make sure that click through pagination is turned on and not scroll through or the script will malfunction.
  * ![img](http://i.imgur.com/RLxi4dY.png)
* Open a gallery page on DeviantArt website. There will be a small button under the gallery creator's profile image. Click it to start parsing out the direct image links. 
  * ![img](http://i.imgur.com/AmVwAah.png)
* Depending on the number of gallery pages it may take some time to parse it all out.
  * ![img](http://i.imgur.com/aQ9pX0j.png)
* After loading all the gallery index pages it starts loading each image page to parse the download link. If it doesn't have one it finds the largest sized image url and gives you that.
  * ![img](http://i.imgur.com/QEepmFC.png)
* Once completed there will be a textbox containing a list of direct download links for each of the images.
  * ![img](http://i.imgur.com/dWar0Ny.png)
* In the case of problems you may get a failure. You would need to load the problem pages manually and save images yourself.
  * ![img](http://i.imgur.com/SYjmD5S.png)

# Known Issues
* Download URLS are finicky. DA changed some back end code and the only known working download manager is DownThemAll. If you have issues and just want the best possible image urls change the "nodownloads: false" line to "nodownloads: true" in the global vars section after all the code comments.
* Download URLS in the form of www.deviantart.com/download/ will have a time limit on how long they are valid for. So while downloading a large content list they may expire and fail to download. This is not a bug in the script but a limitation placed by DeviantArt to prevent bots.  They also require the browser's cookies and a proper referer.

# Change Log
v1.1.14 Added ignore entry for single art pages so it no longer draws a download button on the full image page. Should only show up on galleries.
