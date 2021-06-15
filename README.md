# Choropleth-Mapping-UK-python-
Geographical mapping in python using UK GeoJSON files


A couple of examples on how to plot choropleth maps for UK in python using plotly express.

To create these choropleth maps you need two things, 
firstly a GeoJSON file - this is a nested dictionary, which consists of propeties and coordinates
of its features (i.e. the map space)

secondly you need data which you would like to map, and this needs to have an identifier
to match on to the required feature in the map file.

You can find GeoJSON files online, but for UK maps the Office of National Statistics ONS
contains a geographical portal which has many useful maps which can be found 
under the APIs drop down

A few examples:

UK Counties:
https://geoportal.statistics.gov.uk/datasets/counties-december-2019-boundaries-en-bfc

UK Countries:
https://geoportal.statistics.gov.uk/datasets/countries-december-2019-gb-bgc/data?geometry=-38.338%2C48.768%2C31.052%2C57.907

UK Districts:
https://geoportal.statistics.gov.uk/datasets/local-authority-districts-may-2020-boundaries-uk-bgc-1

UK National parks:
https://geoportal.statistics.gov.uk/datasets/national-parks-december-2019-gb-bfc

For my two examples I will do one for UK Countries (using a dummy data frame) and 
one for UK Districts (using real data which I found on GovUK on population statistics)

I have set these to be basic design however, you can find online easily how
to use color, hover and style options.



Note ** I have used other GeoJSON files (not on ONS) and was able to use
function choropleth on plotly express, however when using ONS files, I found that this would
not work, suggesting to me a possible bug in the library, so instead I use choropleth_mapbox
which is similar.

-----------------------------------------------------------------------------------------------
Start to end video on interactive mapping here: https://youtu.be/6gqHiSFD7yI
