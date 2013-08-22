
# Data integration with Google Maps

Looking for what data fields can be easily added to a Map view. These
are some URLs I found helpful exploring the subject.

* [Info Windows](https://developers.google.com/maps/documentation/javascript/overlays#InfoWindows)
* [Layers](https://developers.google.com/maps/documentation/javascript/layers)
* [KLM support in Google Maps](https://developers.google.com/kml/documentation/mapsSupport)
* [Fusion Tables and Maps example](https://developers.google.com/maps/documentation/javascript/examples/layer-fusiontables-simple)
* [Fusion Tables/Maps docs](https://developers.google.com/maps/documentation/javascript/layers#FusionTables)

## three options for including extra data

HTML embeded into "Info Windows", KLM with HTML data embedded to produce
an "overlay" and finally you can integrate with Google's fusion tables. The
fusion table integrations offers the the most expersive output if you're already
planning to use Google Fusion tables.

The limitation of the HTML embedded in an "Info Window" is one of amount.  Overflowing
the window can cause usual results.  If there are allot of feeds needed to 
be displayed then you probably want to display that on a standard HTML page
and embed the Map view with in it. In that case you could use Markers as links.
This is effectively what Google itself does with things like drive/walking
directions. 


## KLM

KLM is a standards based Geodata file format and one used by Google Maps
to include additional information to "overlay" on the map.  It includes
an data section that can contain HTML markup (also see KmlFeatureData example
in KML support link above).

## Fusion tables and Maps integration

[Google's Fusion tables](https://developers.google.com/fusiontables/) can be 
integrated with [Google Maps](https://developers.google.com/maps/documentation/javascript/layers#FusionTables)
This appears to provide the most possibility for data analysis and interesting
visualizations if you've already stored your data (or a copy of it) in Fusion 
tables.

### Limits

You can use the Maps API to add up to five Fusion Tables layers to a map, one of which can be styled with up to five styling rules.

#### In addition:

* Only the first 100,000 rows of data in a table are mapped or included in query results.
* Queries with spatial predicates only return data from within this first 100,000 rows. Therefore, if you apply a filter to a very large table and the filter matches data in rows after the first 100K, these rows are not displayed.
* When importing or inserting data, remember:
	* The total size of the data sent in one API call cannot exceed 1MB.
	* A cell of data in Fusion Tables supports a maximum of 1 million characters; it may sometimes be necessary to reduce the precision of coordinates or simplify polygon or line descriptions.
	* The maximum number of vertices supported per table is 5 million.
* When looking at the map, you may notice:
	* The ten largest-area components of a multi-geometry are shown.
	* When zoomed farther out, tables with more than 500 features will show dots (not lines or polygons).

