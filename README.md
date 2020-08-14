# D3 Country Bubble Chart

This project demonstrates various ways in which [D3](https://d3js.org/)'s [forces simulation](https://github.com/d3/d3-force) can lay out elements. Each element is a circle that represents a country. The area of each circle is proportional to the [UN's 2015 population estimate](https://esa.un.org/unpd/wpp/Download/Standard/Population/) of the country. Each circle is filled with a color or the flag of the country.

Watch the [D3 Country Bubble Chart](https://www.youtube.com/watch?v=ChniIfhvw-M) video on YouTube. Try the [live demo](https://jeffreymorganio.github.io/d3-country-bubble-chart/demo/).

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-combine-colors.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-combine-colors.png" alt="Combined/Colors"></a>
</div>

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-country-centers-colors.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-country-centers-colors.png" alt="Country Centers/Colors"></a>
</div>

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-continents-colors.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-continents-colors.png" alt="Continents/Colors"></a>
</div>

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-population-colors.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-population-colors.png" alt="Population/Colors"></a>
</div>

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-combine-flags.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-combine-flags.png" alt="Combined/Flags"></a>
</div>

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-country-centers-flags.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-country-centers-flags.png" alt="Country Centers/Flags"></a>
</div>

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-continents-flags.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-continents-flags.png" alt="Continents/Flags"></a>
</div>

<div>
  <a href="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-population-flags.png"><img src="http://jeffreymorganio.github.io/d3-country-bubble-chart/images/d3-country-bubble-chart-population-flags.png" alt="Population/Flags"></a>
</div>

## Data

The population and country center longitude and latitude data for each country is stored in `countries.csv`. The continent names used to create the continent color key are stored in `continent-names.json`. Both files are loaded asynchronously by [d3-queue](https://github.com/d3/d3-queue), which initiates the visualization after both files have loaded.

## Colors and Flags

One set of radio buttons control whether each circle is filled with a color or the flag of the country. The color represents the continent of the country and is chosen from the [schemeCategory10](https://github.com/d3/d3-scale/blob/master/README.md#schemeCategory10) palette using an [ordinal scale](https://github.com/d3/d3-scale/blob/master/README.md#ordinal-scales).

Each flag is rendered as an SVG image and is stored in the `flags` folder. The flags are from the [googlei18n/region-flags package](https://github.com/googlei18n/region-flags/tree/gh-pages/svg) (see [COPYING](https://github.com/googlei18n/region-flags/blob/gh-pages/COPYING)).

## Forces

Another set of radio buttons controls the forces that determine the location of the circles.

<dl>
  <dt>Combine</dt>
  <dd>Pushes the circles into a single group at the center.</dd>
  <dt>Continents</dt>
  <dd>Groups the circles by continent and pushes the groups towards the four corners and the center.</dd>
  <dt>Country Centers</dt>
  <dd>Uses the <a href="https://github.com/d3/d3-geo#geoEquirectangular">Equirectangular</a> projection to push the center of the circles towards the center of the countries they represent.</dd>
  <dt>Population</dt>
  <dd>Groups the circles by continent and sorts them according to population on a <a href="https://github.com/d3/d3-scale#scaleLog">log scale</a>.</dd>
</dl>

## Axes

This project also demonstrates how to animate D3 [axes](https://github.com/d3/d3-axis) on and off the screen when selecting and de-selecting the Population circle grouping. Additionally, the continent color key demonstrates how to create a color key.
