# Personality Sunburst Chart

Obtain a sunburst chart visualization for a personality profile.  For use in an HTML page.

![Personality Sunburst Chart](./examples/personality-sunburst-chart-small.png)

## Step 1: Converting a CSV file with personality traits into a Waton Personality Insights JSON profile
This is required if you only have a csv containing the scores for the personality traits.

### Required files
generate_sunburst_json_from_csv.ipynb - the script you run to convert a csv profile to a json profile
template.json - the target json format with placeholders for the scores pulled from the csv
v3_labels.txt - a text file that maps trait label names to the placeholders in template.json

### Instructions
TBA


## Step 2: Creating a Sunburst Chart from a Watson Personality Insights JSON profile
### Required files
example_v2.html - when you update this with a profile.json and profile_photo.jpg and open it in a browser, the generated sunburst chart will be generated and shown
profile.json - a Watson Personality Insights JSON profile
profile_photo.jpg

### Instructions
Include the following libraries as scripts in your HTML page.
```html
<script src="https://code.jquery.com/jquery-2.2.0.min.js"></script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.17/d3.min.js"></script>
<script type="text/javascript" src="https://unpkg.com/personality-sunburst-chart@2.0.4/dist/index.js"></script>
<script src="https://d3js.org/d3-color.v1.min.js"></script>
```

Create an element to contain the chart in your HTML page.
```html
<div id='sunburstChart'></div>
```

Generate the visualization for a personality profile.
```JavaScript
  // Create the chart, specifying the css selector that identifies the element to contain the chart
  // and the version of Watson Personality Insights profile to use, v2 or v3.  Default is v2.
  var chart = new PersonalitySunburstChart({
    'selector':'#sunburstChart', 'version': 'v2'
  });

  // Replace the path to the json file for the Watson Personality Insights profile you want to visualize, i.e., replace profile.json with the name for the personality profile you're using
  $.getJSON('profile.json', '', function ( profile )

  // Render the sunburst chart for a personality profile (version as specified in creating the chart)
  // and optionally a profile photo.  The photo will be inserted into the center of the sunburst chart.
  chart.show('jsonObject', 'path/to/profile_photo.jpg');

  ```

## License

This library is licensed under Apache 2.0. Full license text is
available in [LICENSE](LICENSE).
