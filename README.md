# Conky-Matic
change colors automatically when wallpaper changes.
When you run ConkyMatic it does the following:

    Automatically gets the path to your current wallpaper (or the path can be passed manually).

    Creates a 16 color palette image from the current wallpaper (look at the bottom of the Conky in the screenshots)

    Extracts the hex color value of each of the 16 images in the color palette.

    Generates a .conkyrc file using colors randomly selected from that palette.

    Copies the new .conkyrc file to the home folder and relaunches the Conky application.

The entire sequence takes the script about 10 seconds, making it very fast and easy to build a fresh conky every time you change your wallpaper. And since the colors are randomly selected (with some logic), running the script multiple times with the same wallpaper will yield different results.

Note: The automatic path gathering feature only works if you use Variety to set your wallpaper.

Requirements

    A Linux installation with Conky installed.

    ImageMagick to generate the color palette PNG and weather icons. Note: If you have Inkscape is installed, ConkyMatic will use it for the weather icon rendering since it has better SVG handling. However, ImageMagick is still necessary for the palette generation.

    Curl to download JSON weather data.

    jq to parse JSON weather data.

    Roboto Font. The default Conky template uses Roboto.

Usage

Point your terminal to the directory containing cokymatic and run it using:

$   ./conkymatic_2.sh

You can also manually pass the path to your wallpaper as an argument:

$   ./conkymatic_2.sh /path/to/your/wallpaper.jpg

Important: Before running ConkyMatic make a backup copy of your .conkyrc file since it will get overwritten.


Customization

In the Templates directory you'll find the default.conky template. This is a normal .conkyrc file, except it contains some pseudo-variables that get replaced by the script with random color values. A list of available variables can be found below.

Additional templates can be created and added to the Templates folder. If more than one template is in the folder, when you run the conkymatic_2.sh script via your terminal you'll be given a choice of templates. Hitting ENTER in the terminal will auto-select the template named default.conky, or you can type the name of the one you prefer to run.

IMPORTANT: all templates must be named with the .conky file extension: Example: foobar.conky


Template Variables

The template variables are just text placeholders which get replaced when the script gets run. The following variables are available for use. The colors will be assigned automatically from your wallpaper colors.

_VAR:COLOR_TIME_
_VAR:COLOR_DATE_
_VAR:COLOR_WEATHER_
_VAR:COLOR_HEADING_
_VAR:COLOR_SUBHEADING_
_VAR:COLOR_TEXT_
_VAR:COLOR_DATA_
_VAR:COLOR_HR_
_VAR:COLOR_BARS_NORM_
_VAR:COLOR_BARS_WARN_
_VAR:COLOR_BORDER_
_VAR:COLOR_BACKGROUND_


Credit : https://github.com/rickellis/ConkyMatic
