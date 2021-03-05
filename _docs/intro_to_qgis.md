---
title: Introduction to QGIS
description: An introductory course to using QGIS software for those new to GIS but familiar with data analysis.
---

# Introduction to QGIS

## Course Summary

### Introduction
This course will provide an introduction to QGIS for non-geographic analysts who are starting to use geospatial techniques and mapping.

### Estimated time for course
3 hours

### Audience
Those beginning to undertake analytical work which brings together geography and statistics.

### Pre-requisites 
Knowledge of the content presented in _Introduction to Geography and Statistics for Analysts_.

---

## QGIS Basics
This first module will cover the basics of using QGIS: including  basic ui elements, project setup, loading data, and some basic functionality.

### Loading QGIS
Before loading QGIS, please check your version number. This tutorial will use QGIS 3.10. 

Upon opening QGIS, you should be met with a screen similar to that below.

![A blank, unsaved project after opening QGIS](https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/untitled_startup.JPG?raw=TRUE)

### UI elements

#### Menus
At the top of the QGIS window are a number of menus. Clicking on one will reveal a further dropdown menu. Some of these dropdown elements also have their own dropdowns etc. For example, expanding `View` reveals a number of options to customise the current view and UI, and some of these options have further options signified by an arrow.

#### Toolbars and Panels
Toolbars are collections of easy-access functions, grouped under a parent family of functions. The toolbars appear as the rows of icons below the menus. These toolbars can be moved around by dragging on the three vertical dots to their left. Hovering the cursor over an icon will display a tooltip with the name of the tool and any keyboard shortcuts for it.

![Toolbars](https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/toolbars.JPG?raw=true)

The following table summarises some of the most useful buttons in these toolbars:

<table style="width 75%" align="center">
  <tr align="center">
    <th>Icon</th>
    <th>Description</th>
  </tr>
  <tr align="center">
    <td><img src="new_open_save_projects.JPG?raw=TRUE" title="Icons for New Project, Open Project, and Save Project"></td>
    <td>`New Project`, `Open Project`, and `Save Project`</td>
  </tr>
  <tr align="center">
    <td><img src="pan_buttons.JPG?raw=TRUE" title="Pan and Pan to Selection buttons"></td>
    <td>`Pan Map` and `Pan to Selection`. `Pan to Selection` will centre the map view on the selected feature(s)</td>
  </tr>
  <tr align="center">
    <td><img src="zoom_butons.JPG?raw=TRUE" title="Zoom buttons"></td>
    <td><p>`Zoom In` and `Zoom Out` will zoom either a fixed amount on click or to an extem from click+drag.</p> 
      <p>`Zoom Full` will zoom to the maximum exten from all layers.</p>
      <p>`Zoom to Selection` and `Zoom to Layer` will zoom to the extent of the selected feature or selected layer, respectively.</p></td>
  </tr>
  <tr align="center">
    <td><img src="identify_features_button.JPG?raw=TRUE" title="Identify features button"></td>
    <td>`Identify Features`. Clicking on a feature with this tool will open the 'Identify Results' panel, displaying attribute information for the highlighted feature.</td>
  </tr>
  <tr align="center">
    <td><img src="select_features_buttons.JPG?raw=TRUE" title="Select Features buttons"></td>
    <td><p>`Select Feature by area or Single Click` will allow the selection of features by either clicking on one feature or doing a click+drag to select multiple. `ctrl+left click` can also be used to click select multiple features at once.</p>
      <p>`Select Features by Value` will open a new dialogue to select features based on value sof the attribute table (see: 'Selecting Features').</p></td>
  </tr>
  <tr align="center">
    <td><img src="attribute_table_button.JPG?raw=TRUE" title="Open Attribute Table Button"></td>
    <td>`Open Attribute Table` for the selected layer.</td>
  </tr>
  <tr align="center">
    <td><img src="field_calculator_button.JPG?raw=TRUE" title="Field Calculator button"></td>
    <td>`Open Field Calculato`r for the selected layer (see: 'Field Calculator').</td>
  </tr>
  <tr align="center">
    <td><img src="measure_button.jpg" title="Measure button"></td>
    <td><p>By default this will be `Measure Line` to measure the distance between two points in the map view. The arrow next to the icon opens a dropdown menu. Using this tool will open a window to display the measurements, where units can be chosen.</p>
      <p>`Measure Area` allows the placing of multiple points to calculate an internal area. Right clicking will complete the area.</p>
      <p>`Measure Angle` two clicks on the map will draw a line. The angle displayed will be between this line and the line from the last point to th the cursor.</p></td>
  </tr>
</table>  

The buttons on the toolbar can be chosen by by going to `View > TOolbars` and toggling options. For this course, make sure `Project Toolbar`, `Navigation Toolbar`, and `Attributes Toolbar` are enabled.

Not all of these buttons are used often, whereas some will be used in every project. Try clicking on each available toolbar button to see what it opens and familiarise yourself with their names.

Panels are parts of the UI which organise a variety of features into larger groups. These features often directly interface with any maps displayed.
<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/panels.JPG?raw=TRUE" />
</p>

Before we begin any work, it's a good idea to set up the UI such that everything need will be easily accessed. For now, we will add an additional panel for quick access to all QGIS functions. 

To do this, go to `View > Panels` and check `Processing Toolbox`. You should now have a panel on the right side of the screen called 'Processing Toolbox'. This panel contains a list of all tools availible in QGIS and a search bar to find them. This will be the primary method for finding tools in this tutorial, although if a tool an be accessed from the toolbar or menus that method will also be shown. For example, the `Buffer` tool can also be found by going to the menu bar and choosing `Vector > Geoprocessing Tool > Buffer`. This is the same tool as you would get by searching `Buffer` in the processing toolbox. 

### Loading data

Loading data into QGIS is straightforward. The simplest way is to drag and drop any delimted text or spatial files straight into the program, where they can be loaded in as layers. There are some potential nuances, however, in what to do when dropping data in. Before loading any data in make sure it is not in a .zip folder. If it is, unzip it first then load it in.

#### Delimited Data (non-spatial)

Text delimited data (.csv, .txt, .xlsx) can be simply dragged and dropped in. Upon doing so, it will appear in the `Layers` panel. As this data is not in a spatial format (unless converted to one later), it can only be explored by opening the attribute table. Try doing this for 'edinburgh_trees.csv' by either right-clicking and choosing `Open attribute table`, or by using the toolbar. The attribute table looks just like a normal spreadsheet, however it cannot be edited right away (we'll come to editing later).

#### Spatial Data

Different kinds of spatial data format have slightly different ways of loading in.

Shapefiles (.shp) come with a number of auxillary files such as .dbf, .dbx etc. These files do no need to be dropped into QGIS; only the .shp needs to be. However, a shapefile's auxillary files should always be kept with it, so it's usually a good idea to have each set of files in their own folder rather than looseley mixed. We'll now load in the `edinburgh_natn.shp` and `ediburgh_aqma.shp` files into our QGIS project. Drag and drop each shapefile (.shp) into QGIS. These layers will be displayed in both the layers panel AND the main window. We can still see the attribute tables, however, using the same method as for the delimited layer.

A geodatabase (.gdb) and a geopackage (.gpkg) are similar formats. Both are eseentially specialised folders which contain both spatial data and their auxillary information in one place. Dragging and dropping in a geodatabase or geopackage will do one of two things, depending on contents. If there is only a single layer in the file, it will be loaded straight in. Otherwise a dialog will appear asking which layers we would like to import and if we would like them to be grouped together.

### Layers and Feature Types

In QGIS, the `Layers` panel displays the names of all data loaded in the current project. Layers contain features, which are generally one of three things: Tables, basemaps, and geometries.

There are three geometry types most commonly used in GIS: points, lines, and polygons.

Points represent a single location, with X and Y coordinates and potentially some associated data for each point. Points do not have spaital dimension, only position. As such, QGIS will by default display points as circles with a fill colour and outline. This symbol representation of the points will remain at constant size relative to the screen as you zoom in and out.

Lines represent connections between points. A line feature can be a single line with nodes and one beginning or end, but can also branch and have multiple end points. What defines it is the point nodes and connections between them. As the line features is effectiely one dimensional, points will only intersect a line if they lie directly on one another. The symbol representation of the line does not represent the extent of the line, which is one-dimensional and does not have true width.

Polgyons, unlike lines and points, do have two dimensional area. Polygons have a boundary separating the 'inside' from the 'outside'. Polygon features can intersect other polygons, lines, and points anywhere on or within the polygon boundary. The symbology for a polygon is made up of an internal 'fill' and an 'outline' for the boundary.

All of these features can either be made up of a single part or multiple parts. The figure below, for instance, shows how by basing symbology on the values of an attribute we can visually separate the geometries from one another.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/basic_features_classified.JPG?raw=TRUE" />
</p>

### Project Settings

#### Project CRS

Each project uses a 'Coordinate Reference System' (CRS). This essentially determines where the X and Y coordinates are place with respect to a given 'origin'. A CRS will have a name and standard code (EPSG:XXXXX) . For most purposes, the project CRS will either be Uiniversal Transverse Mercator (WGS84, EPSG: 4326), or some kind of National Grid. OSGB British National Grid (EPSG: 27700) is the CRS of choice for projects set in Great Britain. The origin of this coordinate system is located in the southwest of the British Isles. British National Grid is actually a PROJECTED coordinate system, which uses 'Eastings' and 'Northings' instead of Longitude and Latitude.

As these tutorials will use data for Great Britain, we will need to set the Project CRS to British National Grid. To do this go to `Project > Properties > CRS`. Now, in the `Filter` bar search for either 'British National Grid' or '27700' (the EPSG code). Now select the result in the 'Coordinate Reference System' box and press OK. 

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/project_crs_window.JPG?raw=TRUE" />
</p>

The project will now use BNG as the CRS. This means that any spatial data with coordinates defined in BNG will be displayed as intended with spatial relationships between points preserved. Data NOT in BNG will be automatically projected if the original CRS is also defined. If data does not have a CRS already defined, we would have to do that manually.

---

## Basic QGIS Tools

This tutorial will cover the tools needed to complete a basic analysis in QGIS. The data we will use is from Edinburgh City Council. This can be downloaded from [link here]. It has been edited from the original soure [link here] to make it suitable for a basic analysis, and extraneous attributes have been removed.

### Data Tools

These tools apply specifically to non-spatial data. Often, data will not be provided spatially, and it must be manipulated to suit a spatial analysis.

#### Non-spatial Joins

A non-spatial join allows us to connect two tables to each other according to a specified attribute. The most common used, and the one we will use now, is a left-join. Just as on a normal table in any other software, a left-join in QGIS will produce a new table with columns between the two inputs tables mathched by feature (rows).

To perform a non-spatial join, go to the processing toolbox panel and search for `Join attributes by field value`.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/edinburgh/edinburgh_trees_join_attribute_window.JPG?raw=true">
</p>

#### Table to geometry

Data will not always come in a spatial format. Here, we have the locations of trees as a csv file, with columns for the X and Y coordinate. This table can be converted into a point geometry, with all other attributes retained, with the `Extract points from table` tool.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/edinburgh/edinburgh_trees_points_from_table_window.JPG?raw=true">
</p>

### Vector Tools

#### Fix Geometry

#### Buffer

A buffer is one of the simplest and most useful tools. Aa buffer will produce a polygon feature which extends from the input feature to a specified distance. The input feature can be a point, line, or polygon, but the output will always be a polygon. 

To demonstrate on points, we will use the refactored trees layer. A single point is not a good physical representation of a tree, which will have a spread. Say the council wished to calculate an approximate area of tree coverage, they would need to have a polygon representation of the trees. By using the buffer tool, we can do this calculation. Search for `Buffer` in processing toolbox.

Now, set the input layer to your trees point layers. Set `buffer distance` to 10. This will automatically be in metres as that is the standard geographic unit of the project CRS. Run the buffer.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/edinburgh/edinburgh_trees_buffer_window.JPG?raw=TRUE">
</p>

The result is that each point now has a circular polygon drawn around it. The radius of this circle is the buffer distance. However, nearby points overlap but are still separate polygons. This can be useful if each individual point was a unique event we cared about, for example if we wanted to see the predicted radius of pollution from factories and know the area covered for each one individually. However we want to know the total area covered by the trees, and these overlaps will result in double counting. To prevent this, we can use the `Dissolve result` option. Open the buffer window again and use the same options as before but with `Dissolve result` checked. Running it now yields a single polygon with overlapping areas merged into the overall polygon. Opening the attribute table for this new layer there is now a single row, representing a single feature. Using the 'information' tool from the toolbar and clicking on the layer will show some geometric information for this layer including the area in m^2.

#### Clip

Clipping is useful for when we wish to cut down geomtries to within the extent of boundary of another. Zooming out, we can see that there are some tree points which are outside of the neighbourhood boundaries. As we only want to consider those within the boundary, we can clip the trees layer.

Clipping will also work on lines and polygons. If used on those, any portions which extend beyond the overlay layer will be removed, leaving only those inside of it.

#### Dissolve

Dissolving will merge all features of a layer into one, or will merge features based on a specified attribute.  To demonstrate, we will dissolve the Natural Neighbourhoods layer into a single polygon. Select the `Dissolve` tool from either the Processing Toolbox or by using the `Vector > Geoprocessing > Dissolve` menu.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/edinburgh/edinburgh_natn_dissolve_window.JPG?raw=TRUE">
</p>



#### Spatial Joins

Probably one of the most useful spatial operations, and one of the most commonly used. A spatial join acts similarly to a non-spatial join, however it will joinn tables based on their location instead of attributes. A number of options are avalable for a spatial join, how each works can be found here: [insert link]. For our purposes, a simple 'intersect' is all that is necessary. Also, as we are primarily interested in the data linked with the spatial features, we will want to create summaries from the joines. To achieve this, we will use `Join attributes by location (summary)` from the processing toolbox.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/edinburgh/edinburgh_aqma_nn_intersection_window.JPG?raw=TRUE">
</p>

It is also possible to join without summarising. Search and open `Join attributes by location` in the processing toolbox. This time, choose 'edinburgh trees' as the input layer and 'edinburgh_natneighbourhoods' as the join layer. Select 'one to many'. This will now join the attributes of he natural neighbourhoods layer to any intersecting points.

#### Centroids

It is often useful to represent data contained in polygons as individual points which can be joined with other layers or turned into proportial symbol maps. The `Centroid` tool can be used to produce a point which lies at the geometric centre of a polygon.

<p align="center">
  <img src="centroids_window.JPG?raw=TRUE" title="Centroids window">
</p>

Choose the 'natural neighbourhoods' layer

There is a problem with this method, however. Not all polygons willhave simple, convex geometries. Some may be more complex shapes where the geometric centroid is outside of the polygon boundaries. The image below shows an area where some polygons appear to have multiple centroids. Really, there are neighbouring polygons where the centroids do not fall within the geometry. These centroids are therefore not spatially representative of there the natural neighbourhoods actually are. To get around this we can use a different tool to generate centroids: `Point on surface`. This will produce a centroid which strictly falls on the surface of the parent polygon.

<p align="center">
  <img src="pointonsurface_window.JPG?raw=TRUE" title="Point on surface window">
</p>

Running this again for natural neighbourhoods we can see that all polygons have a single point each. The points generated from `Point on surface` will be our centroids layer, so we can remove the geometric centroid layer.

Some spatial datasets have existing centroids available with statistical weighting applied. England and Wales statistical Output Areas have their population-weighted centroids avalable. If a population-weighted centroid dataset exists, this would be the preferred choice over generating them by hand as they are more certain to be good for use in official statistics.

---

## Editing and Saving Data

Now that we have worked with some data using basic geospatial tools, we can do some deeper editing and look at more ways of storing geospatial data.

### Attribute Tables

Spatial data, just like non-spatial data, is built around tables with data. Individual features (e.g. a point, a line segment, or a polygon) are defined by individual rows, and their attributes can be contained in multiple columns, which are also known as `Fields`. This is the same a any non-spatial table e.g. a spreadsheet with the names and addresses of individuals. The difference with spatial data is that there is also a field which holds geometry information which can be read by software or code.

As in a spreadsheet, fields also have a type. The data types possible include integers and floats of varying precision, strings (text), date formats etc. As with non-spatial data, we have to make sure the columns are the right type when creating, editing, or using them for analysis.

<p align="center">
 <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/edinburgh/edinburgh_natn_attributetable.JPG?raw=TRUE">
</p>

#### Refactor Fields

Refactoring fields allows us to change how the software interprets values. Search `Refactor Fields` in the toolbox and open it. If we use the natural trees layer as the input, we can see what type has been assigned to each field. Right now, all fields are of type `String`. This means QGIS will interpret these values as text, including numbers, and will not be able to use them to perform numerical operations. To fix this, we can simply select the drop down menus for the 'TREE_HEIGHT_AV' and 'TREE_SPREAD_AV' fields, and change the type to `Double`.

<p align="center">
 <img src = "https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/save_feature_as_window.JPG?raw=TRUE">
</p>

#### Create Fields

To add edit existing fields or add new fields directly to an attribute table, we must be in 'edit mode' for the currently selected layer. TO do this, click on the 'trees' layer, then from the Vector Toolbar select `Toggle Editing`. We are now in edit mode. Open the attribute table for the trees layer. In the top bar, find the `New Field` button. This will open a dialog box.

Now, we can specify the name of the field and the type of values it can hold. Always try to make sure new fields are named consistently with existing fields. Common naming patterns are CamelType, Snake_Type, and SCREAMING_SNAKE_TYPE. The field type drop down works the same as when refactoring fields.

#### Field Calculator

The field calculator uses SQL-like expressions to perform a range of possible operations on a field. As this is a basics tutorial, we will just use standard numerical operations.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/field_calculator_window.JPG?raw=TRUE")
</p>

### Data Formats

Spatial data comes in specialised formats designed to hold geometry information. The three most common methods of formatting spatial data are Shapefiles, GeoDatabases, and Geopakages. 

Spatial data can, however, also be formatted in standard data formats such us .csv or .txt. These can also retain the geometry column, making them easy to convert back into features, but can also be opened and edited in programs like Notepad and Excel.

#### Exporting data

QGIS contains a single UI for exporting data.

On the trees layers, right-click and then go to `Export > Save feature as...`. From here, we have a few options. The top drop-down is where we choose the output format. There is a large range of formats available depdending on the desired output. 

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/save_feature_as_window.JPG?raw=TRUE")
</p>
  
When saving  to a geopackage (GPKG) or geodatabase (GDB), a layer namer must also be specified. Multiple layers can be saved to the same geopackage or geodatabase. A shapefile only needs the file name.
  
If we want to export the attribute table alone, we can choose the CSV option.

---

## Basic Mapping in QGIS

This section will cover some of the options available for producing basic map visualisations. More specifics on the style of maps covered and best practice for mapping can be found here [LINK]. Once this section is completed you will be able to create a number of maps depending on the types of underlying data and purpose of the visualisation.

### Layer Styling

So far, QGIS has assigned random, default colours to imported and created layers. If we want to make the maps presentable we'll need to edit the style of the layers to highlight the data we are trying to get across.

To edit the layer styles, we will use the `Layer Stylng` panel. If not already, enable this from the menu bar under `View > Panels > Layer Styling`.

<p align="center">
  <img src="https://github.com/ONSgeo/training/blob/main/docs/intro_to_qgis/images/layer_styling_panel.JPG?raw=true"
</p>
  
Layer style can also be edited by rght clicking on a layer, choosing `Properties`, and going to the `Symbology` tab. This can be useful if there is little room on the screen for additional panels, however it can make it harder to see the impact of a new style as you make changes.

So using the layer styling panel, we can start to improve the appearance of our layers.

#### Symbology

Before we look at the different approaches for layer styling, here are some fundamental options which apply to each type.

In the style panel the four most important options are `Fill Colour`, `Fill Style`, `Stroke Colour`, and `Stroke Style`. Setting the style for fill or stroke to `No pen` will result in the fill or stroke not shoring. This is a good way to only show borders on top of other layers.

When working with colours in maps it's very important to be aware of both the aesthetic value of the colours and also how accessible they are. Colour schemes should be equally legible to colourblind and non-colourblind people. <a href="https://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3" target="_blank">ColorBrewer</a> is a useful website which displays palettes based on different criteria, including suitability for colour-blindness.

#### Single Symbol

This is the default style for all layers. With single symbol styling, all features in that layer will have the same appearance e.g. all tree points will be the same size and colour. This can be useful when we want to provide, for example, a background layer to provide some spatial reference.

#### Graduated

Graduated maps use a scale starting from one data value and ending at another. A gradient palette is split up into a specified number of groups and split up across the data range. Graduated styles therefore use colour bins to display the data. For the natural neighbourhoods layer, select the drop down in the layer styling panel which says 'single symbol' and change this to 'graduated'.

We may now specify the number of bins for the data, the palette used, and the method for creating the breaks. There are some best practice measures for choosing each of these.

When choosing the number of bins we must consider both the palette and the values. Monotone or duotone palettes may be difficult to interpret if many classes are used as the difference from one shade to the next may not be very visible e.g. Reds, BlPu. A palette with three or more colours, like Viridis, can potentially show more classes before differences become hard to see. Generally, it's a good idea to use around 5 or 6 classes, but this may need to be increased or decreased slightly depending on the variation in the data.

The breaks methods can help us deal with different distributions in the underlying data and therefore produce more accurate maps. The `Mode` dropdown shows the breaks available in QGIS. As with any other visualisation, the optimal mode will depend on how the data is distributed. Generally only two methods will be needed; data spaced evenly across a range will work best with quantiles, but data which has clusters or outliers will be best shown using Natural Breaks (Jenks).

When applied to a polygon, a graduated map is called a 'Choropleth'. To show what this looks like for the natural neighbourhoods layer, we will set the value for a graduated map to 'TREE_HEIGHT_AV_COUNT'. Change the mode to `Natural Breaks (Jenks)` and press `Classify`. By default this will creat 5 bins. Try out different colour ramps and see which look good with the selected data while also being colour-blind friendly. You could also try adjusting the number of classes to see how this changes the map, and also what different break types do.

There is a problem with this type of choropleth. We're visualising the count of trees in a given area. This can be deceptive as larger areas, as a general rule, will have a higher count of trees simply because they can contain more. To conteract this the data for a choropleth should always be normalised. This is usually done in two ways: creating a summary statistic, or normalising by area or per X count of a value e.g.trees/km^2 or trees per 1,000 population. We have already created summary statistcs and calculated the density of trees per km^2. Try changing the values between 'TREES_HEIGH_AV_MEAN" and "TREES_DENSITY_KM2" to see how this changes the appearance of the layer. The latter should result in the larger aras now being grouped into the lower values, while we can see that tree densities are actually much higher in the smaller, more central neighbourhoods.

#### Categorised

Categorised maps are similar to graduated maps except the bins are based on unique values rather than a contunuous range. Categorical maps can be messy if too many unique values are present, so it's usally a good ida to keep the number of categrories to the minimum possible. 

### Print Layouts

Layer styling is the first step in producing map visualisations. To expand on the amount of information a map can present in a single image we must create a 'print layout'. To make a new print layout, go to `Project > New Print Layout` or use `ctrl+p`. Choose a suitable name for the layout e.g. 'Edinburgh Tree Map'.

#### Layout UI

The print layout will open in a new window with a different set of toolbars and panels to the main QGIS window.

<p>
  <img src="print_layout_window.JPG?raw=TRUE" title="Print Layout window">
</p>

The right panels show the active 'items' in the layout, and properties/options for the currently selected item. In the layout items are map views, text, legends etc. On the left is the Toolbox toolbar. The main tools we will use from this toolbar are:

<table style="width 75%" align="center">
  <tr>
    <th>Icon</th>
    <th>Description</th>
  </tr>
  <tr align="center">
    <td><img src="layout_panzoom_buttons.JPG?raw=TRUE" title="Layout pan and zoom buttons"></td>
    <td>Pan and zoom. These apply to the layout view iself not map views</td>
  </tr>
  <tr align="center">
    <td><img src="layout_selectmoveitem_button.JPG?raw=TRUE" title="Layout select/move items button"></td>
    <td>Select/move items. Selecting an item will make it the active item in the properties panel.</td>
  </tr>
  <tr align="center">
    <td><img src="layout_moveitemcontent_button.JPG?raw=TRUE" title="Layout move item content"></td>
    <td>Move item content. This will move the internal content of the selected map view item in the same way as panning and scrolling works in project view.</td>
  </tr>
  <tr align="center">
    <td><img src="layout_addmapview_button.JPG?raw=TRUE" title="Layout add map view"></td>
    <td><p>Add map view. A map view is a essentially a link to the main project window and will render active layers from there.</p>
      <p>The map can be panned and zoomed in on while `Move Item Content ` is enabled.</p></td>
  </tr>
  <tr align="center">
    <td><img src="layout_addlabel_button.JPG?raw=TRUE" title="Layout add label"></td>
    <td>Adds a text box to the layout. The text can be moved with `Select/Move Items` and formatted in the item properties panel.</td>
  </tr>
  <tr align="center">
    <td><img src="layout_addlegend_button.JPG?raw=TRUE" title="Layout add legend"></td>
    <td><p>Adds a legend. The legend is linked to the layers available in the project.</p>
    <p>Items in the legend can be customised in the item properties panel, including what items are included, their order, and formatting.</p></td>
  </tr>
  <tr align="center">
    <td><img src="layout_addscalebarnortharrow.JPG?raw=TRUE" title="Layout add legend"></td>
    <td><p>The first tool adds a scalebar to the layout. This is linked to the zoom scale of a selected map view. Scale bars are primarily useful when aiming to show the distance between data or in contexts where the scale of the map is otherwise unintuitive.</p>
    <p>The second tool adds a north arrow/compass rose. This is rarely needed, usually only for specific scales or boundaries where the the top of the map is not North, the target audience of the visualisation may be unaware of the geography's orientation, or where the map describes some phenomenon related to compass bearing.</p></td>
  </tr>
</table>

#### Adding maps

To add a map to the layout we use the `Add map view` tool from the previous table. With this tool selected, click and drag in the white area to draw the bondary of the view. This view will now display the same map that we can see in the project view. In fact, this map view and the project are linked such that changing layer styles and active layers in the project will change the view in layout. 

<p align="center">
  <img src="layout_mapview.JPG?raw=TRUE" title="Layout map view item.">
</p>

#### Customising Maps

#### Legends & Extras

#### Text

While 'a picture says a thousand words', the context of a map is usually impossible to discern without some text to describe it. Using the label tool we'll add a descriptive title to the map. With the tool selected, click and drag to create a text box. This will contain a 'Lorem ipsum' placeholder by default. 

The properties of the text can be customised in the Item Properties panel. Try experimenting with some of the options under`

#### Exporting Maps

<p align="center">
  <img src="edinburgh_natn_treedensity_choropleth.JPG?raw=TRUE" title="Final output map: Choropleth showing density of trees in Edinburgh Natural Neighbourhoods">
</p>