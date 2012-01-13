## cinnamon-extension-weather

cinnamon-extension-weather was ported from [gnome-shell-extension-weather](https://github.com/simon04/gnome-shell-extension-weather) to work in [Cinnamon](http://cinnamon.linuxmint.com/).
It is a simple extension for displaying weather notifications in Cinnamon.

Currently, the weather report including forecast for today and tomorrow is fetched from [Yahoo! Weather](http://weather.yahoo.com/).

----

### Screenshots

![Screenshot](https://github.com/merlwiz79/cinnamon-extension-weather/raw/master/data/screenshot.png)

----

### Installation

* [Ubuntu](https://launchpad.net/~merlwiz79/+archive/cinnamon-ppa)
* Generic: For a generic installation, run the following commands:
  `./autogen.sh --prefix=/usr && make && sudo make install`
  * Make sure you have the `libglib2.0-dev` package (or equivalent for your distribution)
    installed, or else you'll get an error about `GLIB_GSETTINGS`.
* *Please report further links!*

That's it!

----

### Configuration

cinnamon-extension-weather uses gsettings to save your configuration. You can use `dconf-editor` or `gsettings` from the command line to modify some parameters.

#### Location

At the moment, only WOEIDs consisting of 4 uppercase letters followed by 4 digits are supported. Determine your WOEID using [edg3.co.uk](http://edg3.co.uk/snippets/weather-location-codes/) or [xoap.weather.com](http://xoap.weather.com/search/search?where=Innsbruck).

You can specify your location using the following command. Perhaps you need quotation marks as in the second command.

    gsettings set org.cinnamon.extensions.weather woeid your_woeid
    gsettings set org.cinnamon.extensions.weather woeid "'your_woeid'"

#### Temperature Units (optional, Celsius by default)

You can modify the temperature unit using one of the following commands:

    gsettings set org.cinnamon.extensions.weather unit celsius
    gsettings set org.cinnamon.extensions.weather unit fahrenheit

#### Displayed Location (optional)

Sometimes your WOEID location isn't quite right (it's the next major city around). To customize the displayed city you can type:

    gsettings set org.cinnamon.extensions.weather city your_city

#### Translate Weather Conditions (optional, true by default)

You may want to configure whether to translate the weather condition. If enabled, the condition is translated based on the weather code. If disabled, the condition string from Yahoo is taken. Note: Enabling the translation sometimes results in loss of accuracy, e.g., the condition string "PM Thunderstorms" cannot be expressed in terms of weather codes.

    gsettings set org.cinnamon.extensions.weather translate-condition true
    gsettings set org.cinnamon.extensions.weather translate-condition false

#### Use Symbolic Icons (optional, false by default)

If desired, you can enable the usage of symbolic icons to display the weather condition (instead of full-colored icons).

    gsettings set org.cinnamon.extensions.weather use-symbolic-icons false
    gsettings set org.cinnamon.extensions.weather use-symbolic-icons true

#### Show Text in Panel (optional, true by default)

You can configure whether to show the weather condition text (aka. comment) together with the temperature in the panel (requires restart). If only weather condition text is undesired, consider show-comment-in-panel option.

    gsettings set org.cinnamon.extensions.weather show-text-in-panel true
    gsettings set org.cinnamon.extensions.weather show-text-in-panel false

#### Show Comment in Panel (optional, false by default)

Configures whether to show the comment (aka. weather condition text, e.g. "Windy", "Clear") in the panel. Note that the temperature is still shown (if undesired, consider show-text-in-panel option).

    gsettings set org.cinnamon.extensions.weather show-comment-in-panel false
    gsettings set org.cinnamon.extensions.weather show-comment-in-panel true

#### Position in Panel (optional, center by default)

The position of this Cinnamon extension in the panel can be configured to either 'left', 'center' or 'right' (requires restart of Cinnamon).

    gsettings set org.cinnamon.extensions.weather position-in-panel center
    gsettings set org.cinnamon.extensions.weather position-in-panel left
    gsettings set org.cinnamon.extensions.weather position-in-panel right

#### Refresh Interval (optional, 240 by default)

The interval to refresh the weather information may be set arbitrarily and is specified in seconds.

    gsettings set org.cinnamon.extensions.weather refresh-interval 240

#### Restart Cinnamon

Don't forget to restart Cinnamon:

1. Restart Cinnamon (`[Alt]+[F2]`, `r`)
2. Fork this project as you like

----

### Original Authors

Ecyrbe <ecyrbe+spam@gmail.com>,
Timur Kristóf <venemo@msn.com>,
Elad Alfassa <elad@fedoraproject.org>,
Simon Legner <Simon.Legner@gmail.com>,
Simon Claessens <gagalago@gmail.com>

This file is part of cinnamon-extension-weather.

### License

cinnamon-extension-weather is free software: you can redistribute it and/or modify it under the terms of the **GNU General Public License as published by the Free Software Foundation, either version 3** of the License, or (at your option) any later version.

cinnamon-extension-weather is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with cinnamon-extension-weather.  If not, see <http://www.gnu.org/licenses/>.

