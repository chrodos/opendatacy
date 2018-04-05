# opendatacy Upgrade changes

Changes after upgrade:

## Changes to template
Add the two files for the page templates to this folder and overwrite the others.

opendata2/profiles/dkan/themes/nuboot_radix/templates/page


## Fix flags

Add this to opendata2/modules/locale/locale.css

.language-switcher-locale-session{
  list-style: none;
}

.language-switcher-locale-session li {
                display: inline;
        }
## Fix the empty space at the bottom of the boxes (e.g., application)

Edit file opendata2/profiles/dkan/themes/nuboot_radix/assets/css/nuboot_radix.style.css:10315
Change it to margin-bottom: 0em;
