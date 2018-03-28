# Release Notes for Ext JS 6.5.3

### Grid
+ EXTJS-26172	Scrolling upwards quickly when there are many expanded rows throws error

+ EXTJS-26623	grid with locked column scrolls to top on refresh with preserveScrollOnRefresh: true

+ EXTJS-19300	Store state is not applied when store binding is used

+ EXTJS-26563	Modern list multi-selection produces inconsistent behavior

+ EXTJS-19955	Visual sort state is not applied when store is sorted via API

+ EXTJS-20980	Classic grouped grid scrolls back to focused cell when user expands row

+ EXTJS-23479	Grid reconfigure does not update column alignment

+ EXTJS-23480	Grid column does not respect new values for align

+ EXTJS-24892	rowexpander with grid adding extra record

+ EXTJS-24893	Rowexpander immediately collapses second level expander

+ EXTJS-26268	Grid no longer scrollable when a menu item

+ EXTJS-26331	Grid set as Viewport ignores preserveScrollOnReload:false

+ EXTJS-26678	6.5.3.36 classic nightly regression - Too Many Row Widgets

+ EXTJS-26614	grid viewoptions scrollbar jumps to the top when scrolling

+ EXTJS-25536	Grid is grouped but no group headers or other visual indications are visible

+ EXTJS-25838	Change rating affects item below when it is grouped by rating

+ EXTJS-25950	Document requires of Summary plugin types 


### Tree
+ EXTJS-26515	Tree panel scroll on refresh when a row is focused

+ EXTJS-26452	treepanel scrolls to top when using replaceChild

### PivotGrid
+ EXTJS-25046	Add column to Pivot Grid makes all rows go blank

+ EXTJS-26373	PG configurator does not appear when clicking fields


### Charts
+ EXTJS-26102	Tooltip is not visible in the middle of bar chart

+ EXTJS-26423	The overlay selection rect of the CrossZoom interaction doesn't render on top of the series but behind them.

+ EXTJS-26415	Adding records to Pie store does not call performLayout ('dom' legend doesn't schedule chart layout when the legend size changes)

+ EXTJS-26751	Case error in trackMouse config in chart series

### Forms
+ EXTJS-26177	Select already selected item in selectfield make it unselected

+ EXTJS-26476	Datefield closing by choosing a year (on tablets)

+ EXTJS-26768	Running Msg/Prompt window twice causes issue

+ EXTJS-25839	Ext.field.File#reset does not reset result of getFiles method

+ EXTJS-26154	Calling setValue consecutively clears combo lastSelectedRecords and breaks forceSelection

+ EXTJS-26343	Tagfield with mutliselect false does not clear emptyText

+ EXTJS-26453	Datefield can prematurely invalidate when allowBlank: false and clicking picker

+ EXTJS-25632	SetScroller animation can prevent/close combo picker

### Calendar
+ EXTJS-26610	Calendar event is not drawn when the event is less than 24 hours

### Panel
+ EXTJS-26457	Collapsible panel throws exception on expand

+ EXTJS-26578	Ext.panel.Table buildColumHash should not initially assign value to var len

+ EXTJS-26605	MODERN: Floated panel with alwaysOnTop: true throws error


### List
+ EXTJS-25502	More Undo buttons can be shown in list with listswiper plugin

+ EXTJS-24371	Masked components should not be scrollable

### Window
+ EXTJS-26534	Windows not centred in client view when the view is scrolled down.


### Documentation
+ EXTJS-26437	Ext.field.Field.validator has incorrect reference to Ext.data.validator.Validator

+ EXTJS-25401	Application - getRouter method is not documented


### Button/SplitButton

+ EXT-568	Alt Raised button text is not visible when we toggle the style in IOS Theme

+ EXT-570	Menu Items drop down is not removed on blur

+ EXT-571	Unexpected Text NULL is appearing on the buttons

+ EXT-573	Text is not visible on selected buttons when we toggle the style

+ EXT-574	After clicking,button is not highlighted 

+ EXT-575	Click on Default split buttons are altering other Split buttons

+ EXT-577	Split line is not visible in Alt,Alt Raised for different styles

+ EXT-578	Buttons size are varying while toggle the style

+ EXT-581	Buttons are not highlighted after selecting in IOS Theme

+ EXT-582	UI issue with the selected buttons while toggle the style

+ EXT-588	Alt button is left pressed automatically without clicking on it

+ EXT-589	Drop down menu is highlighted without placing mouse pointer on it

+ EXT-590	Split lines are not visible

+ EXT-592	Tapping only effect part of left or right button part. 

+ EXT-593	Split vertical bar is not disabled for Raised and Alt Raised Split large buttons

+ EXT-594	Left pressed button is not working as expected

+ EXT-595	Split vertical bar is not visible for Alt and Raised Buttons when mouse hover on default button

+ EXT-599	Round ripple is coming out of the button and also in Square form

+ EXT-636	Issues in button shape when changing it to round

+ EXT-569	Split buttons Small,Medium,Large are not varied in size

+ EXT-576	Split buttons are not highlighted on click

+ EXT-585	Mouse-hovering and color issues with alt and alt raised split buttons in IOS theme.

+ EXT-586	Ripple Effect overlaps button boundary in icon type.

+ EXT-587	Click and Mouse-hovering Issues in IOS theme and style decline

+ EXT-591	Default button: Vertical split bar is deflected on left pressed on Default Small button


### DataView
+ EXTJS-25779	[Multisort DateView] items stay selected when sort 

### Examples
+ EXTJS-25845	Chart has a set theme from previous example as default 

### Events
+ EXTJS-26672	GlobalEvents does not properly propagate events associated with touch/press release

### Widget
+ EXTJS-26190	Specifying ui config as array results in an error

### Util
+ EXTJS-26409	Ext.util.TSV#decode does not handle quotes correctly

### NestedList
+ EXTJS-26553	NestedList Issues





# Release Notes for Ext JS 6.5.2

## New Features

### Misc (1)

+ EXTJS-22458 ColorPicker UX should accept and display values in RGB(A) format

## Bugs Fixed

### App (1)

+ EXTJS-25985 Window with destroy listener throws uncaught Controller error when closing window

### Bind (3)

+ EXTJS-26211 Store binding publishes count as null between load request and response

+ EXTJS-25417 Binding for associated record is not triggered if the key setting causes a change

+ EXTJS-25971 Strings in bind templates cannot contain literal "{" characters (escape mechanism needed)

### Button (1)

+ EXTJS-26023 Ext.Button Missing callParent Method on initialize method

### Charts (10)

+ EXTJS-25914 No visible change after changing the template of the Instancing sprite

+ EXTJS-26064 Bar Chart with 2 columns renders incorrectly

+ EXTJS-26074 Theme is not applied to a chart with no series

+ EXTJS-26223 modern Line Chart doesn't load on iOS9 tablet

+ EXTJS-26014 Hiding marker in series hides it in legend as well

+ EXTJS-26024 Chart navigator can't resolve chart listeners to a controller

+ EXTJS-26111 Series range calculation doesn't take nulls into account

+ EXTJS-26344 Drag and drop markers make error in console and won't move

+ EXTJS-25850 Should be able to dynamically configure series 'marker' config.

+ EXTJS-25904 Scatter series: can't change the type of marker dynamically

### Core (5)

+ EXTJS-26163 alignTo method no longer works with element id

+ EXTJS-25784 ESC does not hit the Dialog's onEscape when its buttons are focused

+ EXTJS-23668 Component - unused local variable in onRemoved

+ EXTJS-26020 Component does not update correctly when changing tpl

+ EXTJS-25990 Weighted container incorrectly adds a single object after construction

### Data (4)

+ EXTJS-26208 Adding filters and/or sorters to a Virtual Store causes it to break

+ EXTJS-26270 Memory leak through usage of Ext.data.Batch

+ EXTJS-25989 Ext.data.request.Form.onComplete produces JSON that cannot be parsed when Ext.USE_NATIVE_JSON true

+ EXTJS-26107 Data reader should not explicitly set phantom state unless data is coming from a proxy

### DataView (1)

+ EXTJS-26048 CTRL/A to select all doesn't work in dataviews and grids.

### Dialog (1)

+ EXTJS-26008 Dialog close uses showAnimation when initialized with displayed: true

### Distribution (2)

+ EXTJS-25974 Framework ext-*.js builds should not use transpiler

+ EXTJS-26229 Build errors in KitchenSink are not failing the overall build

### Documentation (12)

+ EXTJS-25793 Calendar configs are incorrectly determined to be properties

+ EXTJS-25072 Ext.MessageBox docs for "show" method not as expected

+ EXTJS-25340 Textarea should indicate growMin/growMax should be used with grow, as opposed to height

+ EXTJS-22393 The tagfield inline example is broken

+ EXTJS-26071 Ext.button.Segmented#change event -- newValue and oldValue can be an array of values

+ EXTJS-25944 Missing config name causing incorrect output ...

+ EXTJS-23316 Documentation - radiofield input value config type is only string

+ EXTJS-24923 Wrong description of Ext.grid.column.Action.menuText

+ EXTJS-25954 Incorrect default labelAlign layout in Ext.field.Text

+ EXTJS-24919 Incorrect default closeAction displayed for MessageBox

+ EXTJS-20064 The twoWay config should be added to the documentation

+ EXTJS-26029 Ext.concat not visible in the docs

### Events (1)

+ EXTJS-22909 Firing event on destroyed component throws an exception

### Exporter (2)

+ EXTJS-26195 Excel Export Sheet name as Excel Title

+ EXTJS-26203 Ext.exporter.file.Style#interior corrupts the generated download

### Forms (16)

+ EXTJS-26283 Item in selectfield or combobox is picked by selecting and picker is closed

+ EXTJS-19731 ComboBox.valueNotFoundText not displaying

+ EXTJS-25921 ComboBox attempts to scroll before items are rendered and get promise rejection

+ EXTJS-25910 Using iOS, inputs with emptyText fail to open keyboard on tap

+ EXTJS-25829 TextField with grow: true doesn't use padding in the autoSize calculation

+ EXTJS-25889 User can end up with open edge picker and open virtual keyboard

+ EXTJS-25982 Calling setValue on focused field won't update it's value until blur

+ EXTJS-26010 Invalid datefield cannot be reset

+ EXTJS-26019 TextArea with minHeight doesn't stretch the inputEl correctly

+ EXTJS-23374 Text field focus bug on touch devices

+ EXTJS-25967 ComboBox minChars is not honored when queryMode is 'remote'

+ EXTJS-25957 Query selector returns duplicate components for a carousel wrapped in a form

+ EXTJS-23285 Cannot focus on textfields with emptyText config on touch devices

+ EXTJS-25448  Load record does not set radiogroup field in inactive tab correctly if it has a default value checked

+ EXTJS-25997 Hidden field should default hidden: true

+ EXTJS-25385 Field is not scrolled into view when you start typing

### Grid (20)

+ EXTJS-26087 Grid's columnsort event is never fired

+ EXTJS-25909 Column renderer gets passed the groupPlaceholder record instead of the first record for renderedGroupValue

+ EXTJS-25996 Navigation issues when grouping feature and cell edting and record updating are combined

+ EXTJS-26207 CheckboxModel throws error when updating checked cell using checkOnly: true

+ EXTJS-26295 Empty text visible even when one of containers is shown

+ EXTJS-24698 Grid view is blank after store reload

+ EXTJS-20934 Locking a column in a locked grid subclass with dockedItems shows them twice

+ EXTJS-26076 If a grid is scrolled down and loaded again, empty view results

+ EXTJS-26091 Grid mask target differs for locked and unlocked grids

+ EXTJS-26058 Grid with buffered renderer will jump when record dragged from it

+ EXTJS-24308 shift + select with checkbox does not work with spreadsheet selection model

+ EXTJS-11547 Locked grouped grid doesn't respect 'lockable' attribute of column

+ EXTJS-26031 Re-ordering grouped header with inner items throws error

+ EXTJS-25691 Reconfiguring grid with ALL locked columns renders no rows

+ EXTJS-23618 Grid column header does not sync correctly with vertical scroll in Firefox

+ EXTJS-25958 RTL grid does not display row editor correctly

+ EXTJS-23766 deferEmptyText: false not honored when columns are not present

+ EXTJS-26092 Locked grid columns headers misaligned when navigating between locked and unlocked sides

+ EXTJS-26113 Grid focuses on all cells while cycling to next row when using cell editing

+ EXTJS-24330 Grid group tabbing navigation from bottom causes error

### Layouts (1)

+ EXTJS-26191 Viewport sized incorrectly with Chrome iOS and breaks scroliling

### Misc (4)

+ EXTJS-26105 DatePanel: disabledDays doesn't prevent selection.

+ EXTJS-25923 Remote ComboBox is not editable

+ EXTJS-25194 Dialog with displayed: true doesn't display unless the displayed config is changed

+ EXTJS-22404 Grid scroll position is reset and blanked out when moving between containers

### Panel (4)

+ EXTJS-26032 Panel throws exception on null buttons config

+ EXTJS-26040 Panel with no items and bound to collapsed isn't actually collapsed

+ EXTJS-25816 Changing panel header to left throws exception in IE8, IE9

+ EXTJS-25960 collapseMode:'mini' expander doesn't render when initially collapsed

### PivotGrid (1)

+ EXTJS-26278 Error thrown during key navigation in locked pivot grid in certain cases

### Sparklne (1)

+ EXTJS-26151 sparkline graph disableTooltips config does not work

### Tabs (2)

+ EXTJS-26079 Tab panel does not destroy tools for overflow scrolling

+ EXTJS-24159 Tabpanel doesn't scroll in RTL

### Templates (1)

+ EXTJS-26000 Coworkee app throws error when reloading dataview

### Theme (5)

+ EXTJS-26081 Triton split button icons are horizontally misaligned when the button has no text

+ EXTJS-26027 Widget ripple config wrongly processes release property for ripple-on-release

+ EXTJS-26022 FieldSet top border is in triton theme doesn't use correct variable

+ EXTJS-25170 Opacity should not be used to lighten colors that are used as borders or backgrounds

+ EXTJS-18728 Loadmask spinner colors make it difficult to see in triton/neptune theme

### ToolTips (3)

+ EXTJS-24917 Tooltip not showing in correct position after view scroll

+ EXTJS-23611 onTargetOver throws exception when tooltip element of QuickTipManager.register has been removed

+ EXTJS-26011 6.5.0 Modern - Various tooltip errors

### Tree (1)

+ EXTJS-25817 Fails to load XML Tree example on IE9

### Window (2)

+ EXTJS-26016 Window is sent to back when clicking the close tool while tooltip is visible

+ EXTJS-25919 Window z-index changes after closing windows

## Known Issues

### Tabs (1)

+ EXTJS-13538 Ext.ux.TabScrollerMenu has not been updated to work in Ext JS 5 and 6

# Release Notes for Ext JS 6.5.1

Release Date: Thur Jul 20 2017  
Version Number: 6.5.1.345

## New Features

### Charts (1)

+ EXTJS-25382 - Chart rotate interaction should fire rotatestart/rotate/rotateend (deprecate rotationEnd)

### Core (1)

+ EXTJS-24406 - Disabling pinch/zoom should also prevent elastic over-scrolling of viewport on iOS in modern

### Data (1)

+ EXTJS-25665 - Store should be configurable to reload on reduction of sorter count to zero

### Exporter (1)

+ EXTJS-21125 - Exporter should be able to export treegrid to spreadsheet

### Forms (4)

+ EXTJS-21726 - Navigate the DatePicker to the first available date onShow

+ EXTJS-24913 - Allow selectfield to default "empty text" value

+ EXTJS-24354 - ComboBox should support an object passed to setValue with both value and display fields

+ EXTJS-21816 - Add a defaultValue config to the DatePicker

### Grid (1)

+ EXTJS-16590 - Modern toolkit grid should support clipboard plugin

### Layouts (2)

+ EXTJS-25242 - Modern box layout should provide scroller overflow handler

+ EXTJS-25049 - Modern Ext.Container should provide bindable activeItemIndex config

### Tabs (1)

+ EXTJS-16516 - Modern toolkit should support desktop-style TabBar

### ToolTips (1)

+ EXTJS-25305 - ToolTip should provide a way to show ellipsis overflow content

## Bugs Fixed

### App (2)

+ EXTJS-25878 - Component references are not cleaned up properly by destroy()

+ EXTJS-25308 - Router redirectTo force option is ignored

### Bind (2)

+ EXTJS-25316 - Two-way binding through store first or last meta properties fails

+ EXTJS-25304 - Textfields and Textareas with 'publishes' config ignore value binding

### Button (2)

+ EXTJS-25724 - Button stays in pressed state after tapping to hide the menu

+ EXTJS-24268 - Button w/menu should appear pressed when menu is displayed (material)

### Calendar (4)

+ EXTJS-25664 - Calendar month view doesn't clear drag selection on add if no add form is available

+ EXTJS-25615 - SideBar items with negative weights should appear at top

+ EXTJS-24891 - Dragging events throws error in IE8/9

+ EXTJS-24996 - Moving All-day event in month view causes throwing error to console

### Charts (22)

+ EXTJS-25745 - Bar series rendering is not spread out across canvas (remove non-functional increment and labelInSpan configs)

+ EXTJS-25741 - Extra legend is created while creating series dynamically

+ EXTJS-25550 - Sprite legend does not render markers when "pie3d" series use the "colors" config. Series "colors" config does not affect colors of series and sprite legend sprites, if configured dynamically.

+ EXTJS-25449 - Add a config that will allow you to change where the gauge chart needle renders

+ EXTJS-25411 - Legend sprite image markers are not visible on first render.

+ EXTJS-25508 - Chart Navigator doesn't bind dynamic store correctly

+ EXTJS-25413 - The bottom axis animation is jittery in the Real-time (numbers) example

+ EXTJS-25384 - Chart Navigator component can't find the overlay surface

+ EXTJS-25333 - 3D Pie series: setting 'highlight' only works in the initial config.

+ EXTJS-25332 - Removing series label (setting to null) doesn't work.

+ EXTJS-25331 - 3D pie series: if the 'label' config wasn't set initially, setting it later won't work

+ EXTJS-22782 - SpriteLegend should have the 'hidden' config. 'docked' config should support dynamic reconfiguration.

+ EXTJS-23053 - Tooltips do not hide immediately when moving to another series

+ EXTJS-25266 - Bouncing logo example has jerky movement in IE11

+ EXTJS-24540 - Chart axes and sprite legend are not using a proper font on initial render to document.body

+ EXTJS-20721 - IndexSizeError on Pie3D destruction and mousemove

+ EXTJS-20870 - Calling loadData can throw error on Pie Chart

+ EXTJS-17104 - When a pie chart displays only one slice, the border of the slice creates a vertical line

+ EXTJS-24894 - 3D pie: chart legend doesn't update when new data is loaded into a store via AJAX proxy

+ EXTJS-25263 - Graphic glitches in charts in IE11

+ EXTJS-25265 - 3D pie chart is rotating slowly in iE11

+ EXTJS-25181 - Ext.chart.AbstractChart is missing require for Ext.chart.Util

### Core (9)

+ EXTJS-25830 - Inheritable - return false when ancestor or descendant not found

+ EXTJS-25809 - layout initialConfig value is being mutated

+ EXTJS-25518 - Rows do not layout properly when grid is scaled by CSS transform

+ EXTJS-25551 - documentMode is not interpreted correctly with X-UA-Compatible meta tag and IE11

+ EXTJS-25601 - Ext.dom.Element.measure() is affected by transforms

+ EXTJS-25423 - referenceHolder is not set correctly when using a view controller

+ EXTJS-23263 - getOrientation incorrect in IE11/Edge

+ EXTJS-25282 - Ext.Function.bind() incorrectly changed default value of appendArgs to true

+ EXTJS-21139 - View incorrectly resized when changing screen orientation while the virtual keyboard is shown

### D3 (4)

+ EXTJS-25584 - Configurable pivot treemap has performance issues when set more dimensions

+ EXTJS-25336 - Root won't collapse d3 tree and than first child collapse whole d3 Tree

+ EXTJS-24332 - D3 components leak tooltip instances once activated

+ EXTJS-23751 - D3 Zoomable Sunburst performance is noticeably worse on Firefox

### Dashboard (2)

+ EXTJS-19853 - Programmatically added views to Ext.dashboard.Dashboard ignore columnWidths

+ EXTJS-19881 - Ext.dashboard.Dashboard does not set state properly when columns are removed

### Data (6)

+ EXTJS-25652 - Session getSaveBatch doesn't set records correctly when proxy has batchActions: false

+ EXTJS-25465 - IPAddress validator has unnecessary escape in its regex

+ EXTJS-25516 - Exception in Virtual Store when result set has fewer pages than initial request (default of 2 pages)


+ EXTJS-23578 - Session is not clean after removing a phantom associated record

+ EXTJS-23577 - Session dirtychange not fired when pushing new records from a child session

+ EXTJS-19901 - Store autoload when groupField specified along with autoLoad: false

### DataView (5)

+ EXTJS-25754 - Incorrect animation in picker slot for UP direction

+ EXTJS-25453 - Component DataView throws exception when store removal occurs while not rendered

+ EXTJS-25586 - Cannot multiselect dataview items with shift

+ EXTJS-24870 - selectable: false should disable selection in dataviews, lists and grids

+ EXTJS-25016 - Dragging images in Lists or DataViews creates a browser native selection

### Direct (1)

+ EXTJS-25560 - When enter the space character " " to menu>textfield is displayed error message

### Documentation (38)

+ EXTJS-25934 - Ext JS - FAQ page should be updated

+ EXTJS-25927 - API diffs are creating page errors

+ EXTJS-25928 - API diffs Classic page has broken layout at the end of the page

+ EXTJS-25748 - Modern Panel - addTool method is not documented

+ EXTJS-25932 - In Documentation link should be updated to chosen version in Quick Start - Helpful Resources

+ EXTJS-25900 - Typo in sass var name $fieldset=border

+ EXTJS-25679 - Touch scroller should be removed from documentation

+ EXTJS-25441 - Router - suspend and resume documentation missing

+ EXTJS-25407 - Route mixin doc typo

+ EXTJS-25443 - History.add - document return value

+ EXTJS-25432 - Documentation should indicate datachanged is fired along with update

+ EXTJS-25442 - Router - typo in a param description

+ EXTJS-25464 - Incorrect signature for component 'painted' event

+ EXTJS-25581 - Container - Remove the fake "." after setActiveTab

+ EXTJS-25375 - GridEditable triggerEvent docs incorrect

+ EXTJS-25363 - Ext.Toast examples throw error

+ EXTJS-25347 - Add documentation for date panel's headerFormat config

+ EXTJS-23230 - Documentation of Ext.ux.colorpick.Selection#format config should use slash as type delimiter

+ EXTJS-23080 - Missing Ext.calendar.panel.Panel#switcher config documentation

+ EXTJS-20242 - Documentation is unclear on combining grouping and groupingsummary grid features (deprecate groupingsummary)

+ EXTJS-25306 - API diffs are missing the deprecated events

+ EXTJS-24694 - Several modern classes marked as private that shouldn't be

+ EXTJS-24879 - typo in Ext.Widget-cfg-instanceCls

+ EXTJS-24289 - Docs for select event are unclear on how record(s) are passed

+ EXTJS-25169 - Cannot run example of Ext.Progress when using Modern API docs

+ EXTJS-24863 - typo in Ext.field.Text links

+ EXTJS-16890 - Make sure all Deprecated members have suggested alternatives

+ EXTJS-25109 - Ext.grid.Tree - add class description

+ EXTJS-25107 - Ext.field.InputMask - add class description

+ EXTJS-25162 - Ext.data.field.Number - add class description

+ EXTJS-25079 - Documentation for Ext.field.ComboBox gives wrong instructions

+ EXTJS-25128 - Add itemtap event to treelist

+ EXTJS-25161 - Ext.slider.Slider - add class example

+ EXTJS-25081 - Viewport documentation refers to old Ext.setup() method

+ EXTJS-25287 - Classic Viewport scrollable's default value is not documented

+ EXTJS-25164 - Ext.data.field.Integer - add class description

+ EXTJS-25163 - Ext.data.field.Boolean - add class description

+ EXTJS-25165 - Ext.data.field.String - add class description

### Drag (1)

+ EXTJS-25726 - Panel that is draggable and resizable will drag on resize

### Events (1)

+ EXTJS-25469 - Event stopPropagation from directly attached listeners (such as 3rd party libs) cause gesture recognizer to fail

### Examples (24)

+ EXTJS-25804 - Direct example doesn't report validation errors.

+ EXTJS-25782 - Direct doesn't load form data in live example

+ EXTJS-25774 - KitchenSink JSONP example fails to get weather data

+ EXTJS-25666 - Edge date picker persists on back button in Form Panel example in modern KS

+ EXTJS-25438 - Fails to load data in JSONP example

+ EXTJS-25477 - Formula in modern Tooltip example is not working

+ EXTJS-25412 - Legend sprite markers are too small in the Line with Markers example

+ EXTJS-25583 - Rating widget is not showing tooltip

+ EXTJS-25574 - Fails to load store source in Remote Combobox examlple

+ EXTJS-25610 - New tabs have incorrect generated number

+ EXTJS-25607 - Forum search example can't be scrolled back to top on touch devices

+ EXTJS-25398 - Changes on rating box don't have effect on the Rating cell

+ EXTJS-25388 - States don't load in Store details

+ EXTJS-24195 - Kitchen Sink throws exception on invalid route

+ EXTJS-25313 - Long names of examples are not fully visible in kitchensink

+ EXTJS-25312 - Advanced date panel won't adapt to window width

+ EXTJS-24984 - Improve styling of form in Dialog - iOS theme

+ EXTJS-24886 - sync config and checkbox state in Flexible Selection example

+ EXTJS-24051 - User is not able to redirect to forum pages from Forum Search example on touch devices

+ EXTJS-25247 - Tooltip align option example Tip and Target buttons have unreadable text

+ EXTJS-25101 - "Undoable Accordion Swiper" - "Swiper" word is not visible in KitchenSink when iOS theme is chosen

+ EXTJS-24938 - Remote ComboBox won't navigate to forum in touch devices

+ EXTJS-25246 - Rapidly clicking buttons in Toast example displays too many toasts

+ EXTJS-25260 - Right tab is clipped in Tree decorations example

### Exporter (7)

+ EXTJS-25749 - XLSX exporter does not properly encode special characters

+ EXTJS-25686 - Exporting XML in Exporter Plugin doesn't work on iPad

+ EXTJS-25558 - Excel pivot table class should generate a name

+ EXTJS-25626 - Poor performance when exporting large grid to XLSX

+ EXTJS-25403 - Dates exported in XLSX files do not import properly in Google Docs

+ EXTJS-25339 - Exporter produce corrupted XLSX when using Japanese saveDocumentAs titles

+ EXTJS-25349 - Exporter Excel03 does not export the correct value for booleans

### Forms (43)

+ EXTJS-25879 - Filefield does not receive red border when the field is invalid for certain themes

+ EXTJS-25887 - Input should be disabled when you tap on field trigger icon on Android

+ EXTJS-25896 - When tap on Combobox (or trigger), keyboard appear in Android tablet

+ EXTJS-25732 - Editing of numberfield - Cursor jump on last position after interaction

+ EXTJS-25895 - Contact Form - Cannot press button Browse by ENTER

+ EXTJS-25913 - Spinner field spinValue should be 1 to match classic

+ EXTJS-25670 - Cannot choose a value after the initial value with remote combo loading

+ EXTJS-25701 - Cannot re-select a previously selected value on combobox

+ EXTJS-25669 - Datepicker throws exception if the day slot is removed

+ EXTJS-25700 - Label as placeholder not positioned correctly on initially hidden fields

+ EXTJS-25694 - Forms using card layout and binding do not validate properly until all cards are visited

+ EXTJS-25671 - Datepicker doesn't set weekend day indicator correctly with startDay that isn't Sunday

+ EXTJS-25476 - No animation should be performed when field with placeholder label is blurred

+ EXTJS-25553 - Scroller showing incorrectly with auto growing TextArea

+ EXTJS-25425 - Date field throws error with invalid input

+ EXTJS-25485 - Custom error handling - passwordValidator doesn't work on empty text

+ EXTJS-25496 - Slider fires change event during construction

+ EXTJS-25587 - Spinner field cannot increment or decrement by arrow keys

+ EXTJS-25620 - Cannot type into numberfield in Safari 9

+ EXTJS-25611 - Buttons are not visible in Date Panels examples - tablets

+ EXTJS-25362 - Floating picker appears behind toolbar

+ EXTJS-25371 - Toggle field doesn't toggle correctly in a dialog with animation

+ EXTJS-25368 - Form layout does not respect configured labelWidth when label has wider text

+ EXTJS-25367 - Filefield "browse" does not set correct request payload for file uploads

+ EXTJS-25356 - field with inputMask throws error on blur

+ EXTJS-24446 - Typeahead not working on Combobox

+ EXTJS-23488 - Combobox's inputEl gets focused when the trigger is tapped on Android devices.

+ EXTJS-25300 - Cannot select item in bound list of modern toolkit combobox on mobile device

+ EXTJS-24948 - Combobox: hideTrigger has no effect

+ EXTJS-24477 - Checkout form - Numberfield - user can change just last digit of number

+ EXTJS-24490 - Ext.field.Toggle and slider flicker on rendering initial non-zero value

+ EXTJS-24180 - Field input mask - Key navigation doesn't work properly on Firefox

+ EXTJS-24019 - Should not immediately start field editing input field of picker when dismissing its popup

+ EXTJS-25052 - File input button text not visible in IE11

+ EXTJS-25014 - Date edge picker navigates to first item when tap above items

+ EXTJS-25193 - Placeholder labels incorrectly aligned in dialogs

+ EXTJS-25048 - Numberfield places decimal at the end

+ EXTJS-25205 - Input mask incorrectly appends user input in some cases

+ EXTJS-25199 - Modern textfield should not require all framework validators

+ EXTJS-25228 - Ext.field.Toggle change event does not provide newValue argument

+ EXTJS-25018 - DatePicker in mobile phones do not allow changing the year

+ EXTJS-15652 - Viewport resizes incorrectly with virtual keyboard open on Windows 8.1 / IE11, Android

+ EXTJS-23628 - Text field heights are incorrect, and text is misaligned, in Chrome 56

### Grid (55)

+ EXTJS-25763 - Column selection after a hidden column goes wrong after scroll.

+ EXTJS-25766 - Disable grouping menu options for tree stores and columns without dataIndex

+ EXTJS-25861 - Grid with rownumberer column allows hiding all "regular" columns with header menu

+ EXTJS-25835 - Nightly build throws 'Duplicate component name' with editors with the same dataIndex but in other grids

+ EXTJS-25747 - Clicking a row numberer cell will select a record even if setRows(false)

+ EXTJS-25767 - Columns with fixed width do not render cells properly after hiding and resizing

+ EXTJS-25725 - Home and End key doesn't work in the widget column fields

+ EXTJS-25756 - Expanding grid group throws exception with scrollable: false

+ EXTJS-25655 - Row selected by checkbox cannot be copied by ClipboardPlugin

+ EXTJS-25644 - Error when inserting container into grid header

+ EXTJS-25656 - Column sorting in header menu is disabled when column selection is enabled

+ EXTJS-25654 - Incorrect row height in Grid ViewOption plugin when column title has wrapping text

+ EXTJS-25640 - Cannot type space when editing cell in modern grid

+ EXTJS-25492 - Focus error on grid scroll in classic

+ EXTJS-25757 - Grid cell editor does not complete edit on blur

+ EXTJS-25459 - Cell editing validateedit event cannot be vetoed

+ EXTJS-25555 - Editing throws error in tree grid

+ EXTJS-25451 - Grid throws an error if cell binding executes after store has been nullified

+ EXTJS-25486 - Clicking check column's "check all" throws error in IE8

+ EXTJS-25488 - Row editing throws error when unlocking a locked column

+ EXTJS-25539 - Multiple sort arrows are not displayed in all themes in modern grid

+ EXTJS-25572 - Show error when changing value in the salary field at big data grid example

+ EXTJS-25593 - Changing the id of a selected record causes orphaned record in grid selection model

+ EXTJS-25630 - Correct width is not set when hide columns in drill down grid

+ EXTJS-25602 - Horizontal scrollbar is removed after collapsing and expanding locked side of grid

+ EXTJS-25358 - ItemSelector does not auto scroll when dragging an item

+ EXTJS-25351 - Grouped Grid with pinHeaders false throws error when header is clicked

+ EXTJS-25303 - menuDisabled for the CheckColumn is not set to true by default

+ EXTJS-23330 - CellEditing plugin editor.el.dom is null

+ EXTJS-20524 - HTML comment in grid cell data leads to error on value update

+ EXTJS-22414 - Double click on cell editor invisibly selects text on Windows

+ EXTJS-20980 - Classic grouped grid scrolls back to focused cell when user expands row

+ EXTJS-25302 - Column groupable config does not hide Group By This menu item

+ EXTJS-25318 - Grid editor being cleared by the Garbage Collector when it shouldn't

+ EXTJS-19567 - Rows with subpixel height in locked grid can become misaligned

+ EXTJS-25275 - Checkbox column performs badly when header checkbox clicked

+ EXTJS-24751 - Row numberer column should not appear in the column header menu

+ EXTJS-24620 - Grid editors should be able to specify extended CellEditor classes both as instances and configs

+ EXTJS-24409 - SpreadsheetModel throws an error when clicking in the grid just below rendered rows

+ EXTJS-24288 - Ext.dataview.Abstract.enableTextSelection config doesn't work.

+ EXTJS-24361 - Grid Rownumberer not working with bindable store in modern

+ EXTJS-24482 - Editor fields in Editable grid are not validated

+ EXTJS-23619 - Selecting partially visible column causes header and grid cells to scroll out of sync in locked grid

+ EXTJS-23363 - [Modern] Grid column has incorrect parameters for renderer

+ EXTJS-20461 - Column header alignment gets out of sync when collapsing groups in a locked grid

+ EXTJS-22637 - Grid refreshNode causes widget to be removed from the DOM

+ EXTJS-25258 - Flexible selection is lost after scrolling down and back up in IE11

+ EXTJS-25236 - Can't open SelectField when gridcelleditable is configured with triggerEvent: 'tap'

+ EXTJS-25251 - Cell editor combo box displays unwanted scrollbar when last item is focused

+ EXTJS-25268 - Grid "group by this" menu action does not work unless grid sets grouped config

+ EXTJS-25235 - Tree garbage collects widgets from WidgetColumn incorrectly on node collapse

+ EXTJS-25240 - Selection column should not have header menu

+ EXTJS-25147 - Click on column header with no dataIndex or sorter configured throws error

+ EXTJS-24963 - 'Show in groups' cannot be unchecked

+ EXTJS-16455 - Grid columns resize when using grid without fixed width and forceFit true

### Layouts (6)

+ EXTJS-25645 - Mousedown on a modal floated component when it has a floated child occludes the child

+ EXTJS-25683 - Flicker when transitioning from to hiding/showing scroll indicators when scrollbar has a size

+ EXTJS-25563 - East panel header is wrongly displayed on Safari / iOS

+ EXTJS-23460 - Able to scroll view behind modal mask in modern on iOS

+ EXTJS-24851 - Carousel swiping is slugish on phones

+ EXTJS-10622 - Container with frame: true causes Layout run failed in IE8/9 if no CSS framing was defined for that component

### List (13)

+ EXTJS-25833 - Error is thrown after swiping accordion list swiper back

+ EXTJS-25870 - NestedList: back button always goes to root after goToLeaf or goToNode is called

+ EXTJS-25511 - Error thrown after deselecting record in binded lists

+ EXTJS-25467 - List multi-selection should toggle item selection on tap

+ EXTJS-25406 - Tapping on index bar should scroll group to top

+ EXTJS-25639 - Indexbar indicator is not hidden after selection in IE11/Edge

+ EXTJS-25357 - PullToRefresh should react only to vertical gestures and list is scrolled to the top

+ EXTJS-25307 - dataMap does not assign data correctly

+ EXTJS-25277 - List items always have (hidden) disclosure tools even if not needed

+ EXTJS-25271 - Nested list breaks if you click back button fast

+ EXTJS-25152 - Pull to refresh list gets stuck

+ EXTJS-25223 - Cannot tab out of Basic list after focusing items with arrow keys

+ EXTJS-25192 - Items appear collapsed after store update when infinite: true and variableHeights: true

### Locale (1)

+ EXTJS-19995 - Incorrect overrides in Swedish Locale

### Menu (6)

+ EXTJS-25523 - Menu hides on global scroll, needs to be more granular

+ EXTJS-25387 - Datepicker in menu hides after choosing year/month on tablets

+ EXTJS-25361 - Using instanced menu as a submenu results in an error

+ EXTJS-25343 - Cannot click menu item of a button in a toolbar with trackMenus set to false

+ EXTJS-25319 - Menus in modern toolkit are documented as being weighted containers but do not set weighted:true

+ EXTJS-25200 - setMenu causes button element to be destroyed

### Misc (7)

+ EXTJS-25822 - ShowBy does not apply a default alignment

+ EXTJS-25697 - Modern viewport should not add the x-root cls to the documentElement

+ EXTJS-25719 - Responsive plugin sets a component's id

+ EXTJS-25292 - Modern toolkit should prevent scroll overflow to disable pull to reload on Android

+ EXTJS-25243 - Various elements in the UI are native browser selectable

+ EXTJS-25244 - Mashup throws exceptions on non-component classes

+ EXTJS-15042 - Ext.ux.IFrame cannot be made to scroll on iPad

### Panel (10)

+ EXTJS-25704 - Cannot remove panel header dynamically

+ EXTJS-25660 - Panel beforeexpand/collapse event doesn't veto correctly

+ EXTJS-25429 - Panel collapsed to the side has incorrect header width in Safari

+ EXTJS-25372 - Panel instance added to container doesn't bind viewmodel correctly

+ EXTJS-25353 - Splitter obscures scrollbar when using a panel with a UI

+ EXTJS-23990 - Incorrect titlebar height on several browsers

+ EXTJS-25301 - Quickly moving years in date panel can cause exception

+ EXTJS-24849 - Date panel is incorrectly displayed after selecting date - iOS10

+ EXTJS-20307 - The collapsed placeholder header does not respect the titlePosition config

+ EXTJS-25234 - Date panel styling issues (material)

### PivotGrid (6)

+ EXTJS-25631 - Drill down grid is not paged

+ EXTJS-25633 - Range Editor: blank value is displayed as Not a Number

+ EXTJS-25554 - Pivot grid expand/collapse all operations should disable events for better performance

+ EXTJS-25424 - Error in console when open Boundlist as RangeEditor

+ EXTJS-25276 - Aggregator functions should have an option of how to treat nulls

+ EXTJS-25284 - Error in console when Expand and collapse row after opening Range editor in Pivot grids

### Selection Model (2)

+ EXTJS-22576 - Tagfield should keep items in order as they are added to the inputEl

+ EXTJS-19866 - Pasting doesn't paste into the selection - only the selected field

### Tabs (3)

+ EXTJS-25693 - Adding closable config to extended Ext.Panel throws uncaught errors in TabPanel

+ EXTJS-25580 - Tab Panel - enable method should be chainable

+ EXTJS-25201 - TabBar layout config not applied correctly

### Templates (2)

+ EXTJS-25842 - Admin Dashboard Profile button icons are not centered on iOS

+ EXTJS-25734 - Admin Dashboard is moving when mouseover menu - scroll bar is showing and hiding

### Theme (8)

+ EXTJS-25408 - Check is not visible, if checkbox is focused, on Aria, Crisp theme

+ EXTJS-25494 - Not able to print multiple pages when using viewport

+ EXTJS-25416 - $button-badge-min-width assumes $button-badge-padding is not a list

+ EXTJS-25352 - Text color of active tab is incorrect when focused in modern neptune and triton themes

+ EXTJS-22783 - Breadcrumb button icon is overlapped with useSplitButtons: false in Triton

+ EXTJS-25131 - Icon Arrow Up (down) is missing in grid headers (iOS Theme)

+ EXTJS-25202 - OpenSans font not loaded in Triton theme

+ EXTJS-25083 - Floating action button (fab) ui is not round on mobile devices

### Tree (2)

+ EXTJS-24548 - Tree panel checkchange event fired twice when using checkPropagation

+ EXTJS-19821 - UI is not updated correctly when node is directly loaded

### Window (5)

+ EXTJS-25728 - Window resize should update size of window ghost

+ EXTJS-25590 - Showing a MessageBox repeatedly throws an error

+ EXTJS-21840 - Draggable items should not react to right mouse

+ EXTJS-24989 - Mask is not hidden when closing maximized dialog

+ EXTJS-24974 - Classic Window will not close on first tap on iOS

## Known Issues

### Tabs (1)

+ EXTJS-13538 - Ext.ux.TabScrollerMenu has not been updated to work in Ext JS 5 and 6

# Release Notes for Ext JS 6.5.0

Release Date: Thursday, May 11 2017  
Version Number: 6.5.0.775

## New Features

### App (4)

+ EXTJS-24277 - Support hashbang in app routing

+ EXTJS-22819 - Router should fire a global beforeroute event

+ EXTJS-24636 - The getApplication method should be available earlier

+ EXTJS-16051 - Router redirectTo should have a replace option to avoid adding to the history

### Bind (2)

+ EXTJS-22695 - ViewModel setData should always set the data on the called VM and should not climb to parents

+ EXTJS-22913 - ViewControllers should support declarative bindings into ViewModels

### Charts (2)

+ EXTJS-23228 - Candlestick series should support the 'renderer' config

+ EXTJS-24239 - Pie 3D series should have series and label renderer support

### Cmd (1)

+ EXTJS-24738 - All packages in extjs/SDK should be npm- and mondorepo-compatible

### Core (4)

+ EXTJS-16563 - Modern toolkit should support Ext.Editor

+ EXTJS-23242 - Add Ext.promise.Promise.catch

+ EXTJS-23472 - Component should provide maskDefaults config for setLoading

+ EXTJS-23158 - Ext.Promise - add race method

### Data (3)

+ Modern toolkit should be able to utilize a store that only fetches the pages needed by 
the views using it (virtual store).

+ Virtual stores should be able use a configured range. 

+ EXTJS-23231 - MemoryProxy should allow its data to be cleared after being read (clearOnRead)

### DataViews (1)

+ DataViews should be able to limit the amount of associatedData presented to the 
itemTpl and tpl

### Documentation (3)

+ EXTJS-22198 - Promote Toolbar trackMenus config to public and document

+ EXTJS-20444 - DockingContainer. initDockingItems should be marked as protected

+ EXTJS-23353 - Document Ext.Component#renderConfig

### Exporter (3)

+ EXTJS-23512 - Exporter should support an exportRenderer config for columns

+ EXTJS-20353 - Exporter should export grouped data and summaries

+ EXTJS-22627 - Column exportStyle should allow width to be specified

### Forms (8)

+ Form fields should have more succint rules for determining validity

+ EXTJS-16530 - Modern toolkit should support FieldSet

+ EXTJS-24437 - Include a textfield ui that makes searchfields look good in a titlebar

+ EXTJS-16528 - Modern toolkit should support TagField

+ EXTJS-16518 - Modern toolkit should support desktop-style ComboBox

+ EXTJS-23235 - Date picker week start day should default to Ext.Date.firstDayOfWeek

+ EXTJS-16521 - Modern toolkit should support TextField triggers

+ EXTJS-20896 - multislider setValue method should accept multiple values and create or destroy thumbs to match

### Grid (17)

+ Modern Grid should support spreadsheet-style selection
 
+ Modern Grid should support tools in cells
 
+ Modern Grid should support tools in row headers

+ Modern Grid should support tools in column headers

+ Modern Grid should support tools in grouped headers

+ Modern Grid should support column menus

+ Modern Grid should support tools in tree cell tools

+ Modern Grid should hide selection tools until needed

+ Modern Grid should support customizable grouping

+ Modern Grid should support summaries and summary models

+ Modern Grid should support pinned footers

+ Modern Grid should support row numbers

+ EXTJS-16549 - Modern toolkit grid should support Action column

+ EXTJS-16548 - Modern toolkit grid should support checkbox selection model

+ EXTJS-16539 - Modern toolkit grid should support inline cell editing

+ EXTJS-16581 - Modern toolkit grid should provide column drag reordering

+ EXTJS-24163 - Paging toolbar should be able to buffer page loads in modern grid

### Layouts (1)

+ EXTJS-23982 - Card layout should automatically choose the correct direction when animating between cards

### Lists (8)

+ Lists should support tool placement within list items

+ Lists should support an improved pullRefresh plugin

+ Lists should support auto-height

+ Lists should support infinite lists

+ Lists should support list item swiping

+ List swiping should have the ability to display an accordion menu

+ List swiping should have the ability to display different items based on the amount of swipe

+ List swiping should have the ability to undo the previous action

### Misc (6)

+ Modern toolkit should support the rating picker

+ EXTJS-18620 - Ext.util.Cookies should be in the core package

+ EXTJS-24012 - Automatically set ripple color based on context

+ EXTJS-22943 - Allow stores to be used inside formulas to calculate values when data changes

+ EXTJS-22677 - Modern toolkit should support form layout

+ EXTJS-22828 - ServerProxy should allow sorting or grouping fields and directions to be the same URL parameter (such as ?sort=name%20ASC)

### PivotGrid (1)

+ EXTJS-22908 - It should be possible to configure pivot grid rows and/or columns as collapsible:false

## Bugs Fixed

### Accessibility (2)

+ EXTJS-20408 - Grid NavigationModel incorrectly consumes F2 key with modifiers

+ EXTJS-23171 - Ctrl-Up arrow does not work in Grid and toolbar in Accordion child panel

### App (1)

+ EXTJS-17386 - store undefined while loading in a viewmodel formula

### Bind (6)

+ EXTJS-24322 - Bind expressions w/minus operators but no spaces are treated as identifiers instead of subtraction

+ EXTJS-23442 - Viewmodel formula doesn't parse arguments correctly when using inline named function

+ EXTJS-23286 - ViewModel doesn't get created if there are no bindings/publishes

+ EXTJS-19403 - Child viewModel saves undeclared root data on parent viewmodel

+ EXTJS-18892 - Calculated field function parser adds dependencies from code in comments

+ EXTJS-17254 - Store should deliver presence while loading to allow loadmasks to be shown

### Button (3)

+ EXTJS-25032 - Improve FAB hover style

+ EXTJS-22450 - Icon only buttons don't always center the icon

+ EXTJS-23682 - Text in buttons is missing in IE 11 modern

### Calendar (2)

+ EXTJS-23742 - [Calendar event] window for create/edit event didn't displayed

+ EXTJS-22697 - eventtap event not fired for calendar day/week view

### Charts (25)

+ EXTJS-24624 - Multiple radar series can not be added dynamically

+ EXTJS-24225 - Should prevent view scrolling when a D3 component is zoomed via mousewheel

+ EXTJS-24594 - Charts legend does not implement isFloating() method causing ZIndexManager to crash

+ EXTJS-23760 - Chart example loads with transparent background

+ EXTJS-23499 - addSeries throws an exception

+ EXTJS-23218 - Time axis: ticks don't match data points in certain cases.

+ EXTJS-22111 - Gauge chart does not scale properly when min/max are close

+ EXTJS-22142 - Colors for Gauge are not respected in legend

+ EXTJS-22318 - Point labels are not positioned correctly when rotation config set in radar chart

+ EXTJS-17104 - When a pie chart displays only one slice, the border of the slice creates a vertical line

+ EXTJS-15893 - Series 'highlight' config should be themable

+ EXTJS-20426 - Chart numeric axis does not respect minimum when adjustByMajorUnit is true & minimum > 0

+ EXTJS-22518 - Line series with smoothing does not render correctly

+ EXTJS-22320 - Radar chart incorrectly sets rotation

+ EXTJS-19788 - Radar chart shows incorrect data if there are multiple series and no min/max is provided

+ EXTJS-22319 - Setting rotation causes style to revert back to default in radar chart

+ EXTJS-20807 - Radar marker misplaced when value equals 0

+ EXTJS-20109 - itemhighlight/change should be consolidated into a single event and fired consistently

+ EXTJS-23136 - Rotated labels randomly not rendering in Charts

+ EXTJS-15671 - Column chart - limit line not cleared when store cleared

+ EXTJS-20496 - Pie chart labels for very small slices can overlap

+ EXTJS-24106 - Modern Gauge example is broken in Safari

+ EXTJS-24085 - Bar chart throws an exception when extending Ext.chart.axis.Category

+ EXTJS-23720 - Modern Area Basic example doesn't work on mobile

+ EXTJS-23824 - Modern chart dataview legend can neither scroll nor wrap when overflowing container.

### Core (5)

+ EXTJS-25064 - Ext.Function.interval does not honour scope parameter

+ EXTJS-24832 - Component keyMap definitions are duplicated on each instance

+ EXTJS-22553 - Ext.ComponentQuery.query() with no selector throws exception

+ EXTJS-20525 - Resizing elements next to an iframe will lose track of mouse move

+ EXTJS-21141 - Ext.util.CSV.decode doesn't recognize the first column value when it is blank.

### D3 (5)

+ EXTJS-23911 - D3 components don't respond to shrinking

+ EXTJS-23797 - Source click doesn't work on mobile phones

+ EXTJS-24017 - Treemap won't load correctly

+ EXTJS-23940 - HeatMaps shouldn't have layout transition on resize

+ EXTJS-23877 - Heatmap layout is not responsive

### Data (9)

+ EXTJS-23647 - Model getValidation.isValid() can be incorrect when using cancelEdit

+ EXTJS-23140 - data.Reader should not cache extractors when using anonymous classes

+ EXTJS-17728 - Ext.data.Session's recordCreator does not update existing, unmodified records with new data

+ EXTJS-20648 - Stateful grid with buffered store, autoLoad:true, and sorters loads twice

+ EXTJS-20025 - Ext.data.Session ignores proxy batchActions setting

+ EXTJS-23102 - Model dependencies are not correctly recalculated in some cases when using replaceFields

+ EXTJS-23044 - If an associated store is referenced before a model is load, the data is not loaded into the store correctly

+ EXTJS-23033 - Changing the group of a record can throw an exception when using a chained store

+ EXTJS-23558 - Some ChainedStore methods can fail when no source is attached

### DataView (4)

+ EXTJS-24560 - Unhandled exceptions when navigating in grid using HOME/END keys

+ EXTJS-23467 - List scrolls to the top when items are inserted or deleted

+ EXTJS-23685 - Horizontal DataView can not be scrolled

+ EXTJS-23560 - Grouped list throws an exception when clearing the associated store

### Documentation (24)

+ EXTJS-24801 - Documentation of Ext.layout.Box configs is not visible

+ EXTJS-23404 - Toast show position does not match documentation

+ EXTJS-23384 - Grid feature code example incorrectly marked as runnable

+ EXTJS-23368 - Ext.carousel.Carousel directionLock config not documented

+ EXTJS-23484 - expanderFirst missing from Ext.list.Tree docs

+ EXTJS-23465 - Wrong var name for $form-toolbar-text-field-invalid-border-color

+ EXTJS-23224 - Improve documentation for undefined values

+ EXTJS-23172 - Window.floating does not inherit documentation correctly

+ EXTJS-23259 - Modern Ext.grid.Grid - itemConfig marked as private, but referred to in docs

+ EXTJS-22632 - Ext.data.Store removeAll should make it clearer that it is affected by filtering

+ EXTJS-22784 - Messagebox show documentation has incorrect parameter name

+ EXTJS-21059 - Rating picker limit config default is incorrect

+ EXTJS-22825 - Ext.data.BufferedStore beforeload and load events should be clarified and referenced to before/prefetch events

+ EXTJS-22730 - Ext.util.Filter code example comments have inaccurate comment statements

+ EXTJS-23092 - asUCText duplicated

+ EXTJS-22689 - Ext.data.proxy.Server -> exception indicates the request is returned but should be response

+ EXTJS-21246 - Ext.grid.filters.filter.Boolean value shouldn't be quoted

+ EXTJS-19637 - Documentation should clarify that BufferedStore is not supported on the Modern Toolkit

+ EXTJS-23015 - Mashup example documentation should show mixins as an array of strings

+ EXTJS-23075 - Add default to columnLines doc entry

+ EXTJS-23869 - Documentation - displayfield - submitValue has incorrect default value

+ EXTJS-23960 - Options and Parameter are not currently producing documentation.

+ EXTJS-23583 - Missing pie label display "inside" config

+ EXTJS-23352 - The "beforedestroy" event documentation needs to include a warning about vetoing

### Draw (2)

+ EXTJS-22883 - Draw container with SVG Engine throws uncaught errors when trying to download

+ EXTJS-22609 - Animation modifier throws on Edge referencing triggers on destroyed sprite

### Events (1)

+ EXTJS-22261 - Ext.event.Event.within disregards allowEl paramater

### Examples (14)

+ EXTJS-24242 - Value is not visible when textfield is too small on Triton theme

+ EXTJS-24536 - Prevent tap event propagation in picker list

+ EXTJS-24120 - [D3] Pivot Heatmap example is not loaded correctly

+ EXTJS-23616 - Incorrect rounding in two-way formulas

+ EXTJS-23279 - Menu fields not disappearing after picking one while window is resized

+ EXTJS-22360 - Vector icons are not properly aligned

+ EXTJS-20922 - BoxReorderer plugin doesn't work in RTL mode

+ EXTJS-24071 - Update Custom error handling example for modern toolkit

+ EXTJS-23996 - Wrong functionality for spinners in two-way formulas example

+ EXTJS-24070 - Ticket App - Icon for button search is not displayed

+ EXTJS-23727 - Elements initial position is out of constrained area

+ EXTJS-23870 - Hide then expand code preview in KS leads to unresizable panel

+ EXTJS-23979 - D3 example should not be presented on IE8/9

+ EXTJS-24000 - Error thrown when destroying Easing example

### Exporter (3)

+ EXTJS-24351 - The xlsx files generated by exporter are not visible in iOS Safari

+ EXTJS-23405 - When exporting grid, zeros are exported as blanks

+ EXTJS-23300 - Grid Exporter should ignore hidden columns

### Forms (25)

+ EXTJS-24683 - Error thrown as you type to number/email field - Chrome

+ EXTJS-25042 - Combobox with labelAlign="placeholder" doesn't keep label elevated when value is set

+ EXTJS-25009 - Selectfield/Combobox should not allow value deselecting when using list picker

+ EXTJS-24866 - Label misaligned when using labelAlign: 'placeholder'

+ EXTJS-24699 - Number field, enter in value above max value will not update input

+ EXTJS-24604 - selectfield cannot be opened in sheet on touch devices

+ EXTJS-24131 - Date is not changed by datepanel picker

+ EXTJS-24538 - Picker fields should open on touchend and allow form scrolling

+ EXTJS-24570 - Numeric validator shows invalid when field is blank

+ EXTJS-23445 - TextArea doesn't propagate enter key

+ EXTJS-23617 - When focused the regular placeholder should be displayed even if labelAlign is 'placeholder'

+ EXTJS-21116 - Datepicker header background color undocumented

+ EXTJS-22670 - Hidden field crashes when created

+ EXTJS-18335 - Field emptyText isn't correctly html encoded

+ EXTJS-21245 - Textarea preventScrollbars disables grow

+ EXTJS-21257 - Cannot specify a renderer string for display field

+ EXTJS-23120 - Cannot upload a file with form submit on Firefox and IE11

+ EXTJS-22968 - Text field focus method doesn't select text correctly when passed a selection range

+ EXTJS-22954 - DateField getValue() should return a Date with cleared time values based upon format config

+ EXTJS-23924 - Displayfield does not add a line break after commas

+ EXTJS-24056 - Selection doesn't work with two items in selectfield on iPhones

+ EXTJS-23677 - Selectfield does not properly apply bind value when using a restful store

+ EXTJS-23662 - Textarea field does not adhere to growMin at init

+ EXTJS-23976 - Placeholder label is not visible when switching between fields

+ EXTJS-23692 - standardSubmit does not post correctly

### Grid (52)

+ EXTJS-24735 - setExtensible does affect a current selection

+ EXTJS-25089 - Shift+Tab in first editable cell crashes browser tab

+ EXTJS-24471 - Focus error thrown after opening column menu in grid header menu

+ EXTJS-24578 - Grid DragDrop#containerScroll true not working

+ EXTJS-24470 - Grid row remains focused after scrolling out of view

+ EXTJS-24686 - Error thrown when you navigate from first or last row in grouped grid

+ EXTJS-24468</span>  <span class="ticket-notes">Locked grid scrolls to top if you click on a partially exposed cell in normal view

+ EXTJS-24589 - Grid mutates an incoming dockedItems array by unshifting its HeaderContainer into it

+ EXTJS-24496 - Columns are offset to the right on tablets and phones

+ EXTJS-24252 - Trigger icons of pickers used in celleditors are not visible

+ EXTJS-24102 - Modern grid column reorder doesn't update columns in grid body

+ EXTJS-24453 - RowBody presence in grid should imply variableHeights: true

+ EXTJS-23375 - Can't bind store to grid with paging toolbar

+ EXTJS-23695 - Rownumberer column is placed at end of columns in locked grid

+ EXTJS-23461 - List filter with a non array value doesn't have initial value set correctly

+ EXTJS-23687 - Missing scrollbar in some pivotgrid

+ EXTJS-23345 - Tabbing from a celleditor will move misalign the unlocked portion of a grid

+ EXTJS-23311 - Error thrown when hiding column which contains selection extension handle.

+ EXTJS-23373 - Buffered Store reload throws error when holding 1 record

+ EXTJS-23413 - Navigation via keyboard arrows can misalign columns in lockable grid

+ EXTJS-23576 - Collapsing a group while editing throws an error

+ EXTJS-23377 - After a load caused by auto-paging, 1 or 2 items are missing on top of the grid.

+ EXTJS-23238 - Unlocked portion of lockable grid scrolls horizontally when editor is activated

+ EXTJS-23212 - Grid header does not scroll with view when cellediting is active

+ EXTJS-23453 - Hidden column state in locked grid can result in layout failure

+ EXTJS-23152 - Ext.grid.filters.filter.Boolean: Filters checkbox does not correctly apply default filter

+ EXTJS-23269 - Editing plugin crashes when editing and then clicking on a widget

+ EXTJS-23127 - Non-collapsing grid groups shouldn't have tips about collapsing

+ EXTJS-23301 - Locking Grid: Unable to scroll horizontally via scroll buttons in normal grid

+ EXTJS-22911 - RowExpander does not properly display when only plugin used in Modern grid

+ EXTJS-22822 - Column#cellFocusable allows focusing the cell when using a focusable widget

+ EXTJS-21488 - Header is scrolled into view when trying to resize - IE

+ EXTJS-23236 - Rowbody throws an exception when reconfiguring columns while not rendered

+ EXTJS-21855 - Accesses to window.top should be guarded for cross-domain restrictions

+ EXTJS-23217 - Stateful Grid with enableLocking and no locked columns does not apply column width correctly

+ EXTJS-20484 - Ext.grid.Panel.sealedColumns has no effect

+ EXTJS-23248 - Grid in collapsed container throws an exception while reconfiguring columns when not laid out

+ EXTJS-20539 - Having a grid with greater than 250 columns causes the grid to misalign headers

+ EXTJS-23187 - Grid checkbox selection doesn't select row correctly with gridviewdragdrop plugin

+ EXTJS-18993 - Sorting column removes active filters

+ EXTJS-23178 - Summary feature corrupts grid when not docked and used with GroupingSummary

+ EXTJS-22727 - RowNumberer does not respond to store insertions/removals

+ EXTJS-22648 - Grid widgets disappear and cause misaligned rows on column sort

+ EXTJS-15537 - Property name "value" breaks editors in Ext.grid.property.Grid

+ EXTJS-21292 - BufferedStore / SpreadsheetModel throws exception when reconfiguring a grid with a selected cell

+ EXTJS-23030 - Widget column cannot bind to hidden state correctly when loading a new dataset

+ EXTJS-22975 - Column header bindings fail on moved grid column

+ EXTJS-23702 - Scrolling in buffered rendered grid is broken by chrome 56 release (Classic)

+ EXTJS-24374 - Grid scroll partners not in sync in certain situations.

+ EXTJS-23865 - Grid columns do not get hidden when using Columns visibility menu

+ EXTJS-23457 - Vertical scrolling by scroll buttons produces abnormal horizontal scroll/jump

+ EXTJS-23786 - RowExpander not getting added to the grid

### Layouts (4)

+ EXTJS-24628 - Expanding a collapsible panel with hideCollapseTool throws error

+ EXTJS-22722 - Ext.Msg can produce viewport scroll

+ EXTJS-23088 - Grid with BufferedStore throws error when heighted by viewport

+ EXTJS-23821 - Card layout in Modern shouldn't create an animation instance when `animation` config is falsy

### List (1)

+ EXTJS-25008 - Swipe in Pull Refresh list cause error in console in non-material theme

### Menu (2)

+ EXTJS-24672 - Tap won't open child menu of menucheckitem

+ EXTJS-24170 - Menu items do not respect a group value in the menu's defaults config

### Misc (41)

+ EXTJS-24982 - View Options plugin column option indicators are not aligned correctly

+ EXTJS-24710 - Nested list editor has an extra button

+ EXTJS-24451 - Tab badges are clipped

+ EXTJS-24664 - Opening menu throws error on iPhones

+ EXTJS-24584 - Columns cannot be sorted when open View Option

+ EXTJS-24101 - [Simple Actions] Message alert is not displayed

+ EXTJS-24100 - Toasts not working properly in Safari

+ EXTJS-24117 - Preview/Download button don't work at Nobel Prize example

+ EXTJS-24122 - Focused spinner field is few px larger, causing remaining content to move

+ EXTJS-24133 - DrillDown: mask is not hidden when hide plugin

+ EXTJS-24432 - Unbound ripples are clipped

+ EXTJS-23757 - Google map is not correctly centered on initialization

+ EXTJS-23749 - [Datepicker] It doesn't show pickerslots for change date

+ EXTJS-24321 - Chained combo - value is not changed when switch first combo

+ EXTJS-23222 - Textfield with selectOnFocus: false puts cursor at end of field, not mouse click position

+ EXTJS-23339 - Remove LazyItems plugin from modern documentation

+ EXTJS-23125 - TextField's content gets selected onFocus when selectOnFocus is false

+ EXTJS-19856 - Combobox with paging toolbar clears input field after next page button is pressed

+ EXTJS-20073 - Store.rejectChanges() after a Store.remove() restores records in wrong order

+ EXTJS-23159 - ensureVisible automatically scrolls element to center not minimum needed

+ EXTJS-24075 - Cannot select row on second time on touch devices and emulation

+ EXTJS-24054 - Body container is not displayed in Data examples on iPhones

+ EXTJS-24077 - Wrong row selection on touch devices

+ EXTJS-23997 - In Right-To-Left RTL example sort icons are not present

+ EXTJS-24013 - Ripple animations pause when element is hidden, resume when shown

+ EXTJS-23883 - Checkout Form: same billing address doesn't work correctly

+ EXTJS-24243 - Last item in Picker (Overlays) can't be selected in non-Chrome browser

+ EXTJS-23846 - Click events are not being triggered in Firefox/Windows/Touch Monitor

+ EXTJS-24130 - Modern Segmented button doesn't handle false value properly

+ EXTJS-23799 - Drag field to Grid - > Drag this date has no effect after action

+ EXTJS-24304 - Method signature for Ext.form.field.Picker onTriggerClick is inconsistent

+ EXTJS-23735 - BadgeText covers button text in Material Theme

+ EXTJS-23768 - Phone viewport should not be scrollable

+ EXTJS-23929 - Pivot Grids: horizontal scrollbar is missing on IE/Edge

+ EXTJS-23781 - Expander should be vertically centered

+ EXTJS-23771 - Error when destroying carousel

+ EXTJS-23882 - Reconfigure grid - Error in console after show some grid.

+ EXTJS-23819 - Cannot scroll in combobox menu

+ EXTJS-23785 - TreeList singleExpand: true doesn't expand clicked node

+ EXTJS-23758 - Charts: preview of SVG charts is broken

+ EXTJS-24055 - [Forum Search] Error is displayed when enter text to combobox

### Panel (6)

+ EXTJS-23451 - Panel mutates passed tool configuration

+ EXTJS-23593 - Cannot reorder docked items

+ EXTJS-23175 - Custom Accordion panel tools have erroneous background image in Triton theme

+ EXTJS-23176 - Focused accordion header tool outline is too light in Neptune and Triton

+ EXTJS-17697 - Panel.ShowBy(...) not working if panel.left is not set

+ EXTJS-23588 - Panel.setTitle has no effect in TabPanel

### PivotGrid (15)

+ EXTJS-24319 - Pivot should use the aggregator functions defined on the Configurator fields

+ EXTJS-24128 - Export (or Download in Chart) doesn't work on Safari desktop

+ EXTJS-24237 - Pivot grid should be reconfigurable via setMatrix

+ EXTJS-23291 - Modifying pivotconfigurator can remove labelRender

+ EXTJS-23669 - [Configurator plugin] Sort switch doesn't work

+ EXTJS-23249 - Dirty indicator remains visible on pivot grid after committing changes to store

+ EXTJS-23602 - Defining more than two topAxis columns will throw uncaught length errors

+ EXTJS-23587 - Pivotconfigurer plugin throws error when removing pivotgrid before displayed

+ EXTJS-22844 - Pivot grid displays duplicate data after adding new records to the store

+ EXTJS-23096 - setStore on pivot grid does not work correctly

+ EXTJS-24129 - Tabular pivot: person names duplicate when sort

+ EXTJS-23598 - Using drag and drop in Configurator plugin should move fields between lists

+ EXTJS-23806 - Outline Pivot grid cells should be empty

+ EXTJS-23674 - CellEditing plugin does not work with the Configurator plugin in a classic pivot grid

+ EXTJS-23747 - [PivotGrid exampels] They aren't scrollable in horizontal direction

### Scroller (2)

+ EXTJS-23182 - Asking for scroll position after calling scroll prevents scroll partners from invoking

+ EXTJS-22559 - Unable to scroll items in a carousel

### Selection Model (1)

+ EXTJS-23913 - Cannot check rows in checkbox selection model with checkOnly:false - Firefox

### Tabs (2)

+ EXTJS-24659 - Configuring activeItem on tabpanel does not work in modern

+ EXTJS-23129 - Switching tabs during removal causes too many layouts

### Theme (7)

+ EXTJS-24461 - Action button in a floating toolbar does has same color as background

+ EXTJS-19641 - Triton theme tool icons overlapping

+ EXTJS-17080 - Neptune theme missing required images

+ EXTJS-24069 - Improve error message styling

+ EXTJS-24021 - Incorrect element size in IE11

+ EXTJS-24168 - Incorrect menu width in IE11

+ EXTJS-24096 - Tree icons are not rendered properly on iOS theme

### ToolTips (1)

+ EXTJS-22501 - Anchor background positioned wrong on Safari

### Toolbars (2)

+ EXTJS-24834 - Toolbar for audio is not displayed on Android mobile

+ EXTJS-22566 - Cannot check checkboxes when moved into a toolbar overflow menu

### Tree (6)

+ EXTJS-24869 - TreeList nodes expanded when setting selection cannot be collapsed

+ EXTJS-23659 - Invalid CSS selector generated for TreeList item

+ EXTJS-23164 - Tree List with filtered store causing error on expand/collapse

+ EXTJS-20650 - Expand/collapse an auto height tree with a maxHeight scrolls to top on refresh

+ EXTJS-23031 - Exception is thrown when collapsing a node in a filtered TreeGrid

+ EXTJS-23842 - Nav, Micro buttons and bottom treelist-log are missing in TreeList example

### Window (3)

+ EXTJS-24211 - Ext.Msg.alert has wrong position

+ EXTJS-23592 - Modal mask is not expanded to cover the background of a moved window in IE11

+ EXTJS-23124 - Window.show of already visible window doesn't bring it to front automatically

### container (1)

+ EXTJS-24375 - setHtml content does not honour component innerElement padding


## Known Issues

### Accessibility (13)

+ EXTJS-10477 - HtmlEditor is not accessible

+ EXTJS-10498 - Grid RowBody feature is not accessible

+ EXTJS-10495 - Locking grid is announced as two separate widgets by screen readers

+ EXTJS-10492 - DragDrop is not accessible

+ EXTJS-10497 - Grid row expander is not accessible

+ EXTJS-10480 - Color Picker is not accessible

+ EXTJS-10499 - Grid CheckboxSelectionModel is not accessible

+ EXTJS-10503 - Grid headers cannot be resized using the keyboard

+ EXTJS-10494 - Grid grouping feature is not accessible

+ EXTJS-10451 - Tree component does not support ARIA expanded state

+ EXTJS-10467 - Menu overflow scrollers are not navigable using the keyboard

+ EXTJS-10475 - ToolTip is not accessible

+ EXTJS-10504 - Grid Headers cannot be reordered using the keyboard

### Core (1)

+ EXTJS-21139 - View incorrectly resized when changing screen orientation while the virtual keyboard is shown

### DataView (1)

+ EXTJS-12345 - ComboBox's bound list becomes transparent on second show on iPad

### Tabs (1)

+ EXTJS-13538 - Ext.ux.TabScrollerMenu has not been updated to work in Ext JS 5 and 6

### Theme (1)

+ EXTJS-17790 - Triton should support tree lines</span>
