#Import Statements

import plotly.express as px
import pandas as pd
from urllib.request import urlopen
import json

with urlopen('https://opendata.arcgis.com/datasets/ee3bb6a5a73540beab9837154fd9aa9a_0.geojson') as response:
    uk_countries=json.load(response)
    

#Have a play around looking at the GeoJSON file to understand its construtcion

#uk_countries
#uk_countries['features'][0]
#uk_countries['features'][1]['properties']


dummydata = pd.DataFrame((['Wales', 8],
                         ['Scotland', 6],
                         ['England', 4],
                         ['Northern Ireland',2],),
                        columns='Country Value'.split())
 
 
 
#I have set this up such that my Country column, matches what is
#seen in uk_countries['features'][i]['properties'] as the key 'ctry19nmw'

#However if I didn't have this I would need to add on a column which matches on to a property of the GeoJSON
#So I will also add on the 'objectid' property to my data set

area={}
for feature in uk_countries['features']:
    feature['id']=feature['properties']['objectid']
    area[feature['properties']['ctry19nm']]=feature['id']

dummydata['id']=dummydata['Country'].apply(lambda x: area[x])

fig = px.choropleth_mapbox(dummydata, locations="id", featureidkey='properties.objectid', geojson=uk_countries, color='Value', hover_name='Country', mapbox_style='white-bg', zoom=4, center = {"lat": 55, "lon": 0})
fig.show()

#This could also be achieved with locations="Country", featureidkey="properties.ctry19nm"
