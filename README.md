# Cutter.js
Cutter.js is a library used for truncating HTML code to limit its length, by word number, without losing the markup.

## Description

Cutter solves the problem when its needed to cut some content by a number of words but its mandatory no lose any markup.
Cutter cuts the content to the number of requested words and if needed puts a link to open the full content again.

### Some benefits:

*   No markup is lost.
*   Framework agnostic.
*   The content can be written without take care about the full content.
*   Not needed to have two different contents.
*   Crossbrowsing
    * Tested on:
        * IE >= 6
        * Firefox >= 3
        * Safari >= 4
        * Google Chrome >= 4
        * Opera >= 9.5
*   Only 1.5kb when [Gzipped](http://tcorral.github.com/Cutter.js/versions/cutter.js.gz).

(Links will only work if you clone the repo.)

[API documentation](https://github.com/tcorral/Cutter.js/examples_and_documents/jsdoc/index.html)

[Examples](https://github.com/tcorral/Cutter.js/examples_and_documents/index.html) to see for yourself!

## Instalation

You can install cutter.js using Bower by typing:

  bower install cutter.js

## Usage

### Before using it:
Insert in your code:

	<script type="text/javascript" src="/path/to/your/bower/dist/cutter.js"></script>

### Simple execution:

	Cutter.run(oApplyTo, oTarget, nWords, [configuration]);

####Mandatory

  >  **oAplyTo**: The element that will have its text truncated

  >  **oTarget**: The element where the truncated content will be placed.

  >  **nWords**: Maximum word count. Any additional word will be truncated.

####Optional

  >  **configuration**: This object contains both the text that will be displayed in the "view more" link and its style.

  >>    configuration.viewMoreText: The text that will be displayed in the "view more" link. The default is "View more"
  
  >>    configuration.viewMoreSeparator: The DOM element tag that separates the text from the text itself

  >>    configuration.class: The class that will be applied to the "View more" link. The default is "more"


*Tip: oTarget Could be the same oApplyTo element if we want to replace the full content with the cut content*

## Usage

```javascript
    cutElement = document.getElementById("test");
    Cutter.run(cutElement, cutElement, 30, {viewMoreText:"Expand", class:"expandLink", viewMoreSeparator:"span"});
```

*On the example above, the element with id "test" will display a maximum of 30 words and a link entitled "Expand". The "expandLink" class will be applied to this link. The remaining words that were previously truncated will show up in the element when the link is clicked.

## Example

```html
<html>
<head>
    <script type="text/javascript" src="../dist/cutter.min.js"></script>
    <style>
        #txt-test i{
            margin-left:20px;
        }    
        
        .expandLink {
            cursor: pointer;
            text-decoration:underline;
            font-weight: 700;
        }
    </style>
</head>
<body>
  <p id="txt-test" onclick="test();">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum tincidunt mattis urna, vitae rhoncus arcu eleifend at. Suspendisse quis est dui. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nam finibus finibus tellus eu convallis. Suspendisse potenti. Pellentesque mollis interdum nulla at cursus. Aliquam nulla dolor, laoreet sed tincidunt ut, ultricies non metus.</p>
</body>
<script>
    cutElement = document.getElementById("txt-test");
    Cutter.run(cutElement, cutElement, 30, {viewMoreText:"Expand", class:"expandLink", viewMoreSeparator:"i"}});
</script>
</html>
```
## License

Cutter.js is licensed under the MIT license.
