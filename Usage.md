# Injection of flot javascript files #

By default, gflot will automatically inject required flot javascript files inside the html page. If you need to control the javascript files which are added (to remove the selection plugin for example if you don't use it), add the following lines to your .gwt.xml :
```
  <replace-with class="ca.nanometrics.gflot.client.resources.FlotJavaScriptLoader.NoInjectionImpl">
    <when-type-is class="ca.nanometrics.gflot.client.resources.FlotJavaScriptLoader.Impl" />
  </replace-with>
```

and then add the javascript files you want to use into the header of your html page. For example :
```
    <!-- flot library -->
    <!--[if lte IE 8]><script language="javascript" type="text/javascript" src="gflotsample/js/excanvas.min.js"></script><![endif]-->
    <script language="javascript" type="text/javascript" src="gflotsample/js/jquery.min.js"></script>
    <script language="javascript" type="text/javascript" src="gflotsample/js/jquery.flot.min.js"></script>
    <script language="javascript" type="text/javascript" src="gflotsample/js/jquery.flot.selection.min.js"></script>
```

You can retrieve the javascript files from flot website :
http://code.google.com/p/flot/downloads/list
or directly in the source of this project.

The flot version actually used is 0.7 and the javascript files are :
  * jquery.min.js (required)
  * jquery.flot.min.js (required)
  * jquery.flot.selection.min.js (only for selection)
  * jquery.flot.symbol.min.js (only for additional symbol on PointsSeriesOptions)
  * jquery.flot.image.min.js (only for image plugin)
  * excanvas.min.js (only for IE <= 8)

# Flot Image plugin #

Since version 2.2.2, gflot partially supports the image plugin.

To use it, add ImageDataPoint instead of DataPoint to the model. The first parameter is the url of the image.

You also have to set the image "show" option to true on the global series options or directly on the series options.

Finally, call the method `plot.setLoadDataImages( true );` on your SimplePlot. It will load the images before creating the plot.

The flot plugin has been modified to prevent NullPointerException when the loadDataImages function is called and no image options have been set. If you use the automatic injection, it is transparent. If not, you can download the modified scripts in the download pages. The plugin is still usable without the modification but you have to define the image options on global series options and specific series options.