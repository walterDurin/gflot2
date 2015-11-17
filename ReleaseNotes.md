# Version 2.2.2 #
  * fix two bugs on PlotWithOverview :
    * the method clear() on PlotWithOverviewSeriesHandler was not resetting all the attributes ([r75](https://code.google.com/p/gflot2/source/detail?r=75))
    * redraw was called for each series ([r76](https://code.google.com/p/gflot2/source/detail?r=76))
  * add support for flot image plugin ([r74](https://code.google.com/p/gflot2/source/detail?r=74))

# Version 2.2.1 #
  * Just forgot to add getter for options on PlotWithOverview

# Version 2.2 #

  * fixed the method setContainer on LegendOptions ([r58](https://code.google.com/p/gflot2/source/detail?r=58))
  * you can now pass the Element used as container in SimplePlot and PlotWithOverview constructors. ([r57](https://code.google.com/p/gflot2/source/detail?r=57))
  * added getter methods for options and on plot. It allows to modify the options after the plot has been loaded and without recreating it (just call redraw())
  * added new methods to set linewidth and colors on markings ([r61](https://code.google.com/p/gflot2/source/detail?r=61))
  * /!\ Breaking change : PlotOptions.setDefaultPointsOptions, Lines and Bars have been removed. Now use the setGlobalSeriesOptions.

# Version 2.1 #

2.1 is adding most of the flot options that wasn't wrap into gflot. There is also javadocs added to the different options and some assert to insure the user don't set wrong an option.

  * added automatic injection of flot javascript files ([r35](https://code.google.com/p/gflot2/source/detail?r=35)). See [Usage](Usage.md) for more informations.
  * added some javadocs to the differents options
  * updated the PlotWithInteractiveLegendExample to use TimeSeriesAxisOptions
  * Series
    * added methods setColor(int), setClickable(boolean) and setHoverable(boolean)
    * it is now possible to retrieve Series from SeriesHandler and pass a Series object to PlotModel.addSeries()
  * SeriesOptions => AbstractSeriesOptions
    * added methods to set the option fill with opacity and fillColor with a gradient
  * BarSeriesOptions : added setHorizontal(boolean)
  * LineSeriesOptions : added setSteps(boolean)
  * GridOptions
    * can now set background color with a gradient
    * added setMinBorderMargin(int), setBorderColor(String), setAboveData(boolean)
  * PointsSeriesOptions : added new symbol with the symbol plugin ([r38](https://code.google.com/p/gflot2/source/detail?r=38))
  * AxisOptions
    * added methods for the following flot options : "color", "position", "tickColor", "show", "reserveSpace", "tickLength" and "alignTicksWithAxis"
    * added methods on TimeSeriesAxisOptions for the flot options : "twelveHourClock", "tickSize" and "minTickSize"
    * added support for "transform" and "inverseTransform" options ([r41](https://code.google.com/p/gflot2/source/detail?r=41))
    * added support for tick generator ([r44](https://code.google.com/p/gflot2/source/detail?r=44))
  * LegendOptions : changed setPosition to use an enum


# Version 2.0 #

  * gwt 2.4.0
  * flot 0.7
  * samples updated and hosted on appengine