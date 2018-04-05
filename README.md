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

