# DEPRECATED
This repository is no longer in active development & use.<br>
[<img src="https://www.mapmyindia.com/api/img/mapmyindia-api.png" height="40"/> </p>](https://www.mapmyindia.com/api)

# Nearby COVID Vaccine Centres, Hospitals etc Search Widget (FREE)

## Introduction
This is an easy & FREE to integrate Nearby COVID Places Search (such as Vaccine Centres, Hospitals, Testing Centres, Isolation Centres etc) Widget by MapmyIndia.

Every person can benefit from being able to easily find nearby COVID vaccination centres, hospitals, testing centres etc - see them on a map, get directions, and get more information about them. 

We at MapmyIndia are continuously updating the database of COVID-related places, such as vaccine centres, treatment centres/hospitals, containment zones, testing centres, isolation centres etc. This is the most comprehensive pan India covid related map database, and we've released it for free through our MapmyIndia Move app (mapmyindia.com/move) and MapmyIndia Maps portal (maps.mapmyindia.com) and MapmyIndia Corona guide (maps.mapmyindia.com/corona).

We're helping ANY website or app developer to easily integrate this information, as a FREE widget, for the benefit of your users and visitors. 

The widget can be used to search for vaccination centres, testing centres, sample collection centres, treatment centres, quarantine centres and micro containment zones across India.

![](https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/covid-place-widget1.gif)

*The image is for illustrative purposes only on how the widget might look like once integrated.

## Version History
| Version | Last Updated | Author | Release Note |
| --- | --- | --- | --- |
| 2.0 | 27 April 2021 | Kunal Bharti([KB](https://github.com/kunalbharti)) | Can search for Vaccination Centres, Testing Centres, Treatment Centres, Containment Zones,  Sample Collection Centres, Quarantine Centres |
| 1.1 | 24 April 2021 | Rohan Verma([RV](https://github.com/rohanverma85)) | Sample Updated |
| 1.0 | 24 April 2021 | Kunal Bharti([KB](https://github.com/kunalbharti)) | Initial Commit |

<br>

## 3 Step process to integrate Nearby COVID Places widget in any Web App
<br>

1. #### Step 1
    Inside the <body> section of HTML of web page, define a div into which the nearby COVID places widget from MapmyIndia needs to be loaded.
    ```html
    <div id=“nearby-covid-places-mapmyindia”></div>
    ```

2. #### Step 2
    Inside the <head> section of HTML of web page, or wherever else you find more suitable, include the following MapmyIndia javascript code.
    ```html
    <script src=“https://maps.mapmyindia.com/covid-places/showNearbyCovidPlacesOnMap.js”></script>
    ```
3. #### Step 3 
    To load up the nearby COVID places widget from MapmyIndia, call the following javascript code **AFTER** the mapmyindia javascript file (as defined in step 2) has loaded.
    ```js
    loadNearbyCovidCentresMapmyIndiaDiv(document.getElementbyId(“nearby-covid-places-mapmyindia”));
    ```
That’s it - all done! 

On reloading your web page after integrating the code - 
1) You should see a MapmyIndia Map on left, search box on top right, and based on current location the nearest COVID places in right panel.
2) The first time the code loads, the user may be prompted to share current location to browser so that the map and search results can be localised to the user
3) User can type into search box, any place of his/her interest, and as he/she types, suggested search results will get populated. Upon clicking of any, new map location with markers of the nearby COVID places, and search results in the panel will get updated.
4) In the search results panel (and on clicking a marker on the map) - details of the COVID places will show up AND a ‘Get Directions’ button will be there, clicking on which user will be directed to the the directions page (external link).

### `loadNearbyCovidCentresMapmyIndiaDiv()` Method

#### Required Parameters
1. `divID`: This is a mandatory parameter which allows the widget to recognise the div where the content of the widget is to be loaded. 

#### Optional Parameters
1. `Params`: 
    - `css`(string): css' absolute URL as per the design of the target web app. This is ONLY required if and only if the target app wishes to over-ride the default css which is implicitly part of the plugin.<br>
    <strong><span style="color:teal;">NOT RECOMMENDED TO CHANGE.</span></strong> Please change only if absolutely necessary.

## Sample Code
```html

<html>
<head>
  
  <!-- Include the following MapmyIndia javascript code into your webpage -->
  <script src="https://maps.mapmyindia.com/covid-places/showNearbyCovidPlacesOnMap.js"></script>

</head>
<body>

   <!-- define the div into which the nearby COVID places widget from MapmyIndia needs to be loaded --> 
   <div id="nearby-covid-places-mapmyindia"></div>

   <!-- call the following code AFTER the mapmyindia javascript file has loaded -->    
   <script type="text/javascript">
        loadNearbyCovidCentresMapmyIndiaDiv(document.getElementById("nearby-covid-places-mapmyindia"));
    </script>
</body>

</html>

```


## How to customize CSS to match the style of the plugin with your web app

### Sample CSS 
<strong>(change NOT recommended)</strong>
```css 
https://maps.mapmyindia.com/covid-places/css/custom.css
```

To be passed as
```js
loadNearbyCovidCentresMapmyIndiaDiv(document.getElementById("nearby-covid-places-mapmyindia"),{css:"https://maps.mapmyindia.com/covid-places/css/custom.css"});
```
<br>

## How to Search for Different Categories of COVID Places

The Nearby COVID Places Widget already has the capabilities to search for not only nearby vaccination centres, but other important COVID places as well. 
To search for other categories of COVID places, a simple additional parameter in the script URL of the widget enables you to specify which category you want the widget to search for.
<br>

### Sample Search for Corona Treatment Centres

#### Script URL

```html
<script src="https://maps.mapmyindia.com/covid-places/showNearbyCovidPlacesOnMap.js?category=HSPTMT"></script>
```

#### Sample Code
```html
<html>
<head>
  
  <!-- Include the following MapmyIndia javascript code into your webpage -->
  <script src="https://maps.mapmyindia.com/covid-places/showNearbyCovidPlacesOnMap.js?category=HSPTMT"></script>

</head>
<body>

   <!-- define the div into which the nearby COVID places widget from MapmyIndia needs to be loaded --> 
   <div id="nearby-covid-places-mapmyindia"></div>

   <!-- call the following code AFTER the mapmyindia javascript file has loaded -->    
   <script type="text/javascript">
        loadNearbyCovidCentresMapmyIndiaDiv(document.getElementById("nearby-covid-places-mapmyindia"));
    </script>
</body>

</html>
```
<br>

### Other Samples for COVID Nearby Places

Read the following [Wiki](https://github.com/MapmyIndia/mapmyindia-nearby-covid-places/wiki/Samples-For-Searching-More-Covid-Categories) article to see more sample of how to search for other types of COVID places using the Nearby Search Widget.
<br><br>

## How to Embed the Widget as an iFrame

The most important thing to remember while embedding this widget in an iFrame is that, an iFrame by default, does NOT allow for geolocation access. This means that the widget won't get the current location of the user of the web page to allow searching for COVID places near his location. 

To overcome this,  please ALWAYS add attribute of allowing geolocation in the iFrame tag as follows: 

### Sample for iFrame embedding of Nearby COVID Places Widget
```html
<iframe width="100%" height="100%" src="https://maps.mapmyindia.com/covid-places/embed?category=HSPVCC" allow="geolocation" >
</iframe>
```
<br>

### Native Webview
<strong>The same URL can also be used for `Native WebView` implmentation of the Nearby COVID Places Widget.</strong>
<br><br>

## Appendix: COVID Places Categories Supported
| Category Code | Description |
| --- | --- |
| [HSPVCC](https://github.com/MapmyIndia/mapmyindia-nearby-covid-places/wiki/Samples-For-Searching-More-Covid-Categories#sample-search-for-corona-vaccination-centres) | Corona Vaccination Centres |
| [HSPTST](https://github.com/MapmyIndia/mapmyindia-nearby-covid-places/wiki/Samples-For-Searching-More-Covid-Categories#sample-search-for-corona-testing-centres) | Corona Testing Centres |
| [HSPTMT](https://github.com/MapmyIndia/mapmyindia-nearby-covid-places/wiki/Samples-For-Searching-More-Covid-Categories#sample-search-for-corona-treatment-centres) | Corona Treatment Centres |
| [HSPCOV](https://github.com/MapmyIndia/mapmyindia-nearby-covid-places/wiki/Samples-For-Searching-More-Covid-Categories#sample-search-for-corona-quarantine-centres) | Corona Quarantine Centre |
| [HSPSCC](https://github.com/MapmyIndia/mapmyindia-nearby-covid-places/wiki/Samples-For-Searching-More-Covid-Categories#sample-search-for-corona-sample-collection-centres) | Corona Sample Collection Centre |
| [CNTZON](https://github.com/MapmyIndia/mapmyindia-nearby-covid-places/wiki/Samples-For-Searching-More-Covid-Categories#sample-search-for-corona-micro-containment-zones) | Corona Micro Containment Zones |

<br></br>
For any queries and support, please contact: 

[<img src="https://www.mapmyindia.com/images/logo.png" height="50"/> </p>](https://www.mapmyindia.com/api)
Email us at [apisupport@mapmyindia.com](mailto:apisupport@mapmyindia.com)


![](https://www.mapmyindia.com/api/img/icons/support.png)
[Support](https://www.mapmyindia.com/api/index.php#f_cont)
Need support? contact us!

<br></br>
<br></br>

[<p align="center"> <img src="https://www.mapmyindia.com/api/img/icons/stack-overflow.png"/> ](https://stackoverflow.com/questions/tagged/mapmyindia-api)[![](https://www.mapmyindia.com/api/img/icons/blog.png)](http://www.mapmyindia.com/blog/)[![](https://www.mapmyindia.com/api/img/icons/gethub.png)](https://github.com/MapmyIndia)[<img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/npm-logo.one-third%5B1%5D.png" height="40"/> </p>](https://www.npmjs.com/org/mapmyindia) 



[<p align="center"> <img src="https://www.mapmyindia.com/june-newsletter/icon4.png"/> ](https://www.facebook.com/MapmyIndia)[![](https://www.mapmyindia.com/june-newsletter/icon2.png)](https://twitter.com/MapmyIndia)[![](https://www.mapmyindia.com/newsletter/2017/aug/llinkedin.png)](https://www.linkedin.com/company/mapmyindia)[![](https://www.mapmyindia.com/june-newsletter/icon3.png)](https://www.youtube.com/user/MapmyIndia/)




<div align="center">@ Copyright 2021 CE Info Systems Pvt. Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://www.mapmyindia.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://www.mapmyindia.com/about/privacy-policy">Privacy Policy</a> | <a href="https://www.mapmyindia.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://www.mapmyindia.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://www.mapmyindia.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>
