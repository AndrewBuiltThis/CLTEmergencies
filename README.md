# Live Weather Dashboard

### Doesn't it suck that whenever there's a weather emergency bearing down on your City, someone asks you to drop everything and make them a one-time app to monitor the storm? I certainly thought so. 

### So I did something about it.

This application was built to provide real-time, continous support for weather emergencies in the Charlotte-Mecklenburg Region in North Carolina. This isn't a one-and-done application, but rather a web dashboard that leverages the awesome live data that is acessible via web APIS. In other words, you can leave this app up-and-running indefinetely and always have accurate, up-to-date and easily accessable information. Pretty neat, huh?

# Here's How It Works

The web-application has a few moving parts that were kept in isolation so that folks can easily modify and deploy this application for their area. The application uses:
* The Esri JS API (4.8);
* The Weather.gov API provided by the U.S. National Weather Center;
* The USGS's RESTful GIS Endpoint;
* The composite outage-tracker Poweroutage.us; 
* The City of Charlotte's RESTful GIS Endpoint; and
* The Bootstrap 4.X framework

## How To Make it Work For You

Always 'Me! Me! Me!' from you lot... but I digress.

Here are the moving parts you need to update in order to deploy this application yourself:
1. Review Esri's Service for leveraging their API which can be found [here](https://developers.arcgis.com/javascript/latest/guide/licensing/index.html)
2. Open the index.html document and make the following modifications (where appropriate)
⋅⋅1. Change the <meta> tags in the html header. If this will be public facing, having proper SEO is important. However, remember to give yours truely credit :)
⋅⋅2. Change the Navigation Bar links where appropriate (unless you really want people to check out the Charlotte Airport)
⋅⋅3. Change the Social Media links (twitter, instagram and social-searcher). If you go to those links, you'll see they're returning info for Charlotte. Change the search terms and then copy the URL and put it in the href attribute.
⋅⋅4. Modify the bottom cards (those are the floating box thingys) with the appropriate content.
⋅⋅5. In the Time Lapse Radar card, check out the URL. notice that right after 'html?' we see 'lat=35.200&amp;lon=-80.829'? Those are UURL the URL-encoded latitude and longitude values for Charlotte. If you change the values, you'll go to a different area.
⋅⋅6. Toward the bottom of the document, you'll see a bunch of scripts. These were kept separate for simplicity's sake. There's a script that calls to https://api.weather.gov/alerts/active/zone/NCZ071. Notice the end of the URL is NCZ071. This is Charlotte's zone classification. Find your classification on the Weather.gov site and replace that fella.
⋅⋅7. Right below that reference is a call to https://api.weather.gov/gridpoints/GSP/118,64/forecast. This is getting the current weather conditions. You'll need to review the api.weather.gov's documentaion to find the appropriate grid-point for your region then replace the URL.
⋅⋅8. In the next script, you'll see a call to https://poweroutage.us/area/county/493. That is Mecklenburg County, NC. Use the site to find your county and then replace the URL appropriately! 
⋅⋅9. The last changes are all to the web-map being displayed in the dashboard which begins (as of now) around line 413. The first thing to change is the URL that currently points to https://waterservices.usgs.gov/nwis/iv/?countyCd=37119... The USGS has a different set of County Codes (CountyCd in the URL). Find yours on their site and replace that value (but keep the rest of the URL!).
⋅⋅10. You may want to remove the streetClosures layer from the map, as that layer is specific to Charlotte. However, it won't hurt you to keep it there -- might just slow ya down. It also serves a great template if you want to use your own REST services!

And you should be good to go! 

Feel free to reach out for help or question!

Cheers,
A
