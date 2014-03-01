Simple-Masonry-Filter
=====================

Inspired by multiple-filter-masonry, extends the masonry plugin by David DeSandro adding the ability to filter items via a callback filter method.

### Usage

To use, simply set your page up as you would for the Masonry plugin. Include the masonry filter plugin after the masonry javascript:

* Note: This plugin does require jQuery to work.

    ```
    <script src="http://code.jquery.com/jquery-1.11.0.min.js"></script>    
    <script type="text/javascript" src="javascripts/imagesLoaded.js"></script>
    <script type="text/javascript" src="javascripts/masonry-3.1.4.js"></script>
    <script type="text/javascript" src="javascripts/masonry.filter.js"></script>
    ```

Again, set up your initialization scripts as you would for the masonry plugin:

    var self = $("#masonry");
    self.imagesLoaded(function () {
        self.masonry({
            gutterWidth: 15,
            isAnimated: true,
            itemSelector: ".card-container"
        });
    });

Finally, to filter, simply call the masonryFilter jQuery function on your masonry container with a filter option. The filter parameter recieves the DOM (jQuery) object as its context (this). You may use the jQuery object for filtering logic. The filter function should return true if the item should be shown, false if it should be filtered out.

    self.masonryFilter({
        filter: function () {
            if (!filter) return true;
            return $(this).attr("data-filter") == <desired filter>;
        }
    });
    
### Demo

Please see the [demo page](http://mikethedarv.github.io/Simple-Masonry-Filter/)