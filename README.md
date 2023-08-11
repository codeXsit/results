
# Responsive Jigsaw Puzzle

A responsive javascript jigsaw plugin utilizing HTML5 Drag and Drop API.


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.


### Prerequisites

Javascript dependencies that need to be included:

```
<!-- Polyfill JS -->
<script src="https://cdn.polyfill.io/v2/polyfill.min.js?features=default"></script>
```


### Installing

1. Include the core plugin files on your page:

```
<!-- CSS -->
<link rel="stylesheet" href="../path/to/file/puzzle.css">

<!-- Javascript -->
<script src="../path/to/file/puzzle.js"></script>
```

2. Create a variable and initialize the plugin.

```
var puzzle = new Puzzle({options});
```

## Avaialbe Options

| Property 	| Description 	| Default 	|
| --------- | ------------- | --------- |
| **el**	| Container element which will hold the puzzle. _This option **MUST** be passed a valid HTML element_ | null |
| **image**	| URL for the image to be used. Must be a valid src value for the <[img](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#Supported_image_formats)> tag | :) |
| **numcolumns** | Number of columns in the puzzle grid | 3 |
| **numrows** | Number of rows in the puzzle grid | 3 |
| **difficulty** | Determines how much of the puzzle is shuffled. Values include "easy","normal","hard" and "expert" | "normal" |
| **debug** | Outputs useful information for drag/drop events. Must be set as a boolean value | false |


## Methods

### Init
_Usage:_
```
init()
```

Initialize puzzle instance and attach to container element.

**returns** puzzle instance.

### setOpts
_Usage:_
```
setOpts( Object[ {options} ] )
```

Redeclare options on current puzzle.

**returns** puzzle instance.

### setDifficulty
_Usage:_
```
setDifficulty( String["easy" | "normal" | "hard" | "expert"] )
```

Set difficulty of a puzzle using one of the predefined options.

**returns** puzzle instance.

### setGridSize
_Usage:_
```
setGridSize( Object[ { [numrows, numcolumns] } ])
```

Update the number of rows or columns for a puzzle.

**returns** puzzle instance.

### setImage
_Usage:_
```
setImage( String[ image_url ] )
```

Update the puzzle image (_Must be a valid src value for the <[img](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#Supported_image_formats)> tag_).

**returns** puzzle instance.

### isSorted
_Usage:_
```
isSorted()
```

Check to see if the puzzle is completed.

**returns** true or false.

### getTiles
_Usage:_
```
getTiles()
```

Grabs the current order of tiles in the puzzle.

**returns** multi-dimensional array of tiles, the first item is the original position of the tile and the second is the tile itself.

### correctTiles
_Usage:_
```
correctTiles()
```

Counts the number of tiles in order and returns that number.

**returns** number value of correct tiles.

## Callbacks

These events are exposed through the settings and accept callback functions:

* __dragstart__ - Fires when a tile is first dragged.
* __dragenter__ - Fires when a tile enters a dropzone.
* __drag__ - Fires while a tile is currently being dragged.
* __dragover__ - Fires while a tile is dragged over a dropzone.
* __dragleave__ - Fires when a tile is exits a dropzone.
* __dragend__ - Fires when a tile is no longer being dragged.
* __drop__ - Fires when a tile is dropped.
* __touchstart__ - Fires when a tile is touched.
* __touchmove__ - Fires while a tile is dragged over the document.
* __touchhover__ - Fires while a tile is dragged over a dropzone.
* __touchend__ - Fires when a tile is no longer being dragged.
* __correct__ - Fires when a tile is dropped into the correct slot.
* __finished__ - Fires when the entire puzzle is completed.

To use callbacks pass a custom function to one of the above events in your initial settings. 

Each callback is passed a custom object that includes a reference to the puzzle instance, the event and the event target.

## Running the tests

You can include the `debug` option to output useful information to the console.


## Built With

* [Polyfill IO](https://polyfill.io/v2/docs/) - Extends vanilla JS support in IE 


## Authors

* **Eric Harris** - *Initial work* - [Eric-Jr](https://github.com/Eric-Jr)


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
