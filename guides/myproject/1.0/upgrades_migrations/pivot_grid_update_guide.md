#Pivot Grid Upgrade Guide

##Package Structure

The `mzPivotGrid` and `mzPivotMatrix` packages have been merged into a single package called 
`pivot`. The resulting structure looks like this:

![PivotGrid File Structure](images/pivot_structure.png)

##Package Inclusion
If you used the `mzPivotGrid` package in your MVC app, you will need to change your 
`requires` block in the Sencha Cmd generated `app.json` file. Previously, it was named 
`mzPivotGrid`. It should be updated to `pivot` and the `exporter` package should also be copied
to the app packages folder since it is required by `pivot`.

##Build Files
If you used the built version of `mzPivotGrid`, be sure to change all paths to point towards 
the compiled file in the package's build directory. 

For instance:

     pivot/build/pivot{-debug}.js
     
You will also need to utilize the appropriate CSS file that can also be found in the build 
directory's theme folders.

     pivot/build/{theme}/resources/pivot-{flavor}.js

##Updated Namespace
Several classes have been changed: 
- Mz namespace has been moved to the Ext namespace.
- Mz.aggregate.* have been moved to Ext.pivot.*.
- All Abstract classes have been renamed to Base.
- Mz.pivot.plugin.ExcelExport is now Ext.pivot.plugin.Exporter and its ptype is `exporter`.
- Mz.pivot.dataexport.* have been dropped and the Excel classes are now part of the `exporter` package.
- Mz.pivot.plugin.drilldown.* have been dropped.
- All Sass variables for the pivot package have been reworked and are now prefixed with `pivot-grid`.
- Ext.pivot.MixedCollection and all Ext.pivot.plugin.configurator.* classes are now private.
- All plugins have new ptypes prefixed with `pivot`: `pivotconfigurator`, `pivotdrilldown`, `pivotrangeeditor` and `pivotexporter`

##Updated Configs
The pivot grid component used to have `mzpivotgrid` as xtype which is now `pivotgrid`. `mzpivotgrid` 
is still available but will be dropped in future versions.

All Abstract (Base) classes have been changed to use factoriable configs. Ext.Factory is used
now internally to instantiate objects instead of Ext.createByAlias. Previously the `mztype` config
was used to identify the class that needed to be instantiated. Since version 6 you should use
`type` instead of `mztype`.

For instance:

     {
          xtype: 'mzpivotgrid',
          matrixConfig: {
               mztype: 'local',
               store: 'storeId'
          },
          //...
     }
     
Should be replaced with:

     {
          xtype: 'pivotgrid',
          matrixConfig: {
               type: 'local',
               store: 'storeId'
          },
          //...
     }

Since `mztype` is now `type`, the old `type` config in Ext.pivot.filter.Base became `operator`.
All constants defined in the Base filter class were dropped and literals should
be used to set the `operator`.

For instance:

     topAxis: [{
          dataIndex:     'year',
          header:        'Year',
          filter: {
               mztype:   'label',
               type:     Mz.aggregate.filter.Abstract.TypeBetween
               from:     2010,
               to:       2012
          }
     }]
     
Should be replaced with:

     topAxis: [{
          dataIndex:     'year',
          header:        'Year',
          filter: {
               type:     'label',
               operator: 'between',
               value:    [2010, 2012]
          }
     }]

Please take a look at the Ext.pivot.filter.* classes to see what other operators are available.

##Remote calculations
Matrix configs `keysSeparator` and `grandTotalKey` are sent to the server together
will all configured dimensions and should be used on the server when the JSON response
is generated.

##Localization

![image alt text](images/pivot-locale_structure.png)

All pivot grid locales have been moved to the `pivot-locale` package.

##Export to Excel plugin
This plugin has been refactored. The Mz.pivot.plugin.ExcelExport class has been renamed to
Ext.pivot.plugin.Exporter which has now the `ptype: "pivotexporter"`.

For instance:

     {
          xtype: 'mzpivotgrid',
          plugins: [{
               ptype: 'mzexcelexport',
               pluginId: 'excel',
               title: 'Excel export'
          }]
     }
     
     //somewhere on a button you might have something like this
     var xml = grid.getPlugin('excel').getExcelData(true, true);
     // and the xml content was either sent to the server or saved in the browser somehow
     
Should be replaced with:

     {
          xtype: 'pivotgrid',
          plugins: [{
               ptype: 'pivotexporter'
          }]
     }
     
     // somewhere on a button you may have something like this
     grid.saveDocumentAs({
          type: 'excel',
          title: 'Excel export',
          onlyExpandedNodes: true, // that's the equivalent of the first param in the old getExcelData function
          showSummary: false, // that's the equivalent of the 2nd param in the old getExcelData function
          fileName: 'export.xml'
     });
     
     // saveDocumentAs will try to save the file in the browser. If your browser is not supported then do this
     var xml = grid.getDocumentData({
           type: 'excel',
           title: 'Excel export',
           onlyExpandedNodes: true, // that's the equivalent of the first param in the old getExcelData function
           showSummary: false // that's the equivalent of the 2nd param in the old getExcelData function
      });
     // and probably send the xml content to the server

As you can see above the `pivotexporter` plugin adds two new methods to the pivot grid component. These methods
accept a config object as parameter. 

A bunch of configs were available on the old plugin which allowed you to style the Excel output. These configs 
do not exist anymore on the plugin level, instead a new set of configs can be passed to the `saveDocumentAs` 
or `getDocumentData` methods. Reason is that you could implement your own Exporter class that extends
Ext.exporter.Base which can have its own set of configs.

Here is an example of how to map the old configs to the new Excel Exporter class.

     grid.saveDocumentAs({
          type: 'excel',
          title: 'Excel export', // previously set on the plugin itself
          defaultStyle: {
               font: {
                    FontName: 'Calibri',     // previously known as `cellFontName`
                    Size: 11,                // previously known as `cellFontSize`
                    Family: 'Swiss',
                    Color: '#000000'
               },
               interior: {
                    Color: '#ffffff'         // previously known as `cellFillColor`
               },
               borders: [{
                    Position: 'Top',
                    Color: 'red'             // previously known as `cellBorderColor`
               }]
          },
          
          titleStyle: {
               name: 'Title',
               font: {
                    Size: 11                 // previously known as `titleFontSize`
               },
               interior: {
                    Color: '#ffffff'         // previously known as `titleFillColor`
               }
          },
          
          tableHeaderStyle: {
               name: 'Heading 1',
               font: {
                    Size: 11                 // previously known as `headerFontSize`
               },
               interior: {
                    Color: '#ffffff'         // previously known as `headerFillColor`
               }
          },
          
          groupHeaderStyle: {
               name: 'Group header',
               font: {
                    Size: 11                 // previously known as `groupHeaderFontSize`
               },
               interior: {
                    Color: '#ffffff'         // previously known as `groupHeaderFillColor`
               }
          },
          
          groupFooterStyle: {
               name: 'Group header',
               font: {
                    Size: 11                 // previously known as `groupFooterFontSize`
               },
               interior: {
                    Color: '#ffffff'         // previously known as `groupFooterFillColor`
               }
          }
     });
 
In this new approach various other styling can be applied to the exported document. Check out
the Ext.exporter.file.excel.Style class for more styling options.