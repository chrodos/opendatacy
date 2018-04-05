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
