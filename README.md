# rti-viewer_cb-add-on

CollectionBuilder-CSV Add-on: RTI item viewer 

This repository provides template files to add an RTI viewer option into a [CollectionBuilder-CSV](https://github.com/CollectionBuilder/collectionbuilder-csv) project.
The files in this directory structure can be copied directly into a CB-CSV repository to add the new features.

*note: only compatible with CB-CSV out of the box, not other templates*

## RTI 

Reflectance Transformation Imaging (RTI) is an imaging technique used to reveal surface characteristics of 3d objects. 
RTI viewers allow users to change lighting angles and characteristics to explore the surface features and details. 
Learn more at [Cultural Heritage Imaging RTI](https://culturalheritageimaging.org/Technologies/RTI/).

This add-on uses [Relight](https://vcg.isti.cnr.it/relight/) and [OpenLIME](https://github.com/cnr-isti-vclab/openlime) to allow displaying RTI items directly in your CollectionBuilder digital collection. 

For displaying on the web, RTI captures must be pre-processed into a series of jpg images, using the [Relight tool](https://vcg.isti.cnr.it/relight/).
Relight software can convert an existing ".rti" or folder of images into Relight web format. 
Download the software from their [releases page](https://github.com/cnr-isti-vclab/relight/releases), and use the [CHI introduction video](https://vimeo.com/752733616) to learn how to use it, specifically to export to Relight format (around 13:01). 
(Relight documentation seems to be a work in progress!)

## How To Use

Add to CB-CSV project: 

- Start a [CollectionBuilder-CSV](https://github.com/CollectionBuilder/collectionbuilder-csv) project
- Download this add-on to your computer (click "Code" > "Download ZIP", then unzip package)
- Copy all content in the add-on (all files and folders *except the README.md*) and paste into your existing CollectionBuilder-CSV project. The folder structure in this add-on should match up with your CB-CSV template, adding new files in the correct places (do not delete or overwrite anything in your existing CB project!). 

Add your RTI items: 

- RTI items in Relight format will be a folder containing a "info.json" file and a series of ".jpg" images. Name the folder following the conventions of your item's objectid. Copy the folder (and all contents) into your CB project's "objects" folder (or other web accessible location). 
- In the "object_location" field of your metadata, provide a relative path or full url to the RTI folder (e.g. `/objects/rti-ex-01` or `https://example.com/items/rti-ex-02`).
- In the "display_template" field use the option `rti_viewer`
- Optionally, manually create a thumbnail image for the item. Put the image in your "objects" folder and reference in "image_thumb" and "image_small" fields. 
