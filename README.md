# opendatacy Upgrade changes

Changes after upgrade:

## Changes to template
Add the two files for the page templates to this folder and overwrite the others.

opendata2/profiles/dkan/themes/nuboot_radix/templates/page


## Fix flags

Add this to opendata2/modules/locale/locale.css
```css
.language-switcher-locale-session{
  list-style: none;
}

.language-switcher-locale-session li {
  display: inline;
}
 ```
## Fix the empty space at the bottom of the boxes (e.g., application)

Edit file opendata2/profiles/dkan/themes/nuboot_radix/assets/css/nuboot_radix.style.css:10315
Change it to margin-bottom: 0em;

## Add the new Licences
Replace the function dkan_dataset_content_types_license_subscribe() in file opendata2_old/profiles/dkan/modules/dkan/dkan_dataset/modules/dkan_dataset_content_types/dkan_dataset_content_types.license_field.inc

```php
function dkan_dataset_content_types_license_subscribe() {
  return array(
    "cc-by" => array(
      "label" => "Creative Commons Attribution 4.0 International (CC BY 4.0)",
      "uri" => "https://creativecommons.org/licenses/by/4.0/",
    ),
    "cc-by-sa" => array(
      "label" => "Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)",
      "uri" => "https://creativecommons.org/licenses/by-sa/4.0/",
    ),
    "cc-nc"  => array(
      "label" => "Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)",
      "uri" => "http://opendefinition.org/licenses/cc-nc/",
    ),
    "notspecified" => array(
      "label" => "License Not Specified",
    ),
  );
}
```
## Change the layer of the maps to hide turkish names in occupied Cyprus

File: opendata2/profiles/dkan/modules/dkan/dkan_sitewide/dkan_sitewide.blocks.inc
Line: 171
```javascript
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
```
TO
```javascript
L.tileLayer('https://stamen-tiles-{s}.a.ssl.fastly.net/terrain/{z}/{x}/{y}.png', {
```

## Color of the file format in datasets
Edit file:opendata2/profiles/dkan/modules/dkan/dkan_dataset/css/dkan_dataset.css

```css
.label[data-format=HTML],
.label[data-format=html],
.label[data-format*=html] {
  background-color: #55a1ce;
}
.label[data-format=jpeg],
.label[data-format=jpg] {
  background-color: blue;
}
.label[data-format=json],
.label[data-format*=json] {
  background-color: #ef7100;
}
.label[data-format=xml],
.label[data-format*=xml] {
  background-color: #ef7100;
}
.label[data-format=text],
.label[data-format*=text] {
  background-color: #74cbec;
}
.label[data-format=csv],
.label[data-format*=csv] {
  background-color:  #27d1b4 
}
.label[data-format=xls],
.label[data-format*=xls] {
  background-color: #2db55d;
}
.label[data-format=zip],
.label[data-format*=zip] {
  background-color: #686868;
}
.label[data-format=api],
.label[data-format*=api] {
  background-color: #ec96be;
}
.label[data-format=pdf],
.label[data-format*=pdf] {
  background-color: #e0051e;
}
.label[data-format=rdf],
.label[data-format*=rdf],
.label[data-format*=nquad],
.label[data-format*=ntriples],
.label[data-format*=turtle] {
  background-color: #0b4498;
}
.label[data-format=data],
.label[data-format*=data] {
  background-color: olive;
}
.label[data-format=txt],
.label[data-format*=txt] {
  background-color: #70c6e5;
}
.label[data-format=tsv],
.label[data-format*=tsv] {
  background-color: #6f5191;
}
.label[data-format=dwg],
.label[data-format*=dwg] {
  background-color:  #4dd127;
}
.label[data-format=SOAP],
.label[data-format*=SOAP] {
  background-color:  #699cf5 ;
}
.label[data-format=esri],
.label[data-format*=esri] {
  background-color:  #b810f7  ;
}
.label[data-format=kml],
.label[data-format*=kml] {
  background-color:  #f71061;
}
.label[data-format=kmz],
.label[data-format*=kmz] {
  background-color:  #cc1152 ;
}
.label[data-format=wms],
.label[data-format*=wms] {
  background-color:   #2c2a2b ;
}
.label[data-format=raster],
.label[data-format*=raster] {
  background-color:   #FA0FCB ;
}
.label[data-format=shp],
.label[data-format*=shp] {
  background-color:   #FA710F ;
}
.label[data-format=doc],
.label[data-format*=doc] {
  background-color:   #186399;
}
```

