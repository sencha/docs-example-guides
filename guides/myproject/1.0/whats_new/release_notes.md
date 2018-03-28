<style>
.toc-page{
    display:none !important;
}
</style>

# Release Notes for Ext JS 6.0.2

Release Date: March 29th, 2016

Version Number: 6.0.2.437

## Noteworthy

`Ext.grid.plugin.CellEditing` now fires beforeedit and edit before moving to the next cell while tabbing. With 
`Form Field` components in a `CellEditor`, if you were using `beforeedit` to prevent the completion 
of the edit for a previous cell, now you should use the `validateedit` event instead.

## New Features

Accessibility (1)

+   EXTJS-16862   Display fields should be accessible
    
Charts (1)

+   EXTJS-16706   Chart line series should allow missing data points to be treated as zero or connected through instead of only renderable as a gap
    
Documentation (2)

+   EXTJS-17155   Store.onProxyLoad should be public
+   EXTJS-17418   Component.addPlugin method should be protected

Forms (1)

+   EXTJS-19511   The column's editor config may now be configured with a "field" property. If this is the case, the editor config is used to create the CellEditor, and the field property to create the input field.

Grid (2)

+   EXTJS-16552   Modern toolkit grid should support column resize grip
+   EXTJS-18860   Grid selection binding should be supported in Cell and Spreadsheet selection models

## Bugs Fixed

Accessibility (8)

+   EXTJS-18835   Mouse click on grid expander adds outline on both cell and icon.
+   EXTJS-19476   If FocusableContainer's last focused element is removed, it is no longer tabbable.
+   EXTJS-19495   Reconfiguring grid makes header container untabbable
+   EXTJS-19517   Toolbars should use group role when opting out of FocusableContainer behavior
+   EXTJS-19530   Closable tabs should be considered non-accessible
+   EXTJS-19616   ARIA checks inconsistent across components
+   EXTJS-19702   Shift+TAB into TableView which contains tabbables doesn't work
+   EXTJS-19758   NVDA announces Date picker as editable
    
App (4)

+   EXTJS-13843   menucheckitem breaks #route on Nexus7
+   EXTJS-18763   Refs with autoCreate: true do not get reinstated correctly after destroy
+   EXTJS-18865   redirectTo with force triggers routes twice if the route is already active
+   EXTJS-19273   Controller gets created twice when calling getController with short alias
    
Bind (4)

+   EXTJS-19001   Bindings fire repeatedly for same date value
+   EXTJS-19451   Combobox text input gets cleared in some cases when using forceSelection
+   EXTJS-19528   Session does not spawn correctly from parent when used with a fieldset with a legend
+   EXTJS-20622   Destroy method does not remove bindings
    
Button (4)

+   EXTJS-18048   In Aria Demo > Tab Item selector - click on button throws error in the console
+   EXTJS-19378   Disabled state is not reflected correctly in menu items when using box menu overflow
+   EXTJS-20094   SplitButton arrowEl focusable by default when arrowVisible configured false
+   EXTJS-20641   Button text property overrides overflowText property
    
Charts (9)

+   EXTJS-16954   majorTickSteps are not rendered properly on numeric axis
+   EXTJS-18063   calloutLine: false not respected
+   EXTJS-18861   3D Pie series can blink when animating or interacted with, when SVG engine is used.
+   EXTJS-18900   Polar/Pie Chart reports incorrect item and tooltip when data value is zero
+   EXTJS-19254   Pie chart rendering breaks if it's shrunk to the point where series are no longer visible, even after the original size is restored.
+   EXTJS-19822   Changing fillOpacity of chart series has no effect
+   EXTJS-20018   Destroying animated charts can throw uncaught errors
+   EXTJS-20104   Always zero index in gauge series' renderer in latest nightly
+   EXTJS-20158   Plot Charts - Buttons are disabled. Cannot be pressed

Core (16)

+   EXTJS-19201   Ext.coerce isn't correctly evaluating false == '0' (a one character string containing zero)
+   EXTJS-19212   Ext.util.MixedCollection $extCollectionIndex not being removed from item when sorted
+   EXTJS-19341   Delegated events don't fire correctly on containers with an itemId
+   EXTJS-19349   Target is null when item is dropped outside browser window - Win10 tablet
+   EXTJS-19355   Compatibility property on overrides does not accept string array
+   EXTJS-19460   Flicking scrollbar on touch screen devices results in content moving opposite way.
+   EXTJS-19544   Ext.util.TSV/CSV#decode goes infinite loop with an empty input
+   EXTJS-19640   Floaters with alignTo scroll outside the scrolling element
+   EXTJS-19697   Message box show with empty title shows previous title
+   EXTJS-19728   AMF0 and AMF3 formats don't load
+   EXTJS-19820   Removing a buffered listener during the event firing throws an error.
+   EXTJS-20039   Ext.Loader deadlock detecion is not reliable
+   EXTJS-20056   Toast not visible in Modern Triton Theme
+   EXTJS-20245   SVGElement.offsetParent deprecated in V48
+   EXTJS-20449   Inheritable statics from mixin are not inherited properly
+   EXTJS-7419   callParent does not work with inheritableStatics

Dashboard (1)

+   EXTJS-19634   Dashboard component incorrectly positioned by drag and drop

Data (25)

+   EXTJS-15462   Heterogeneous trees do not use proxy of child nodes to read their children
+   EXTJS-17125   Automatically update association store filter when owning model is saved
+   EXTJS-17902   Root firstChild/lastChild properties contain wrong nodes
+   EXTJS-18711   List grid filter: an options store created from an options list config shouldn't update when the store changes
+   EXTJS-18750   Incorrect getter is created for inverse side of hasMany association with a specified name
+   EXTJS-19102   Foreign key of associated models is not updated when record is saved
+   EXTJS-19146   Store.each is not safe for record removal
+   EXTJS-19221   Modifying id of record in group store can duplicate the item in some circumstances
+   EXTJS-19260   ManyToOne association doesn't read nested empty data collection as complete
+   EXTJS-19292   Ajax request fail on local files when status == 0
+   EXTJS-19310   Store fires metachange event prior to reconfiguring for new fields and still has old data
+   EXTJS-19345   Grid with auto height using a chained store does update height when new records are added
+   EXTJS-19406   Ext.data.Store leaks memory and sorts removed groups
+   EXTJS-19448   Changing a foreign key in hasMany causes exception when record is joined to multiple parties
+   EXTJS-19583   Setting root of TreeStore after a filter has been applied cannot read 'isExpanded' property of null sibling node
+   EXTJS-19699   Remote proxy does not send store filters whose value is falsy
+   EXTJS-19857   Syncing store throws JS error if trackRemoved = false
+   EXTJS-19911   Webstorage/LocalStorage not serializing data
+   EXTJS-19942   Grouped ChainedStore does not update record id correctly on server sync
+   EXTJS-19959   Session does not auto-include records in store for ManyToOne when the owner record is a phantom
+   EXTJS-20030   Ext.data.Validation should always be true for instances of the Ext.data.Model base class
+   EXTJS-20031   Shared id generators are not shared by models within same session
+   EXTJS-20262   BufferedStore not requesting enough pages on reload
+   EXTJS-20271   filterFn is removed for filters that specify value or operator via binding
+   EXTJS-20309   Ext.data.proxy.Proxy does not call base destroy()

DataView (3)

+   EXTJS-18932   DataView doesn't react to store updates when pending a refresh while not visible and can lead to exception
+   EXTJS-19132   List index bar scrolls out of view when using native scroller
+   EXTJS-20519   Typo in AbstractView

Draw (1)

+   EXTJS-19592   Image Sprites do not fire sprite events

Events (7)

+   EXTJS-17947   'single' event listener isn't unbound on devices that support mouse & touch
+   EXTJS-18435   mouseenter/mouseleave events never fires with delegate event option defined
+   EXTJS-18712   Managed listeners for translated events cannot be removed
+   EXTJS-19133   TaskRunner can sometimes fire idle event, even when fireIdleEvent is configured to false on IE
+   EXTJS-19223   Mouse wheel events don't fire correctly in Firefox
+   EXTJS-19649   resumeEvent should use canonicalEventName
+   EXTJS-20303   App for financial chars freezes when user try to use zoom feature

Examples (14)

+   EXTJS-15863   SimpleTask example>Menu button immediately lose focus after click
+   EXTJS-17543   ColorSelector UX does not render all sliders correctly
+   EXTJS-17748   Live Search Grid Example - missing checkboxes
+   EXTJS-18245   Modern example - Big data grid - slider at the last page can't be moved back by button
+   EXTJS-18815   BigData - Data doesn't change when modifying record via editor plugin
+   EXTJS-18818   Custom drag&drop - error in console when dropping same patient twice in the same place - IE8
+   EXTJS-18898   Subtable plugin border not shown correctly on firefox
+   EXTJS-19237   Wrong focus on row after adding new one on changed sorting in KS cell editing example
+   EXTJS-19335   Ext.ux.ajax.Simlet does not return configured response headers
+   EXTJS-19432   The Feed Viewer example doesn't load - error 404
+   EXTJS-19597   KS Calendar issue when change from Daylight to Standard
+   EXTJS-20211   Error when in console when switching from breadcrum toolbar to tree view in kitchen sink main window
+   EXTJS-20376   DataView - Sometimes chosen items are not selected
+   EXTJS-20416   can't drop in Custom Drag and Drop example

Forms (50)

+   EXTJS-15307   UpdateRecord causes checkbox values in model to be true/false instead of inputValues
+   EXTJS-15750   Ext.form.field.Time not being validated onChange and onBlur
+   EXTJS-17201   Combobox tab key does not cause component to lose focus on FF
+   EXTJS-17471   createNewOnEnter should not create new tag when some value in dropdown list is selected
+   EXTJS-17779   ComboBox forceSelection is too aggressive in clearing out the field input
+   EXTJS-17976   Region collapses when picker in region has mouseover
+   EXTJS-18014   Ext.form.Basic should require Ext.form.action.StandardSubmit
+   EXTJS-18034   textfield selectOnFocus doesn't work properly
+   EXTJS-18055   lastSelectedRecords forces selection in assertValue. Should be cleared on value change.
+   EXTJS-18509   When using touch screen, invalid form field causes form to jump to top when using mouse
+   EXTJS-18574   2 or more Comboboxes with paging toolbar causes id collisions
+   EXTJS-18654   ComboBox doQuery() always returns true
+   EXTJS-18786   Placeholder hasn't right color on touch device
+   EXTJS-18847   MultiSelect component loses item selection when using scroolbar in IE
+   EXTJS-18997   validate method of Ext.data.validator.Validator is not passed the record argument when form field is validated
+   EXTJS-19014   datefield "Today" button is enabled if date is outside of min/max range
+   EXTJS-19024   Previously selected date is not highlighted in modern datepicker
+   EXTJS-19119   When column is configured with align:right, Ext.grid.RowEditor overwrites user-defined fieldStyle configured on editor
+   EXTJS-19250   Ext.picker.Date not setting initial value
+   EXTJS-19271   Tag field with multiSelect: false throws console error
+   EXTJS-19274   ComboBox collapsing as typed characters match item when binding the combo's value
+   EXTJS-19317   Tag field should clear typed value when it matches selection
+   EXTJS-19318   Tag field with typeAhead and autoSelect selects incorrect record
+   EXTJS-19353   Ext.ux.colorpick.Field / can't load form values if value is null
+   EXTJS-19433   File upload via form.submit() not processing response correctly
+   EXTJS-19453   TagField Highlighting selection on typing is not working
+   EXTJS-19469   Selectfield does not automatically scroll to selected value on display
+   EXTJS-19487   Combobox typeahead types ahead on erase
+   EXTJS-19514   File field without fixed "name" fails on second upload.
+   EXTJS-19529   Combobox input not set when displayField set in initComponent
+   EXTJS-19595   queryMode:'remote' ComboBox does not fire change when query changed back to the previous queried value
+   EXTJS-19596   Date picker should preventDefault on arrow keys
+   EXTJS-19631   Selectfield is selecting wrong value
+   EXTJS-19646   emptyCls is not removed from combobox when value is set via binding but store is not loaded
+   EXTJS-19647   Checkbox disregards inputValue when passed '1' or 1
+   EXTJS-19775   Email and telephone hyperlinks destroy HtmlEditor iframe
+   EXTJS-19779   Slider filed does not perform multiple method calls on change
+   EXTJS-19842   Combobox with enableRegExp:true throws error when entering asterisk
+   EXTJS-19932   getSameGroupFields() in Ext.field.Checkbox does not properly define a root for Ext.query
+   EXTJS-20044   Disabling a filefield after a reset causes exception
+   EXTJS-20049   ComboBox does not clear partial text selection after selection using typeAhead
+   EXTJS-20185   Ext.form.Panel.reset method missing argument
+   EXTJS-20199   Destroying tagfield in a non-destroyed panel causes "Uncaught TypeError: Array.prototype.indexOf"
+   EXTJS-20248   stripCharsRe for ComboBox doesn't correctly replace if the same value is re-entered
+   EXTJS-20250   ComboBox setValue returns undefined when value is cleared
+   EXTJS-20298   ComboBox in a widgetcolumn does not collapse when clicking its trigger
+   EXTJS-20341   Multi selector grid - employees men disappears after touch
+   EXTJS-20447   Field before/afterLabelTextTpl is not kept when calling setFieldLabel
+   EXTJS-20492   Error while destroying a grid with celleditor, when tagfield has focus
+   EXTJS-20610   Datefield does not fire onchange when selecting date

Grid (86)

+   EXTJS-15145   Sliderwidget will not slide when using RTL
+   EXTJS-15662   Grid drag/drop fails in some browsers
+   EXTJS-15736   Using scrollable true on grid with a locked column causes exception
+   EXTJS-16196   Locking grid throws "Cannot read property 'els' of undefined" on reconfigure in some cases
+   EXTJS-16390   Pasting cells from Excel into grid with spreadsheet model and clipboard plugin results in an extra row.
+   EXTJS-16693   Spreadsheet selection model fires selectionchange event twice
+   EXTJS-16830   CellModel exception when sorting BufferedStore
+   EXTJS-16925   Cell editing events out of order when using tab to navigate cells
+   EXTJS-17005   Checkcolumn checkchange should pass the record as a parameter
+   EXTJS-17196   Buffered renderer plugin incorrectly sizes view when view size changes and it is hierarchically hidden
+   EXTJS-17253   Grouping feature events not firing on grid
+   EXTJS-17941   Wrong position of combobox list with virtual keyboard opened - Android
+   EXTJS-18092   Columns are movable just to one side on touch screen in RTL
+   EXTJS-18195   Expanded row scrolls into view when trying to collapse
+   EXTJS-18351   Focusing a cell does not scroll it into view when using touch scroller
+   EXTJS-18491   Cursor position in fields is not consistent across browsers when roweditor fields are activated
+   EXTJS-18655   Groups disapearing in grid after refresh
+   EXTJS-18841   Number filter clears value when tabbing to "eq" field
+   EXTJS-18868   Row expander - row changes position after trying to collapse partially hidden row
+   EXTJS-18927   Error in grouped grid after a store reload and group is collapsed
+   EXTJS-18985   Row editor does not reposition itself when textarea is used as an editor in last few rows
+   EXTJS-18989   Groups with encoded HTML special chars breaks grouping
+   EXTJS-19013   Grid SelectionModel allows selectAll when showHeaderCheckbox:false
+   EXTJS-19176   Grid with spreadsheet model swaps rownumber and checkbox columns when reconfigured
+   EXTJS-19251   Containers in a WidgetColumn do not layout properly when scrolling beyond buffer zones
+   EXTJS-19282   Row in locked grid doesn't expand to same height as unlocked side
+   EXTJS-19289   List grid filter should not react to store changes to update the menu when given options
+   EXTJS-19311   Locking grid does not respect Checkbox selection model injectCheckbox during column lock and unlock
+   EXTJS-19350   Refocusing Table when trigger of focusleave was actionable element does not renter actionable mode.
+   EXTJS-19360   Horizontal scrollbar can sometimes not appear when locking column for first time.
+   EXTJS-19389   Cell editing cannot be restarted on locked column
+   EXTJS-19425   Grid groups can't be opened after calling scrollTo or related API until a user-initiated scroll is performed
+   EXTJS-19446   Grid columns menu picker does not update new columns on reconfigure
+   EXTJS-19474   CheckboxModel header checkbox should only operate on items available to the current view
+   EXTJS-19508   RowExpander does not update layout on expand/collapse
+   EXTJS-19515   "'findParent' of undefined or null reference" on grid panel with viewport scrolling on touch-enabled device using IE
+   EXTJS-19522   Partially visible rows cannot be selected/highlighted when clicking causes the row to scroll into view in webkit-based browsers
+   EXTJS-19533   Virtualized scrolling does not reach browser scroll limits
+   EXTJS-19534   Spreadsheet selModel throws error if mouseup is outside grid.
+   EXTJS-19562   List gridfilter errors when destroyed if its store is a string value before menu is first shown
+   EXTJS-19623   Grid cellediting on sorted column causes error
+   EXTJS-19652   After store update and row removal, cell editing no longer works and throws errors
+   EXTJS-19664   Clipboard plugin does not paste dates from excel with spreadsheet selection model
+   EXTJS-19675   Grid with buffered rendering and cell editor sometimes throws errors after scrolling
+   EXTJS-19682   Cell editing cannot be canceled on Firefox
+   EXTJS-19696   Reconfigure throws JS error when grid has focus
+   EXTJS-19710   Buffered renderer does not work after reconfigure if the grid is initially configured without columns
+   EXTJS-19766   List filter incorrectly uses grid store when options list is configured
+   EXTJS-19770   Grid focus can prevent text selection
+   EXTJS-19810   Grid cell editor DOM element is null after row is removed and garbage collection runs
+   EXTJS-19843   Intermittent errors when scrolling upwards from end of grid with variableRowHeight
+   EXTJS-19846   Infinite grid with BufferedStore, buffered renderer, and locked column displays blank view when scrolling quickly
+   EXTJS-19851   Grid column align class does not apply to cells
+   EXTJS-19863   Filter menu is not created when grid is configured with sortableColumns and enableColumnHide disabled
+   EXTJS-19869   Clipboard plugin should not respond when grid is in actionable mode
+   EXTJS-19872   Stateful width of locked column is not applied
+   EXTJS-19875   Unable to collapse all groups when using groupFn
+   EXTJS-19883   Clipboard plugin throws error when configured to copy/paste in raw format
+   EXTJS-19886   Cell editing uses value from renderer when model value is undefined
+   EXTJS-19887   CellModel does not apply styles correctly if the selected cell position changes
+   EXTJS-19899   New edit value should be updated if termination of previous edit causes record mutation.
+   EXTJS-19916   Docked Summary scrolls vertically with view when grid is locked
+   EXTJS-19922   Grid column menu is visible when scrolling beyond bounds of parent container
+   EXTJS-19950   Grid forceFit:true where calculated flexes tend to zero throws error
+   EXTJS-19964   Cannot activate cell editor when editing was previously cancelled by clicking gridview
+   EXTJS-19993   Dropping a column on a grouped column header can cause column misalignment
+   EXTJS-19996   Grid view displays empty rows when grouping is cleared
+   EXTJS-20019   Ext.grid.column.Column setText() updates the wrong element
+   EXTJS-20021   Removing records on grid with grouping does not update selection
+   EXTJS-20035   Editing in locked grid causes change in normal grid scroll position
+   EXTJS-20058   Destroying grid in action column handler creates error
+   EXTJS-20134   Grid filters not applied correctly when using reconfigure with nested columns
+   EXTJS-20159   Locked grid with a viewmodel throws exception on destroy
+   EXTJS-20181   Copying cell data from Excel (Windows-only) includes line feed which produces unexpected paste results in grid
+   EXTJS-20194   Locked split grid with specified locked size cuts off last locked column
+   EXTJS-20219   Summary count in conjunction with grouping returns list of objects instead of count
+   EXTJS-20241   Spreadsheet selection model with checkboxSelect: true causes component to uncheck after mousemove
+   EXTJS-20244   Grid filter information not sent in requests for bound viewmodel stores
+   EXTJS-20351   Grid focusRow fails to focus new row after reconfiguring with a new column set
+   EXTJS-20387   Spreadsheet model throws error when binding to the store
+   EXTJS-20395   MessageBox has incorrect z-index after editing in a floating grid
+   EXTJS-20439   Cannot use native text copy / paste in cell editors with spreadsheet model
+   EXTJS-20548   Cell editing on a grid swallows events intended for widgets
+   EXTJS-20561   Grid column contextMenu not shown with longpress on mobile
+   EXTJS-20583   Grid filter creates request when column menu first expanded
+   EXTJS-20634   Grid causes extraneous refreshes when choosing options from list filter

Layouts (7)

+   EXTJS-15309   Collapsible panel inside vbox layout is positioned incorrectly during expand animation
+   EXTJS-19222   Layout not performed correctly when showing hidden item in absolute layout
+   EXTJS-19397   Ext.layout.container.Auto Chrome bug workaround can be removed for recent versions
+   EXTJS-19421   Center layout does not lay out HTML components correctly
+   EXTJS-19452   Calling setDocked(null) on container throws uncaught typeError
+   EXTJS-19721   "targetCls is missing" warning for Panel with viewport plugin and box layout
+   EXTJS-19791   Accordion layout does not respect child animCollapse duration

Locale (3)

+   EXTJS-19575   'Loading...' is translated into Traditional Chinese in Simplified Chinese locale file
+   EXTJS-19617   Format inconsistencies cause bug in Lithuanian locale
+   EXTJS-20081   Russian locale file uses incorrect thousandSeperator

Menu (5)

+   EXTJS-17844   Submenu closes when parent item is clicked
+   EXTJS-17945   Menu selection changes URL to '#' on touch devices
+   EXTJS-19298   Menu icon vertical separator on wrong side in RTL mode
+   EXTJS-19679   Tabbing from menu with hidden ancestor goes out of the document
+   EXTJS-19773   Menu defaultType not respected correctly

Misc (1)

+   EXTJS-18907   DragZone does not register containerScroll element

Panel (6)

+   EXTJS-18902   Tools in ghost/drag proxy disappear when dragging panel
+   EXTJS-19122   Ext.Msg does not suppress message when useMsg is set
+   EXTJS-19518   Panel toolbars (t/r/b/l/f) mutate a passed config object
+   EXTJS-19975   Setting panel title with numeric value does not update the title
+   EXTJS-6924   Expand fails for panel with animation that is initially collapsed
+   EXTJS-9961   Ext.panel.Panel with titleCollapse is not expanding on header click

PivotGrid (4)

+   EXTJS-19181   Range editor plugin does not calculate cell values correctly when "Uniformly" type is used
+   EXTJS-19465   Configurator panel disappears after setting grid height
+   EXTJS-19777   Pivot grid naming for pt_br locale does not work with framework locale name
+   EXTJS-19907   Ext.pivot.plugin.configurator.Container should have requires[] for Vbox and Column layouts

Scroller (17)

+   EXTJS-10272   Auto height window with minHeight, scroll jumps after expand child panel
+   EXTJS-12640   Auto height form scrolls to top when radiogroup option selected in container
+   EXTJS-15691   Panel with relative height scrolls to top when adding items
+   EXTJS-16080   Auto height form loses scroll position when modifying a value
+   EXTJS-16334   Adding or removing elements to an auto height form causes it to scroll to the top
+   EXTJS-16349   Auto height form scrolls when modifying value
+   EXTJS-18502   Scroll position resets when a panel is added to a container with maxwidth
+   EXTJS-18895   Binding in border layout can cause grid to scroll to top on selection
+   EXTJS-19140   Clicking on a checkbox scrolls the form if a height is not set
+   EXTJS-19312   Tapping to abort momentum scroll does not fire scrollend event
+   EXTJS-19756   When form is vertically scrolled, showing a hidden form field can cause the form to scroll to the top
+   EXTJS-19828   directionLock functionality is not honoured
+   EXTJS-6091   Expanding/Collapsing auto height fieldset causes scroll position to be reset
+   EXTJS-7103   Shrinkwrap auto layout component loses scroll position when layout is updated
+   EXTJS-7869   Scroll position lost when Box layout updates
+   EXTJS-8231   Tab setTitle will reset form panel scrollbar if form panel has auto height children
+   EXTJS-9286   Form panel with auto height fieldset in viewport - setVisible cause scroll reset to top

Tabs (3)

+   EXTJS-14334   Cannot change activeTab via buttons in tabbar overflow menu
+   EXTJS-16281   Overflowing tabs in a TabPanel don't properly scroll via mouse wheel
+   EXTJS-19667   Initially disabled TabPanel does not show active tab

Templates (4)

+   EXTJS-14784   Executive Dashboard: The download is initialized twice on one click
+   EXTJS-19206   Modern Admin Dashboard - Dismissing menu on phone email screen prevents composing new email via + button
+   EXTJS-20397   Admin Dashboard - after resizing charts doubleclick don't return it to its default state
+   EXTJS-20698   Cannot see items in Friend list in Modern Admin Dashboard

Theme (9)

+   EXTJS-14098   Tab scroller arrows are not being shown correctly for RTL
+   EXTJS-18344   Picker is styled incorrectly in windows theme
+   EXTJS-18776   Modern theme-neptune doesn't require font awesome
+   EXTJS-19306   grid-cell and toolbar UI CSS is not generated for tagfields in classic-based themes
+   EXTJS-19395   Tree arrows point wrong way in RTL with Triton theme
+   EXTJS-19521   Window icon appear grayed out due to added opacity (0.5)
+   EXTJS-19724   Minor RTL element misplacement in group headers
+   EXTJS-19827   Load mask spinner animation not working correctly
+   EXTJS-20084   Checkbox label font size variable incorrect

ToolTips (4)

+   EXTJS-17583   Tooltips not showing for hybrid touchscreen devices on hover
+   EXTJS-17892   Tooltip should not ignore mouseover event on touch devices
+   EXTJS-18288   Tooltip does not display arrow pointing to the target even when anchor is explicitly set
+   EXTJS-19276   Tooltip anchor moves with each rendering

Toolbars (1)

+   EXTJS-15500   Radiofield component does not allow selection on toolbar overflow menu

Tree (10)

+   EXTJS-18474   TreeStore does not filter on child nodes
+   EXTJS-19179   Incorrect focus in locked grid when removing rows
+   EXTJS-19202   Asterisk expand all key event causes exception with locked tree
+   EXTJS-19391   Reconfiguring locked tree can render empty rows
+   EXTJS-19393   Loading/reloading a tree store that has used filterBy() throws an exception
+   EXTJS-19581   Treelist micro mode row item hover styling not being applied
+   EXTJS-19619   Treelist menus in micro mode do not dismiss on mouseOut in IE
+   EXTJS-19663   Treelist does not maintain the correct order for micro mode with dynamic node insertion
+   EXTJS-19678   Tree panel does not render correctly if a child node is loading during render
+   EXTJS-20007   Tree view no longer applies expander class when mousing over the expander icon

Window (8)

+   EXTJS-15843   Window restore tool not correct when starting maximized
+   EXTJS-16184   Modal window background does not resize with browser window
+   EXTJS-16683   Blur event doesn't fire on Ext.window.Window
+   EXTJS-19686   Maximized window is draggable when animateTarget is configured
+   EXTJS-19954   Tabbing in child modal window incorrectly tabs to parent window
+   EXTJS-19984   Ext.WindowManager.hideAll() does not hide mask when window is modal
+   EXTJS-20088   MessageBox displays scrollbars when displayed more than once on touch/hybrid-enabled device
+   EXTJS-20149   Window modal mask gets positioned on top of the window when hiding other modal windows

## Known Issues

Accessibility (16)

+   EXTJS-10451   Tree component is not accessible
+   EXTJS-10467   Menu overflow scrollers are not navigable using the keyboard
+   EXTJS-10475   ToolTip is not accessible
+   EXTJS-10477   HtmlEditor is not accessible
+   EXTJS-10480   Color Picker is not accessible
+   EXTJS-10491   Property Grid is not accessible
+   EXTJS-10492   DragDrop is not accessible
+   EXTJS-10493   Paging Toolbar is not accessible
+   EXTJS-10494   Grid grouping feature is not accessible
+   EXTJS-10495   Locking grid is not accessible
+   EXTJS-10496   Grouped grid headers are not accessible
+   EXTJS-10497   Grid row expander is not accessible
+   EXTJS-10498   Grid RowBody feature is not accessible
+   EXTJS-10499   Grid CheckboxSelectionModel is not accessible
+   EXTJS-10503   Grid headers cannot be resized using the keyboard
+   EXTJS-10504   Grid Headers cannot be reordered using the keyboard

Charts (1)

+   EXTJS-10739   RTL Charts do not correctly display bidirectional text

Core (1)

+   EXTJS-17885   Modern toolkit should provide an Ext.setup equivalent method

DataView (1)

+   EXTJS-12345   ComboBox's bound list becomes transparent on second show on iPad

Layouts (1)

+   EXTJS-4768   Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container

Tabs (1)

+   EXTJS-13538   Ext.ux.TabScrollerMenu does not work with Ext JS 5.0

Theme (1)

+   EXTJS-17790   Triton should support tree lines

Total: 22

# Release Notes for Ext JS 6.0.1

Release Date: September 8, 2015  

Version Number: 6.0.1.250

## Noteworthy

The default value for Ext Direct Remoting API variable name was changed from

    Ext.app.REMOTING_API

to

    Ext.REMOTING_API

for better alignment with published Ext Direct specification. If your application makes use of the

    loadProvider

method in Ext.direct.Manager, you will need to review and possibly update the

    varName

config option.

## New Features

Accessibility (1)

+   EXTJS-18935 Focusable events focusenter and focusleave should be public 

App (3)

+   EXTJS-18770 Application mainView config should accept config object 
+   EXTJS-19000 Provide a "lookup" method as a short hand for "lookupReference" 
+   EXTJS-19011 The active profile should be able to provide xtype definitions appropriate to target environment 

Button (1)

+   EXTJS-19009 Buttons should have a textAlign config in modern toolkit 

Charts (1)

+   EXTJS-18479 Charts should fire 'itemhighlightchange' to detect transitions to no item being highlighted 

Cmd (1)

+   EXTJS-18693 Universal apps need a resource folder that is page-relative and shared by all build profiles 

Core (2)

+   EXTJS-19010 Responsive plugin should be provided on modern toolkit 
+   EXTJS-19186 Ext.Component#fromElement should be provided for modern toolkit 

Data (1)

+   EXTJS-18567 Session should have a method that will clone a record instance from a parent to a child 

Direct (2)

+   EXTJS-18275 Allow a limit of requests to be batched in Ext Direct 
+   EXTJS-18768 Allow Direct method to be excluded from batch. 

Draw (3)

+   EXTJS-18766 Sprites should have a transform method to apply arbitrary transformations not limited to scale, rotate and/or translate 
+   EXTJS-18930 Add shear x/y methods to Ext.draw.Matrix 
+   EXTJS-18958 Sprites should provide a public animation config to control their animated attributes 

Forms (1)

+   EXTJS-16559 Modern toolkit should provide a progress bar widget 

Grid (3)

+   EXTJS-18500 Modern grid should support flex column widths 
+   EXTJS-18713 summaryRenderer should receive the cell like a normal cell renderer in the modern grid 
+   EXTJS-18899 Modern grid should support hideHeaders config 

Misc (1)

+   EXTJS-18475 Ext.Img alt, src and title configs should be bindable 

Panel (1)

+   EXTJS-16510 Modern toolkit should support panel header, title, tools and icon 

Templates (1)

+   EXTJS-18876 Admin dashboard should be a universal application 

Theme (2)

+   EXTJS-18811 Blackberry Theme for Modern Toolkit 
+   EXTJS-18996 Upgrade Font Awesome package to use latest version (4.4.0) 

Tree (2)

+   EXTJS-18378 Trees should provide a beforecheckchange event to allow checking/unchecking to be prevented 
+   EXTJS-19187 Treelist should provide an itemclick event 

## Bugs Fixed


Accessibility (5)

+   EXTJS-18186 FocusableContainer should prevntDefault on UP/DOWN arrow keys 
+   EXTJS-18361 Cannot see underscore in text fields on normal zoom in FF 
+   EXTJS-18665 Cannot tab away from a focused slider with multiple thumbs 
+   EXTJS-18767 Sliders use wrong ARIA attributes 
+   EXTJS-18879 Keyboard navigation is not working properly in Date menu 

App (1)

+   EXTJS-17556 View model links don't create separate record instances correctly when used with a parent view model 

Button (4)

+   EXTJS-16118 Browse local files button doesn't work on iOS8 
+   EXTJS-17953 Wrongly displayed buttons in modern toolkit on Edge in modern-neptune theme 
+   EXTJS-18774 Error: menu button behavior will conflict with toggling 
+   EXTJS-19111 Menu button ARIA warning check not accounting for inherited listeners 

Charts (12)

+   EXTJS-18028 3D pie chart wrong drawing order 
+   EXTJS-18460 Updating the store of a pie chart breaks the rendering 
+   EXTJS-18572 Chart.getInteraction method does not match type properly 
+   EXTJS-18573 ItemEdit interaction should destroy the tooltip it creates on its own destruction. 
+   EXTJS-18599 RotatePie3D interaction doesn't always work if one grabs the edge of the series 
+   EXTJS-18609 useDarkerStrokeColor and showMarkers configs have no updaters 
+   EXTJS-18706 JS error when activating tab with chart 
+   EXTJS-18790 Pie chart rendering breaks when number of labels changes 
+   EXTJS-18831 Real-time chart is unresponsive - iOS 
+   EXTJS-18862 When previewing a chart, Ext JS logs out ARIA compliance warning 
+   EXTJS-18870 Edge lines are not always displayed from end to end in 3D bar 
+   EXTJS-18924 Drawing - Bouncing Logo - Troubles with loading of picture, Error 404 

Cmd (2)

+   EXTJS-18617 platformTags used by platformConfig do not always resolve tablet property correctly on phones 
+   EXTJS-19131 Fashion generates incorrect CSS for focused buttons in classic Admin Dashboard. 

Core (14)

+   EXTJS-17523 Instance configs should allow functions to replace emptyFn and family template methods 
+   EXTJS-17694 FieldContainer does not add layout's targetCls to its containerEl 
+   EXTJS-17870 Ext.Date.clearTime gets into an infinite loop if the date informed is Invalid 
+   EXTJS-18108 Container.nextChild/prevChild return undefined instead of null when child not found 
+   EXTJS-18192 Component.load does not honour the scripts: true config 
+   EXTJS-18388 ComponentQuery should be able to filter objects which are not instances of Ext classes 
+   EXTJS-18477 Ext.dom.Query.selectValue defaultValue is not used 
+   EXTJS-18503 Scroll partners do not match elastic overscroll of active scroller. 
+   EXTJS-18623 Container.nextChild/prevChild may return siblings or other non-child nodes if no matching child is found 
+   EXTJS-18679 onScrollStart fired too early in IE8 when scrolling both x and y axes 
+   EXTJS-18681 Ext.util.ItemCollection not required by Ext.Container 
+   EXTJS-18764 Viewport plugin layout warning 
+   EXTJS-18772 Uncaught TypeError: Cannot read property '_incr_' of undefined in modern toolkit 
+   EXTJS-19046 Edge doesn't know touch event "drag", "doubletap" 

Data (16)

+   EXTJS-14996 ManyToOne association doesn't infer keys correctly when loading the store (not nested loading) 
+   EXTJS-15583 validate method of Ext.data.validator.Validator is not passed the record argument when one is available 
+   EXTJS-17384 Ext.data.reader.Json parsing invalid data never fires exception event 
+   EXTJS-18085 Store load calls should be buffered to avoid making multiple network requests 
+   EXTJS-18209 Buffered Store requests every page in the scroll range when scroll bar dragged and locked columns present. 
+   EXTJS-18219 TreeStore loaded from flat file not sorting children 
+   EXTJS-18481 getResponseHeader broken 
+   EXTJS-18489 Binding of loaded associated store in child session triggers a proxy load 
+   EXTJS-18521 Ext.data.field.Field calculate function config fails to determine dependencies in IE 
+   EXTJS-18594 Modern form panel calls missing method Ext.Ajax.parseStatus 
+   EXTJS-18595 Returning false from beforesubmit event in formpanel doesn't prevent submit on modern toolkit 
+   EXTJS-18683 BufferedStore does not fire the beforesort event 
+   EXTJS-18760 Pagingtoolbar status message incorrect on initial load using memory proxy 
+   EXTJS-18836 Sortable#sort throws an error if the first sorterFn in a multi sort operation returns 0 (equality) 
+   EXTJS-18848 Sorting a locked grid with a buffered store throws an error. 
+   EXTJS-18911 Session.commit() does not clean up matrix data 

DataView (3)

+   EXTJS-18650 Chaining selection - Binding selection view doesn't react onClick,onTap 
+   EXTJS-18851 Dataview with selection binding renders items unselectable 
+   EXTJS-19089 Ext.List does not react to store.removeAll() 

Distribution (2)

+   EXTJS-19083 Commercial build should exclude watermark files. 
+   EXTJS-19095 Missing trial watermark font 

Draw (7)

+   EXTJS-18302 Sprite events don't fire on some sprites 
+   EXTJS-18356 Bounding box is not rendered properly for transformed Text sprites 
+   EXTJS-18360 Line sprite bbox calculation does not account for line width nor for transformations 
+   EXTJS-18431 Sprites have incorrect transformation order (rotate, scale, translate) but should be scale, rotate, translate 
+   EXTJS-18578 Sprite events fire on hidden sprites 
+   EXTJS-18929 sprite.setTransform does not set the dirty flag on the surface 
+   EXTJS-18957 skewX and skewY contain incorrect matrix data 

Events (1)

+   EXTJS-16448 Element change events do not fire when delegated (which is the default) 

Examples (14)

+   EXTJS-17515 KS: ExtJS Calendar - example freeze after button click - IE11,Spartan - Win10 Tablet 
+   EXTJS-18373 Scrolling Modern example source causes the background to disappear after the first "page" 
+   EXTJS-18453 Chart Axis Labels show wrong name in Pivot Grid Chart example 
+   EXTJS-18458 Pivot grid with chart integration example has issues 
+   EXTJS-18749 JsonSimlet responseText undefined for POST requests 
+   EXTJS-18783 KitchenSink Pivot grid example is not correctly loaded in IE8 
+   EXTJS-18828 Kitchen sink menu is not displayed on iOS8 
+   EXTJS-18832 Pivot grid example with configurator throws error in console when collapsing panel and changing dock position 
+   EXTJS-18852 Kitchen Sink partially fails to load in IE10 / IE11\. Panel header tools unresponsive. 
+   EXTJS-18887 Simpletasks - Treepicker disappears after click on expander 
+   EXTJS-18889 Grid is empty if selection type is Spreadsheet in ARIA demo 
+   EXTJS-18936 Kitchen Sink triton font isn't loading 
+   EXTJS-19019 User can't scroll in Data Binding examples 
+   EXTJS-19093 Missing resource images in Address Book example 

Exporter (1)

+   EXTJS-18965 showZeroAsBlank is ignored when data is exported to Excel 

Forms (34)

+   EXTJS-12570 E-mail vtype validates with space at the beginning 
+   EXTJS-15231 HtmlEditor in IE11 behaves incorrectly with Enter key 
+   EXTJS-15372 Datefield error tooltip not displayed 
+   EXTJS-17020 Opening combobox with no store throws error 
+   EXTJS-17248 Combobox does not respect checkChangeBuffer configuration 
+   EXTJS-17334 Picker does not allow you select the last item 
+   EXTJS-17372 Combobox keeps focus when another field is selected if the boundlist is expanded 
+   EXTJS-17948 Tabbing out of Date picker when selected date is disabled does not close picker 
+   EXTJS-18279 Numberfield does not properly filter certain non-numeric keypresses 
+   EXTJS-18430 Checkbox fields with hideLabel:true cause incorrect form layout. 
+   EXTJS-18448 Delete key does not work in FF in textfield with vtype & maskRe 
+   EXTJS-18457 selectfield does not display properly after creating a build 
+   EXTJS-18465 ComboBox forceSelection:true and allowBlank:true restores previous value on blur 
+   EXTJS-18505 RTL labelAlign: 'right' is incorrect 
+   EXTJS-18548 TextArea updateHeight updateWidth incorrect variable name 
+   EXTJS-18553 Font package rules such as "fa-gear" should override framework rules in iconCls configs 
+   EXTJS-18565 Combobox displayTpl overwritten with auto generated store 
+   EXTJS-18621 stripCharsRe doesn't work when key held down 
+   EXTJS-18632 Cannot select picker item after several editor clear 
+   EXTJS-18709 Ext.form.field.Picker#setEditable not handling onTriggerClick of inputEl 
+   EXTJS-18729 Picker fields (ComboBox etc) do not collapse on scroll in FF. 
+   EXTJS-18741 TimeField issue when default Value does not match increment 
+   EXTJS-18745 Combobox clears on focus when displayValue == emptyText 
+   EXTJS-18755 Sliders get misaligned with their buttons when set to vertical (Triton Theme) 
+   EXTJS-18795 Multi-slider thumbs incorrectly positioned when set to extreme upper bounds and slider is clicked 
+   EXTJS-18798 Browser history navigates backward/forward when browsing months in a Datepicker using ctrl key 
+   EXTJS-18829 Grid Filtering - Datepicker dissapears after click 
+   EXTJS-18840 Backspace in modern toolkit form fields conflicts with device auto-complete and repeats portions of text 
+   EXTJS-18864 Month picker clicks cause parent menu to hide 
+   EXTJS-18933 Filefield button disappears after file is selected in IE8 and 9 
+   EXTJS-18942 Modern - Form panel - Swipe causes blanking of the screen 
+   EXTJS-18962 Can't mark radio button on Cupertino 
+   EXTJS-19004 Path to file is not set in IE9 
+   EXTJS-19136 Double click on itemselector on menu button doesn't work. 

Grid (57)

+   EXTJS-14083 Grid group expand/collapse tips not added to the grouping feature markup 
+   EXTJS-16385 CellEditing - right mouse click in FireFox triggers edit 
+   EXTJS-16592 Grouping: reconfiguring with a new store adds additional view listeners to the view 
+   EXTJS-16778 Locking Grid: focus jumps to different cell when scrolling 
+   EXTJS-17051 Grouping: Adding new record to existing group will create its own group above current group 
+   EXTJS-17064 Cannot copy/paste columns in spreadsheet selection model in locking grid 
+   EXTJS-17237 Locking side of locking grid misaligned in RTL mode 
+   EXTJS-17362 isDisabled in action column not called when record is updated 
+   EXTJS-17416 View needs to scroll when editing a row not in the current view (buffered renderer = true) 
+   EXTJS-17476 KS: Big Data grid - locking specific column breaks the grid - IE11,Spartan - Tablets W10 
+   EXTJS-17522 Grid Summary is not displayed for columns that were initially hidden 
+   EXTJS-17577 Grouped headers do not display after moving columns and restoring state 
+   EXTJS-17699 CheckboxModel's checkOnly:true is not respected by CellEditing plugin on first edit 
+   EXTJS-17736 Grid scrolls to initial horizontal position when initializing a row editor by clicking on a column cell within the scrollable area of the grid 
+   EXTJS-17819 Locked grids with asymmetric row heights can generate exceptions when scrolling 
+   EXTJS-17980 Grid Cell Edited with Roweditor loses focus after clicking on UPDATE/CANCEL 
+   EXTJS-18019 When modifying a grid filter triggers a LoadMask the change of focus dismisses the menu 
+   EXTJS-18054 ensureVisible within a viewready listener throws el of null error 
+   EXTJS-18090 Missing or partialy visible row numbers in locking grid example - RTL Hebrew 
+   EXTJS-18286 Grid without a fixed height will scroll all the way to the top when the horizontal scrollbar is clicked 
+   EXTJS-18311 Group column header long text truncated (no ellipsis) 
+   EXTJS-18390 Hiding all sub columns, then showing the owner results in bad layout in modern grid 
+   EXTJS-18415 On touch devices, grids with variable row heights might not be able to scroll to the end. 
+   EXTJS-18459 Calling summary collapseAll() in a grid with locking throws "Maximum call stack size exceeded" 
+   EXTJS-18461 Cannot resize column immediately after resizing without first moving the mouse 
+   EXTJS-18490 Row editor disappears when scrolling beyond leading/trailing buffers 
+   EXTJS-18493 "view" undefined variable Ext.rtl.grid.plugin.BufferedRenderer 
+   EXTJS-18515 A subheader in a group cannot be shown if all subheaders are hidden 
+   EXTJS-18527 Cell editor fails to focus in IE8 
+   EXTJS-18597 Grid reconfiguring will not update Grouping Summary with new column configuration 
+   EXTJS-18633 Can hide all columns using the grid column menu 
+   EXTJS-18653 Grouping feature startCollapsed is not working when buffered rendering not used. 
+   EXTJS-18655 Groups disapearing in grid after refresh 
+   EXTJS-18677 Cannot disable grid loadMask 
+   EXTJS-18686 Destroying a lockable grid with buffered renderer errors if grid's store data is updated 
+   EXTJS-18721 Scrolling with touch screen is not working on buffer grid 
+   EXTJS-18778 Grid groups can't be opened after calling scrollTo or related API until a user-initiated scroll is performed 
+   EXTJS-18781 Big data grid - error in console after collapsing group and moving columns 
+   EXTJS-18805 Incorrect scroller size and position - touch devices 
+   EXTJS-18830 Grid headers don't scroll horizontally when trying to edit a field that requires scrolling 
+   EXTJS-18844 Summary of sorted grid is not updated after column reordering 
+   EXTJS-18880 Renderers in ViewControllers are not called when dependent fields are updated 
+   EXTJS-18922 Cannot open grid header menu - IE9 - Classic theme 
+   EXTJS-18941 Un/mark rows in menu fails if animation of opening group is not done 
+   EXTJS-18959 Grid with locked columns become out of sync on iPad 
+   EXTJS-18971 Property grid - interaction with comboboxes causes block of the second combobox 
+   EXTJS-18979 Columns in modern grid do not always have correct width and sometimes don't appear initially 
+   EXTJS-18990 Disabling grouping can refresh the grid incorrectly, leaving it at an incorrect scroll position. 
+   EXTJS-18994 widgetcolumn with radiogroup disappears after sorting the grid 
+   EXTJS-19016 Grid List filter isn't filtering on store load 
+   EXTJS-19054 Cannot scroll modern grid horizontally using touch screen on Windows 
+   EXTJS-19086 emptyText is misplaced on Grid 
+   EXTJS-19087 Vertical scrollbars cause grid headers to get out of sync 
+   EXTJS-19101 Grid with spreadsheet model loses row number when reconfigured 
+   EXTJS-19109 Grid list filter throws exception when binding a filtered store when remoteFilter: true 
+   EXTJS-19113 Modern grouped header not rendered properly in device themes 
+   EXTJS-9820 grid.reconfigure doesn't engage load mask when configure with locked columns 

Layouts (3)

+   EXTJS-18538 Memory leak with grid inside box layout with align: stretch 
+   EXTJS-19053 TextArea input element does not stretch the height on its input element in modern Neptune/Triton 
+   EXTJS-19057 Dock layout moves DOM around at every layout in some configurations 

Locale (1)

+   EXTJS-15425 12-hour time format period labels are incorrect for Swedish locale 

Menu (6)

+   EXTJS-17468 Grid header column menu - check list can't be checked - IE11,Spartan - Tablets W10 
+   EXTJS-17913 Menu will focus disabled items on arrow keys navigation 
+   EXTJS-17914 Tabbing out of submenu results in lost focus 
+   EXTJS-18318 Menu CheckItems with submenus toggle on tap outside of checkbox. 
+   EXTJS-18853 Docked items on menus do not properly adjust body position in latest nightly build 
+   EXTJS-18882 Clicking the icon in a menu hides the menu but does not perform the action 

Misc (4)

+   EXTJS-18660 Navigation View (modern) shows back button on the right side with empty stack 
+   EXTJS-18661 Navigation view(modern) title is shifted to far right corner after new card is pushed and when popped out 
+   EXTJS-18663 MessageBox/Alert cannot be closed sometimes on Chrome 34 in modern toolkit 
+   EXTJS-18960 Compiler directive in Ext.mixin.Identifiable causing problems with development version of app on IE10 

Panel (2)

+   EXTJS-18480 Panel body of framed panel is not in proper DOM order vs dockedItems in IE8/9 
+   EXTJS-18909 HTML markup in panel title is not escaped for aria-label attribute 

PivotGrid (1)

+   EXTJS-17859 Drill down plugin doesn't work with remote matrix 

Scroller (2)

+   EXTJS-19044 Edge browser uses incorrect scrolling mode (Scrollbars are invisible and mousewheel scrolling is disabled) 
+   EXTJS-19073 Window scrollbar does not work in 08252015 nightly build 

Selection Model (1)

+   EXTJS-18592 CTRL/click in SINGLE mode should not select 

Sparkline (1)

+   EXTJS-17730 Zero state shown when moving mouse over an empty value in TriState sparkline 

Tabs (2)

+   EXTJS-18817 Wrong tab background color of selected tab in Window Layout example - IE8 
+   EXTJS-18819 Tabs in Header tabs example rotate on mouse over - IE8 

Templates (4)

+   EXTJS-18833 Styling issue in Admin dashboard - Email 
+   EXTJS-19159 Modern Admin Dashboard - Wrong icon color 
+   EXTJS-19189 Modern Admin Dashboard - tapping on selected node in navigation tree does not dismiss the sheet 
+   EXTJS-19190 Admin Dashboard - one of the widgets panel's content does not match between classic and modern 

Testing (1)

+   EXTJS-18579 Buffered renderer scrolls to wrong offset in IE8 

Theme (14)

+   EXTJS-17788 Resizable handles are missing styling in the triton theme 
+   EXTJS-18162 Textfield doen't have placeholder default color in IE 10/11 
+   EXTJS-18340 MessageBox is styled incorrectly in blackberry theme 
+   EXTJS-18341 Back button is styled incorrectly in blackberry theme 
+   EXTJS-18342 Tabs are styled incorrectly in blackberry theme 
+   EXTJS-18492 Menus with submenus display wrongly facing icon in RTL 
+   EXTJS-18525 Font icons used in panel and window headers are not properly positioned 
+   EXTJS-18542 Modern neptune's Component's $neutral-color var is defined twice 
+   EXTJS-18883 Typo in theme-neutral/Splitter.scss 
+   EXTJS-18945 Nested list leafs show white text on white background in the mountain view theme 
+   EXTJS-18964 Icons are replaced by squares in some examples - IE8, Triton 
+   EXTJS-19007 Misplaced icons - modern Toolbars example - Blackberry theme 
+   EXTJS-19008 Wrongly placed clear field icon in modern Overlays example - blackberry theme 
+   EXTJS-19045 Wrong fonts in Menu, in cupertino theme 

Toolbars (2)

+   EXTJS-17738 Toolbars not focusing on first enabled item 
+   EXTJS-18228 Menu remains opened in overflowed toolbar 

Tree (5)

+   EXTJS-15875 Events not firing after setRootNode 
+   EXTJS-17842 Sorting a collapsed tree node causes the children to be shown 
+   EXTJS-18742 iOS applies :hover styles on tap for TreeList 
+   EXTJS-19103 Admin Dashboard - Toolstrip shifts icons to the left on IE and Firefox 
+   EXTJS-19155 Treelist produces hover effects on the treelist items on mobile devices that emulate hover 

Window (2)

+   EXTJS-14698 Window doesn't constrain left correctly 
+   EXTJS-17969 Overlay window does not hide in Window 10 on Spartan browser 

## Known Issues


Accessibility (15)

+   EXTJS-10456 VoiceOver for Mac is not supported 
+   EXTJS-10467 Menu overflow scrollers are not navigable using the keyboard 
+   EXTJS-10477 HtmlEditor is not accessible 
+   EXTJS-10479 LoadMask is not accessible 
+   EXTJS-10480 Color Picker is not accessible 
+   EXTJS-10490 Progress Bar is not accessible 
+   EXTJS-10491 Property Grid is not accessible 
+   EXTJS-10492 DragDrop is not accessible 
+   EXTJS-10493 Paging Toolbar is not accessible 
+   EXTJS-10496 Grouped grid headers are not accessible 
+   EXTJS-10497 Grid row expander is not accessible 
+   EXTJS-10498 Grid RowBody feature is not accessible 
+   EXTJS-10499 Grid CheckboxSelectionModel is not accessible 
+   EXTJS-10503 Grid headers cannot be resized using the keyboard 
+   EXTJS-10504 Grid Headers cannot be reordered using the keyboard 

Charts (1)

+   EXTJS-10739 RTL Charts do not correctly display bidirectional text 

Core (1)

+   EXTJS-17885 Modern toolkit should provide an Ext.setup equivalent method 

DataView (1)

+   EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad 

Examples (1)

+   EXTJS-13879 Dashboard Portal drag-n-drop experience is not optimal especially on tablets 

Grid (2)

+   EXTJS-10494 ARIA - Grid Grouping Feature is not supported 
+   EXTJS-10495 ARIA - Locking Grid is not supported. 

Layouts (1)

+   EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container 

Tabs (1)

+   EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0 

Theme (2)

+   EXTJS-17790 Triton should support tree lines 
+   EXTJS-9806 ext-theme-aria does not support Windows high-contrast mode 

ToolTips (1)

+   EXTJS-10475 ARIA - ToolTip is not supported 

Tree (1)

+   EXTJS-10451 ARIA - The Tree component is not supported. 

#Release Notes for Ext JS 6.0.0

Release Date: July 1, 2015

Version Number: 6.0.0.640

## New Features

Accessibility (3)

+   EXTJS-12098 Containers should track their children's focus
+   EXTJS-13606 Floating mixin should support keyboard navigation
+   EXTJS-17285 ariaLabelledBy should support references

App (1)

+   EXTJS-16853 ViewController.fireViewEvent should ensure that the view is the first parameter

Button (1)

+   EXTJS-16860 Split buttons should have two tab stops

Charts (1)

+   EXTJS-17043 Axis labels should support declarative renderers

Core (1)

+   EXTJS-17667 Should provide a standards-compliant implementation of Promises

Data (1)

+   EXTJS-17672 Ext.Ajax request method should return a promise

Draw (1)

+   EXTJS-18248 Surface should have a 'remove' method for removing sprites

Forms (1)

+   EXTJS-16771 Form fields should handle validation errors in accessible way

Grid (1)

+   EXTJS-15634 Grid editing plugins should apply to top-most grid instead of being cloned to each side when locking

Panel (1)

+   EXTJS-16997 Panels should have a defaultButton config to activate particular button on ENTER key press

Selection Model (1)

+   EXTJS-16143 Clipboard plugin should allow columns (such as rownumberer) to be excluded from copy

## Bugs Fixed

Accessibility (3)

+   EXTJS-14427 Date picker dropdown calendar causes navigation issues with JAWS
+   EXTJS-17454 Ext.FocusManager.enable() throwing an error
+   EXTJS-17797 MessageBox buttons are not tabbable when text input (prompt) is enabled

App (1)

+   EXTJS-18345 Having a view named "Main" prevents the app from starting when using the modern toolkit

Bind (1)

+   EXTJS-17758 Modern toolkit textfields do not update two-way bindings as you type

Button (5)

+   EXTJS-17103 Disabled button enables when parent container got enabled
+   EXTJS-17818 Disabled buttons are rendered with tabindex="0"
+   EXTJS-17940 Triton theme split buttons do not show arrow icons in IE10 and 11
+   EXTJS-18073 Ext.button.Segmented should require Ext.layout.container.SegmentedButton
+   EXTJS-18171 Explicit button keyboard handlers are blocked by defaultButton processing

Charts (15)

+   EXTJS-15800 Linked axes should always use the range of the master axis
+   EXTJS-16954 majorTickSteps are not rendered properly on numeric axis
+   EXTJS-17653 CartesianChart which leads to 'TypeError: n.toPrecision...'
+   EXTJS-17719 3D Pie chart radius is not updated when distortion or thickness changes. It is also not calculated to efficiently use the vertical space.
+   EXTJS-17879 'itemhighlight' interaction is always added to a chart
+   EXTJS-17880 Chart layout is broken in certain scenarios (e.g. renderTo: document.body)
+   EXTJS-17951 Chart theme should be updated after changes to the 'series' config.
+   EXTJS-18015 f.blur is not a function - Unexpected error in FireFox console, during interaction with charts
+   EXTJS-18044 Custom sprites don't derive styling from the current framework theme
+   EXTJS-18045 Axis limits are off by the amount of innerPadding (left or top, depending on axis orientation)
+   EXTJS-18136 Charts should not register Series and Axes with ComponentManager
+   EXTJS-18184 Old series sprites are not destroyed when the 'chart' config changes
+   EXTJS-18232 Vertical axes of cartesian chart should extend one pixel more to the bottom.
+   EXTJS-18235 Preview image of the chart shouldn't overflow on mobile
+   EXTJS-18268 Modern toolkit - Column Chart (3D) doesn't load

Core (9)

+   EXTJS-12965 Grid momentum scrolling not working in Safari/Chrome
+   EXTJS-14944 Stateful mixin should require TaskRunner since it uses it
+   EXTJS-15869 Microsoft Surface keyboard obscures window
+   EXTJS-17280 modern toolkit - component's are not displayed. Windows Phone 8.1
+   EXTJS-17926 Ext.util.Format.number incorrectly rounds up using format with ## and /i
+   EXTJS-18067 ViewController binding doesn't seem to work in Modern toolkit
+   EXTJS-18183 TouchScroller's destructor tries to destroy scroll indicators which may not exist.
+   EXTJS-18277 Namespace warnings during Cmd build
+   EXTJS-18348 Accessing properties on widgets can sporadically result in exceptions on IE9

Dashboard (1)

+   EXTJS-18113 Executive dashboard - default routing not working

Data (13)

+   EXTJS-15785 Loading XML can result in memory leaks in IE (added "keepRawData" config to Reader)
+   EXTJS-16678 treeStore.setRoot doesn't set treeStore property to passed model instance
+   EXTJS-17143 Buffered store clears it records on load/reload even if beforeload returns false
+   EXTJS-17144 Buffered store doesn't fire load event if server returns 0 totalCount on reload
+   EXTJS-17351 store.getRemovedRecords should return a copy of the internal array
+   EXTJS-17447 Ext.getStore(id) not working in Ext JS 6 when migrating Touch 2.4.1 app to Modern
+   EXTJS-17727 HasOne association without in target model foreignKey throws exception when nested loading
+   EXTJS-17882 operation.Destroy throws exception when syncing > 1 destroyed records
+   EXTJS-17894 Adding a record to a store that has a sorted ChainedStore with an association source throws error
+   EXTJS-17981 ChainedStore getByInternalId fails if called after filtering
+   EXTJS-18012 Store.Remove(record) w/filter applied doesn't remove a record that's filtered out
+   EXTJS-18084 Store.rejectChanges works on filtered records instead of source data
+   EXTJS-18231 Error thrown on submitting form in Direct example

DataView (2)

+   EXTJS-17621 Pull Refresh not working
+   EXTJS-17812 The DataView itemremove event now fires once for a block removal from the underlying store. An array of removed items is passed rather than a single item.

Direct (1)

+   EXTJS-16193 Invocation arguments for Ext.direct.RemotingProvider#beforecallback (event) are inconsistent

Events (1)

+   EXTJS-17220 isSpecialKey returns true for ! and # in editor

Examples (26)

+   EXTJS-17185 Welcome folder is not included into build
+   EXTJS-17261 Wrong paths are generated for Chart examples source in modern toolkit
+   EXTJS-17707 Source button is not shown when modern example visited repeatedly
+   EXTJS-17919 getModeToggleButton is not a function error on modern charts with renderer
+   EXTJS-17943 Server-side security flaw in Feed Viewer example
+   EXTJS-17954 Info icon not shown in Linear Data Geographical Tree example
+   EXTJS-17970 Stand-alone examples fail to load charts-all.css and ux-all.css when using Triton theme
+   EXTJS-18022 AMF Grid example is not loading
+   EXTJS-18043 Missing fonts in standalone examples
+   EXTJS-18095 SenchaDash - error getScrollable().isInView is not a function
+   EXTJS-18096 Admin dashboard 3D Pie chart is not visible in Chart overview
+   EXTJS-18097 SenchaDash - Error thrown after loading example - IE8
+   EXTJS-18099 Admin dashboard missing menu toggle button on IE8
+   EXTJS-18104 Admin dashboard has some icons shifted on iPads
+   EXTJS-18110 Missing icons/glyphs in modern examples
+   EXTJS-18120 Modern ChainedStore example fails to load
+   EXTJS-18154 Error thrown on destroying Locking Grid on touch devices
+   EXTJS-18155 Routing doesn't work in KS Chart examples
+   EXTJS-18173 Executive dashboard initial load broken
+   EXTJS-18201 Modern theme - KS > Charts: Candle Stick and Line With Icons doesn't load
+   EXTJS-18212 Geo Congress example throws an error if you select a person
+   EXTJS-18213 Settings icon not visible in GeoCongress example
+   EXTJS-18233 Energy app in modern examples - Charts not loading
+   EXTJS-18300 Modern example - Energy app - broken radial charts
+   EXTJS-18326 Animation - Cannot go back - h.setReverse is not a function, Mobile phones
+   EXTJS-18352 Modern example - Big data grid - slider doesn't appropriately respond to user input

Forms (12)

+   EXTJS-17195 Tapping error icon causes a JS error in Chrome on Windows 8 Touch devices
+   EXTJS-18017 Not working file upload function in Kitchen Sink examples
+   EXTJS-18034 textfield selectOnFocus doesn't work properly
+   EXTJS-18122 Filefield no longer open select file window for IE11 when embedded in tbar menu 5.1.1
+   EXTJS-18134 Input list element is a different height from tag elements.
+   EXTJS-18157 Checkbox with no boxLabel not visible
+   EXTJS-18194 Multiple thumb > one thumb goes across second thumb, after second interaction
+   EXTJS-18203 FieldContainer fieldlabel mixin in FF was not hiding label if not specified
+   EXTJS-18211 Sliders > Multiple thumbs > thumbs are moving unexpectedly, if they are getting too close
+   EXTJS-18246 Modern toolkit - Clear button (x) exceeds a text field, modern neptune and triton
+   EXTJS-18267 Checkbox is checked and unchecked after single tap
+   EXTJS-18382 Color field triggers errors when the color picker is closed by ESC and reopened

Grid (48)

+   EXTJS-12841 Mouse based grid row dragging does not work on touch enabled platforms
+   EXTJS-15336 Grid empty text is not shown when store loads while hidden/collapsed
+   EXTJS-16146 TableView#enableTextSelection not working
+   EXTJS-16708 Row editing plugin does not properly position OK/Cancel buttons for variable row heights
+   EXTJS-16800 GridView's disableSelection isn't being passed to the selection model constructor
+   EXTJS-17151 RowEditor isValid() method overwritten with boolean value
+   EXTJS-17255 Row should not be selected when navigating within the row
+   EXTJS-17419 Positioning using CSS transforms for a buffered rendered grid can lose its scroll position in a card layout
+   EXTJS-17459 Grouping on a grid bound to a buffered store results in an error when grouping on a column with a renderer
+   EXTJS-17525 Exception thrown when clicking on the checkbox column header of a grid with an empty store with selectionMode="SINGLE"
+   EXTJS-17557 Grid with summary feature can leak memory in IE especially using XML
+   EXTJS-17776 Grouping is not working when groupKey is an empty string
+   EXTJS-17799 Removing last row in grid with row editing plugin throws error
+   EXTJS-17801 Spreadsheet selection "extender" does not reposition on column resize
+   EXTJS-17821 Mouseup from grid header resize or drag results in a click.
+   EXTJS-17823 Grouped Grid - group is not collapsed after tapping on group name in list
+   EXTJS-17826 Moving columns on tablet is not possible after column resizing
+   EXTJS-17839 Shrinkwrap width grid headers get wrong measured width in Triton
+   EXTJS-17916 Reconfiguring locked grid with summary feature throw exception
+   EXTJS-17921 Key navigation in a spreadsheet selection doesn't work when using colspan
+   EXTJS-17924 Extender drag handle is shown over column headers
+   EXTJS-17939 Cannot edit cells after removing row with active cell editor
+   EXTJS-17975 Renderer scope is lost in Ext.tree.Column
+   EXTJS-17979 View height increase may leave buffer rendered block at incorrect position.
+   EXTJS-18025 Removing row in grid with row editing plugin throws error when not in actionable mode
+   EXTJS-18041 Cannot tab through cells in row editing plugin - Firefox only
+   EXTJS-18042 Error thrown in the console when editing cell in Locking, Group Summary Grid Example
+   EXTJS-18047 Error is thrown in the console when scrolling the grid in Locking Grouping Summary grid example
+   EXTJS-18049 autoLoad configured on the Grid will fail when the store is bound from the ViewModel
+   EXTJS-18062 Cannot open links in grid on tablets
+   EXTJS-18064 Spreadsheet selectRows errors when a non-row selection exists
+   EXTJS-18082 Cannot paste text into a textfield in a grid toolbar when using clipboard plugin
+   EXTJS-18083 GroupStore throws when last item of a group is removed
+   EXTJS-18088 Cannot scroll grid horizontally all the way to the end on touch devices
+   EXTJS-18123 getVisibleColumns method broken for locked grids
+   EXTJS-18135 Inserted at zero record in a grid store displays as a blank row when scrolled down.
+   EXTJS-18178 Header menu doesn't show on click in IE9
+   EXTJS-18202 selectionchange event fires twice on a grid with a locked column
+   EXTJS-18225 Memory leak in list grid filter
+   EXTJS-18240 Modern example - Big data grid - too small rows in some themes
+   EXTJS-18260 Modern Grid Paging Toolbar plugin doesn't maintain correct number of pages, can't scroll back to 1, and explodes if you have fewer than 8 items
+   EXTJS-18276 Grid DragDrop plugin appends dropped records to end of Store
+   EXTJS-18285 grouping will no longer expand if you reorder columns
+   EXTJS-18325 Grids cannot be scrolled beyond their buffered rendering size on touch devices
+   EXTJS-18339 Modern grid header menu doesn't work, and needs styling in all themes
+   EXTJS-18372 Big data grid example, scroller height much too large
+   EXTJS-18377 Modern example - Big data grid - scrollbar not sized correctly
+   EXTJS-18381 Modern Grid Paging Toolbar plugin - Maximum Call Stack errors if number of items is too small for two pages

Layouts (3)

+   EXTJS-17762 Ext.navigation.View not showing animation when pushing a new card
+   EXTJS-17978 Card layout items are not preserving scroll position when hidden
+   EXTJS-17984 Frame is not displayed in border layout - touch screen

Locale (1)

+   EXTJS-17834 In localization examples some sign letters from Japanese and Korean alphabet are incorrectly drawn

Menu (1)

+   EXTJS-17467 MenuItem with Checkbox AND submenu hides submenu on checkbox toggle.

Misc (4)

+   EXTJS-17342 ExtJS 6 Beta sencha.cfg - wrong version
+   EXTJS-17840 closable === false on Ext.Msg results in script error
+   EXTJS-18150 MISCELLANEOUS > History-Router - Cannot go back on original page
+   EXTJS-18234 Missing text on navigate button in modern Example Energy app - iPhone 6

Panel (4)

+   EXTJS-17731 Panel title ignored if the type is numeric.
+   EXTJS-17886 Collapsing a panel that contains the focus element causes an exception
+   EXTJS-18089 Ext.dom.Element doesn't fired the painted event
+   EXTJS-18125 Panel expand has null exception while hideCollapseTool set to true

PivotGrid (5)

+   EXTJS-18024 Value filters not working in Pivot grid with configurator plugin
+   EXTJS-18069 Value filter window incorrectly drawn in Pivot Grids - Configurator plugin example
+   EXTJS-18071 Filters on top axis dimensions lead to wrong row totals
+   EXTJS-18072 Error in the console when using value filter on Pivot Grids - Configurator Plugin example
+   EXTJS-18133 Adding a Value filter with an '=' operator doesn't find any results

Scroller (1)

+   EXTJS-18159 Scrollbar for infinite lists has incorrect range on desktop devices in modern toolkit

Tabs (1)

+   EXTJS-18364 Tab rotation is broken in IE8

Theme (9)

+   EXTJS-17160 Ext JS classic toolkit should support using glyphs via css class name
+   EXTJS-17692 Cannot add !important to mixin parameters using Fashion
+   EXTJS-17987 Styling is missing in validation status plugin - Triton theme
+   EXTJS-18074 THEME CSS Mixins: google-webfont & https problem
+   EXTJS-18172 Cupertino theme buttons not styled correctly
+   EXTJS-18205 Border color wrong in locked grids
+   EXTJS-18236 Normal Button - Looks like a different type. Animation of pressing is not appear. Cupertino theme
+   EXTJS-18328 Enterprise - grids are misaligned on some themes
+   EXTJS-18376 Triton theme tabs background color turns black on hover in IE8

Toolbars (1)

+   EXTJS-18039 Breadcrumb: wrong path (parentNode) when reselecting childNode from different parent

Tree (5)

+   EXTJS-18016 Opening nodes in scrolled tree causes view to scroll up and down
+   EXTJS-18229 Incorrect scroll in sorted tree after drag and drop
+   EXTJS-18299 TreeList --> Re-Collapse/Expand cause error in console, this.targetArr is null
+   EXTJS-18355 Bad indentation in Tree List
+   EXTJS-18385 Tree.select not working on a non-scrollable tree

Window (2)

+   EXTJS-18033 Toasts should not render close tool by default when autoClose == true
+   EXTJS-18200 Source window is not scrollable in modern KitchenSink charts examples

## Known Issues

Accessibility (15)

+   EXTJS-10456 VoiceOver for Mac is not supported
+   EXTJS-10467 Menu overflow scrollers are not navigable using the keyboard
+   EXTJS-10477 HtmlEditor is not accessible
+   EXTJS-10479 LoadMask is not accessible
+   EXTJS-10480 Color Picker is not accessible
+   EXTJS-10490 Progress Bar is not accessible
+   EXTJS-10491 Property Grid is not accessible
+   EXTJS-10492 DragDrop is not accessible
+   EXTJS-10493 Paging Toolbar is not accessible
+   EXTJS-10496 Grouped grid headers are not accessible
+   EXTJS-10497 Grid row expander is not accessible
+   EXTJS-10498 Grid RowBody feature is not accessible
+   EXTJS-10499 Grid CheckboxSelectionModel is not accessible
+   EXTJS-10503 Grid headers cannot be resized using the keyboard
+   EXTJS-10504 Grid Headers cannot be reordered using the keyboard

Button (1)

+   EXTJS-16118 Kitchen Sink - Form Fields: Browse local files button doesn't work on iOS8

Charts (1)

+   EXTJS-10739 RTL Charts do not correctly display bidirectional text

Core (1)

+   EXTJS-17885 Modern toolkit should provide an Ext.setup equivalent method

DataView (1)

+   EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad

Examples (1)

+   EXTJS-13879 Dashboard Portal drag-n-drop experience is not optimal especially on tablets

Grid (2)

+   EXTJS-10494 ARIA - Grid Grouping Feature is not supported
+   EXTJS-10495 ARIA - Locking Grid is not supported.

Layouts (1)

+   EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container

Tabs (1)

+   EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0

Theme (2)

+   EXTJS-17790 Triton should support tree lines
+   EXTJS-9806 ext-theme-aria does not support Windows high-contrast mode

ToolTips (1)

+   EXTJS-10475 ARIA - ToolTip is not supported

Tree (1)

+   EXTJS-10451 ARIA - The Tree component is not supported.

#Release Notes for Ext JS 6.0.0 Beta

Release Date: May 25, 2015
Version Number: 6.0.0.415

##New Features

Charts (5)

+ EXTJS-15657 Add support for full-stacked (100% stacked) charts.

+ EXTJS-17388 Add support for itemhighlight interaction and itemevents to 3D Pie series

+ EXTJS-17478 itemhighlight interaction should be automatically added when the series has highlight: true

+ EXTJS-17566 3D pie and 3D bar series should have a colorSpread attribute to control gradients

+ EXTJS-17596 Charts and series should fire a storechange event

Forms (1)

+ EXTJS-15280 ComboBox should allow a GridPanel to be used as the picker

Grid (3)

+ EXTJS-17257 RowEditor should navigate between rows on TAB out of either end of editable fields.

+ EXTJS-17332 Shift-select columns with the spreadsheet selection model

+ EXTJS-9554 ActionColumn should support glyphs

PivotGrid (1)

+ EXTJS-17766 Configurator should support configurable docking

Total: 10

##Bugs Fixed

Accessibility (3)

+ EXTJS-15550 Grid is announced as editable even when its not

+ EXTJS-15821 JAWS does not announce grids properly

+ EXTJS-17582 Column text config set as raw HTML inside aria-attribute

App (2)

+ EXTJS-14877 Calling redirectTo within the route will override the hash on initial route exec

+ EXTJS-17423 Ext.app.Application and Ext.application overwrite path information from Cmd due to appFolder config

Bind (1)

+ EXTJS-17221 Bound selection points to wrong record after reload

Charts (11)

+ EXTJS-15255 Memory leaks with charts

+ EXTJS-16246 Charts Pie series lengthField configured throws error when record is deleted from store

+ EXTJS-16478 Line chart series don't render correctly (not filled) with `fill` and `smooth` config

+ EXTJS-16703 Charts placed on unrendered tabs of a tabpanel do not work properly

+ EXTJS-17433 Chart destroy does not check autoDestroy on store (leads to js error)

+ EXTJS-17496 3d bars won't be displayed after chart has been loaded with an empty store (if animation is enabled)

+ EXTJS-17703 3D Pie slices shouldn't have a stroke (by default)

+ EXTJS-17711 Tap/click on any of charts in modern toolkit causes application crash

+ EXTJS-17718 Zoom / Pan buttons are missing - Kitchen Sink Charts

+ EXTJS-17742 3D Pie chart drawn wrong when rotated to certain angles

+ EXTJS-17803 Column charts - blank tooltip - Triton theme only

Cmd (1)

+ EXTJS-17425 Fresh universal project does not 'sencha app refresh'

Core (12)

+ EXTJS-15881 menu reference lookup fails when attached to button

+ EXTJS-16242 Observable constructor should be re-callable

+ EXTJS-16737 Not possible to load ext-all-debug.js on demand

+ EXTJS-17517 Paint monitoring fails in latest versions of Chrome (34+)

+ EXTJS-17533 Floaters always realign themselves on any scroll event regardless of whether they need to or not.

+ EXTJS-17630 Ext.mixin.Bindable.removeBindings Exception

+ EXTJS-17760 Ext.Mask initialize() doesn't set scope for hide event

+ EXTJS-17761 Navigation view shows Back button even on first card.

+ EXTJS-17816 Modern toolkit app is unusable on Windows touch screen devices

+ EXTJS-17871 Size monitoring fails in latest versions of Chrome (34+)

+ EXTJS-17918 namespace.OverflowChange is not a constructor error on Firefox

+ EXTJS-9456 toQueryString doesn't decode + as space

Data (10)

+ EXTJS-13795 Ext.Ajax singleton should support setting CORS value

+ EXTJS-15785 Loading XML can result in memory leaks in IE (added "keepRawData" config to Reader)

+ EXTJS-16234 Buffered Store: Redundant loading of datastore when filtering

+ EXTJS-16347 Autoload=false and stateful grid store always loads

+ EXTJS-16388 Buffered Store does not execute callback for empty data set or on error

+ EXTJS-17168 In sandbox mode, application of default values to fields calls 'Ext.clone' and results in 'Ext is not defined' error

+ EXTJS-17238 rejectChanges() throws if store has one or more sorters

+ EXTJS-17270 Store currentPage not always synced with actual loaded page.

+ EXTJS-17360 On a filtered store, changing an item so it no longer matches the filter unjoins it from the store

+ EXTJS-17441 Fields with convert methods are marked as persist: false

DataView (3)

+ EXTJS-17139 LoadMask stays visible if a store load encounters a proxy exception

+ EXTJS-17233 Ext.view.View - adding  new record to store adds element in wrong place when using a template with a wrapping element

+ EXTJS-17317 MultiSelect grid. Pre selected items are not checked in the selection grid.

Draw (4)

+ EXTJS-17702 Composite sprite should delete its children when it's being destroyed

+ EXTJS-17795 The 'angle' method of the AttributeParser should normalize -Pi and +Pi to the same value.

+ EXTJS-17796 fontWeight processor for Text sprite doesn't follow the spec

+ EXTJS-17869 Draw container fires erroneous 'resize' event (should be named 'bodyresize')

Examples (10)

+ EXTJS-14436 ARIA: Keyboard Navigation: Content panel: Tools on the header of the panel are not working (Refresh or help)

+ EXTJS-14710 Kitchensink: Main page doesn't correctly show icons for groups of examples IE8

+ EXTJS-16810 Missing icons for examples in KitchenSink

+ EXTJS-17133 Wrong path in Dynamic localization example

+ EXTJS-17135 Grouping feature assumes that groupField lookups in the record results in a String

+ EXTJS-17326 KitchenSink chained combos - selecting a new contry doesn't clear the previous country's state

+ EXTJS-17365 Can not appendChild to tree in KS navigation tree when tree is collapsed

+ EXTJS-17396 Infographic: tapping on a state doesn't highlight its slice or update the state name label

+ EXTJS-17607 Double click on remove button opens row editor

+ EXTJS-17647 Click on remove button opens row editor - KS>Chaining Stores example

Forms (12)

+ EXTJS-13033 ComboBox - hideTrigger not working when set in initComponent

+ EXTJS-15330 Ext.form.field.File does not fire the focus or blur event

+ EXTJS-15981 KS: Custom error handling - Error msg persists in error summary 

+ EXTJS-16817 TagField generates corrupted markup for tags if their display value contains markup characters

+ EXTJS-16820 Tagfield does not realign picker when height changes

+ EXTJS-16825 allowOnlyWhitespace on TagField doesn't work

+ EXTJS-17049 Combo clearValue broken when forceSelection is true

+ EXTJS-17146 Need double tap to edit fields on iOS

+ EXTJS-17180 Tagfield with allowblank false always returns errors

+ EXTJS-17216 Tagfield with binding to view model store throws 'Ext.data.Store created with no model' warning

+ EXTJS-17390 Document comobox's getSelection method

+ EXTJS-17705 Field label has wrong position - modern toolkit

Grid (26)

+ EXTJS-15810 Focusing 'action column' causes error

+ EXTJS-15851 Continuous scrolling in buffer store causes incorrect display of records

+ EXTJS-15892 Locked grid scrolls badly in Firefox with mouse wheel

+ EXTJS-16022 LiveSearchGridPanel - Uncaught TypeError: Cannot read property 'down' of null

+ EXTJS-16084 paginate grid doesn't scroll top when we load page on nightly

+ EXTJS-16397 Grid column autosize creates cell overflow in FF in nightly builds

+ EXTJS-16430 Ext.grid.column.Action disabled config does not generate proper CSS className

+ EXTJS-16608 Shift click to multi-select doesn't work with cellediting

+ EXTJS-16644 When scrolling a grid horizontally using trackpad, headers are misaligned with columns

+ EXTJS-17105 Adding cellediting after grid init caused error on cellclick

+ EXTJS-17178 Widgets are not reused when a store reloads

+ EXTJS-17223 Grid navigation model should react to programmatic cell focus

+ EXTJS-17224 Wrong focus placement in editable Grids in Firefox

+ EXTJS-17303 When scrolling derenders the activeElement, grid loses track of focus.

+ EXTJS-17316 Tabbing into grid doesn't work if there's RowExpander in use

+ EXTJS-17321 Column resizing goes to locked size when resizing the leftmost grouped header on the non-locked size

+ EXTJS-17324 Spreadsheet selection model does not fire change event on clearing selection

+ EXTJS-17325 KitchenSink spreadsheet grid - selection styling remains after deselection

+ EXTJS-17349 Row editor isn't positioned correctly when adding and editing last row in view

+ EXTJS-17391 Extraneous values in widgetcolumn with tristate chart

+ EXTJS-17470 Removal of record with Widget column does not remove widget, so it is destroyed.

+ EXTJS-17485 Grid refresh with buffered renderer causes an error on Windows 8 touch devices

+ EXTJS-17678 Grouping feature rendered incorrectly when stateful

+ EXTJS-17704 Grid column header sort indicator is misaligned

+ EXTJS-17744 widgetcolumn - error when collapse group

+ EXTJS-17824 this.dom is undefined in KS examples with paging

Layouts (2)

+ EXTJS-16101 Viewport fails to fill entire viewable area on Safari iOS 8.1

+ EXTJS-17536 Form reset breaks layout in IE8

Menu (3)

+ EXTJS-17284 ColorMenu throws exception when selecting item

+ EXTJS-17399 KS - Grouped Grid - example freezes after selecting specific groups - on Mobile devices

+ EXTJS-17654 Cannot bind checkHandler for CheckItem menus to a ViewController

Misc (1)

+ EXTJS-16473 Sparklines are blurry on Hi-DPI displays

Panel (2)

+ EXTJS-16173 Component scroll position is reapplied from previously destroyed component (Gecko)

+ EXTJS-9505 collapseMode: 'mini' misbehaves in west/north regions (webkit)

PivotGrid (3)

+ EXTJS-17800 Non-sortable columns can be sorted in PivotGrid

+ EXTJS-17804 PivotGrid column sorting issue when having more than 2 sortable columns

+ EXTJS-17829 Sorting in compact view doesn't work properly

Tabs (3)

+ EXTJS-14738 "Unable to get property 'dom' of undefined or null reference" changing the tabs position or rotation on IE8 and IE9 (RTL)

+ EXTJS-17289 TabPanel doesn't move tab bar items for moveBefore/moveAfter methods

+ EXTJS-17408 Reorderable tabs are broken - drops on wrong positions / become invisible

Theme (3)

+ EXTJS-17632 Sass color mix method fails on hsla colors

+ EXTJS-17652 Tool icons are big in Neptune touch and Crisp touch themes

+ EXTJS-17710 Background color of MountainView theme should be dark gray

ToolTips (1)

+ EXTJS-15171 Slider example with tooltips: tooltips shows in wrong area

Toolbars (1)

+ EXTJS-17540 Field in toolbar does not get value propagated into its clone in the overflow menu

Tree (7)

+ EXTJS-17214 Treestore beforesort event is not fired

+ EXTJS-17265 defaultListenerScope doesn't work in TreePanel-TreeColumn renderer

+ EXTJS-17322 TreePanel store API is not consistent with Grid

+ EXTJS-17366 TreeModel does not handle defaultValue correctly

+ EXTJS-17367 TreePanel cannot have the "store" config set dynamically

+ EXTJS-17401 KS>Trees> Tree Reordering - throws js exception when dnd is performed

+ EXTJS-17406 Trees with drag and drop functionality  - nodes are dropped into wrong folders, or not changing positions at all

Total: 121

##Known Issues

Accessibility (15)

+ EXTJS-10456 VoiceOver for Mac is not supported

+ EXTJS-10467 Menu overflow scrollers are not navigable using the keyboard

+ EXTJS-10477 HtmlEditor is not accessible

+ EXTJS-10479 LoadMask is not accessible

+ EXTJS-10480 Color Picker is not accessible

+ EXTJS-10490 Progress Bar is not accessible

+ EXTJS-10491 Property Grid is not accessible

+ EXTJS-10492 DragDrop is not accessible

+ EXTJS-10493 Paging Toolbar is not accessible

+ EXTJS-10496 Grouped grid headers are not accessible

+ EXTJS-10497 Grid row expander is not accessible

+ EXTJS-10498 Grid RowBody feature is not accessible

+ EXTJS-10499 Grid CheckboxSelectionModel is not accessible

+ EXTJS-10503 Grid headers cannot be resized using the keyboard

+ EXTJS-10504 Grid Headers cannot be reordered using the keyboard

Bind (1)

+ EXTJS-17758 Modern toolkit textfields do not update two-way bindings as you type

Button (1)

+ EXTJS-16118 Kitchen Sink - Form Fields: Browse local files button doesn't work on iOS8

Charts (1)

+ EXTJS-10739 RTL Charts do not correctly display bidirectional text

Core (2)

+ EXTJS-12058 Sandbox mode is not working

+ EXTJS-17885 Modern toolkit should provide an Ext.setup equivalent method

DataView (1)

+ EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad

Examples (1)

+ EXTJS-13879 Dashboard Portal drag-n-drop experience is not optimal especially on tablets

Grid (3)

+ EXTJS-10494 ARIA - Grid Grouping Feature is not supported

+ EXTJS-10495 ARIA - Locking Grid is not supported.

+ EXTJS-17826 Moving columns on tablet is not possible after column resizing

Layouts (1)

+ EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container

Misc (1)

+ EXTJS-17762 Ext.navigation.View not showing animation when pushing a new card

Tabs (1)

+ EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0

Theme (3)

+ EXTJS-17770 Triton theme has visual issues on IE8

+ EXTJS-17790 Triton should support tree lines

+ EXTJS-9806 ext-theme-aria does not support Windows high-contrast mode

ToolTips (1)

+ EXTJS-10475 ARIA - ToolTip is not supported

Tree (1)

+ EXTJS-10451 ARIA - The Tree component is not supported.

Total: 33

#Release Notes for Ext JS 5.1.1

Release Date: May 7, 2015

Version Number: 5.1.1.451

##Noteworthy

Viewports and iOS8 Ext JS requires a viewport meta tag in order to control the layout of the viewport
in mobile browsers.  In previous releases this tag was dynamically
appended to the document head for applications that used Ext.plugin.Viewport
or Ext.container.Viewport.  As of iOS8 dynamic addition of the viewport
tag no longer works correctly, resulting in incorrect measurement of
viewport size on initial layout.  As a result Ext JS now requires
that applications add the following viewport meta tag directly to their
index.html pages:

    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">

##New Features

Accessibility (1)

+ EXTJS-13482 Border layout splitter should support keyboard interaction

Bind (1)

+ EXTJS-15695 Allow initial data to be specified with the create option in viewmodel links

Charts (1)

+ EXTJS-16605 Axis and Series should support named listeners and dispatch them to the appropriate controller or scope

Core (1)

+ EXTJS-10906 Add lazy instantiation plugin

Data (1)

+ EXTJS-17588 Readers need a "keepRawData" config to discard its "rawData" when possible (holding XML documents causes leaks in IE)

Forms (1)

+ EXTJS-16603 Combobox should provide a getRecordDisplayData method for augmenting display value generation

Grid (1)

+ EXTJS-16297 Cell editors should support Ext.Widget classes as editors

Total: 7

##Bugs Fixed

Accessibility (4)

+ EXTJS-15526 Ext.menu.CheckItem doesn't update it's aria-checked attribute

+ EXTJS-15914 Ext.FocusManager.enable() throwing an error

+ EXTJS-16216 Disabling the focused Component must result in intelligent focus adjustment.

+ EXTJS-16280 LoadMask focusing breaks paging ComboBox

Animation (1)

+ EXTJS-11596 slideIn/slideOut positions element incorrectly

App (2)

+ EXTJS-14877 Calling redirectTo within the route will override the hash on initial route exec

+ EXTJS-16764 ViewController. beforeInit - missing view parameter

Bind (6)

+ EXTJS-15041 Number field with binding can cause the user typed value to be overwritten with a trimmed to decimalPrecision value

+ EXTJS-16167 Unable to set boxLabel if not initially configured

+ EXTJS-16579 Setting a field in an associated record via a binding doesn't work correctly

+ EXTJS-16793 DataView with selected record and binding a new store causes exception

+ EXTJS-17221 Bound selection points to wrong record after reload

+ EXTJS-17376 ViewModel destroy method can cause noticeable delay when using lots of formulas

Button (1)

+ EXTJS-15211 Vertical segmented buttons have incorrect styling in RTL mode

Charts (23)

+ EXTJS-15082 Bar graph legend broken with one yField charted

+ EXTJS-15560 3D Pie charts lack 3d gradient effect

+ EXTJS-15882 Charts do not set defaultBindProperty (should be "store")

+ EXTJS-15885 Series labels should animate with their data point

+ EXTJS-15978 Column chart - With renderer - Icons with values are shifted down - firefox

+ EXTJS-16198 Chart setTheme does not work when animation: false

+ EXTJS-16246 Charts Pie series lengthField configured throws error when record is deleted from store

+ EXTJS-16254 Axis rangechange event is fired multiple times

+ EXTJS-16272 bar3d series 'style' config attributes brightnessFactor and saturationFactor don't propagate to the box sprite

+ EXTJS-16342 Ext.draw.Container or derived classes do not rendered properly in a widgetcolumn with large data sets

+ EXTJS-16354 Gauge series throws error when using setTitle()

+ EXTJS-16410 Using setHidden() on series does not update chart legend

+ EXTJS-16503 Chart.axes config should be able to accept Ext.chart.axis.Axis instances

+ EXTJS-16675 Radial axis labels can be clipped

+ EXTJS-16703 Charts placed on unrendered tabs of a tabpanel do not work properly

+ EXTJS-16738 Chart itemevents plugin fires mouse events in reverse order of itemmouseover before itemmouseout

+ EXTJS-16746 Chart innerPadding config doesn't work with pie3d series

+ EXTJS-16748 The outer side of pie3d series doesn't have a proper z-index

+ EXTJS-17082 Series with tooltip can cause multiple itemhighlight interactions to be created

+ EXTJS-17097 Chart with both tooltip and itemhighlight interaction does not highlight properly

+ EXTJS-17421 Setting the series for a chart using setSeries() not working

+ EXTJS-17433 Chart destroy does not check autoDestroy on store (leads to js error)

+ EXTJS-17496 3d bars won't be displayed after chart has been loaded with an empty store (if animation is enabled)

Coding Style (1)

+ EXTJS-16172 Application - missing semi-colon in the constructor method var block

Core (24)

+ EXTJS-11672 Panel's starting X Y offset calculated incorrectly when rendered to a div and constrained

+ EXTJS-14540 previousFocus is not sufficient to do focus tracking

+ EXTJS-15242 Element.setSizeState calls array indexof directly

+ EXTJS-15247 The AMF provider for Ext.Direct has calls to deprecated addEvents method

+ EXTJS-15881 menu reference lookup fails when attached to button

+ EXTJS-16125 Ext.Img destroy causes "Cannot destroy Element" warning when src is configured (using a glyph does not)

+ EXTJS-16180 Enabling a container doesn't correctly unmask child components

+ EXTJS-16242 Observable constructor should be re-callable

+ EXTJS-16270 Listeners declared on component plugins do not resolve scope "controller" correctly

+ EXTJS-16283 Ext.ZIndexManager.hideAll does not reset flag correctly

+ EXTJS-16316 ext-bootstrap.js will not load the proper ext-all*.js file

+ EXTJS-16352 Ext.dom.Element.setCls() function can throw an exception in some cases

+ EXTJS-16387 Shadow not synchronized on move when the window has negative left/top position

+ EXTJS-16442 Date regex for 'y' accepts single digit year

+ EXTJS-16462 Translated event listeners are not called when the event name contains uppercase characters

+ EXTJS-16466 Dates that cannot be parsed return undefined instead of null

+ EXTJS-16594 stopEvent/preventDefault/stopPropagation ignored as element listener options

+ EXTJS-16613 Focusable components require two clicks to activate in Firefox

+ EXTJS-16642 Container#moveBefore/moveAfter moves child to incorrect index when moving up (5.1.0)

+ EXTJS-16737 Not possible to load ext-all-debug.js on demand

+ EXTJS-16777 Focusing an Ext.Widget can result in "Cannot read property 'isFocusable' of null or 'focus' of null"

+ EXTJS-16794 ObjectTemplate applies empty object to null values in template

+ EXTJS-16984 Ext.Widget listeners declared in subclasses get cached on their superclass

+ EXTJS-9456 toQueryString doesn't decode + as space

Dashboard (2)

+ EXTJS-16174 Cannot programmatically add Views to Ext.dashboard.Dashboard

+ EXTJS-16601 Dashboard: Can't drag portlets to last position in a column once panel has overflowed

Data (33)

+ EXTJS-11490 TreeStore: added sub-children nodes are not phantoms

+ EXTJS-15218 Record dropped state is not reset on reject()

+ EXTJS-15332 Poor performance when loading records with lots of associations

+ EXTJS-15785 Loading XML can result in memory leaks in IE (added "keepRawData" config to Reader)

+ EXTJS-15994 BufferedStore sort does not position the scroll properly

+ EXTJS-16100 Store's rejectChanges method should batch UI updates

+ EXTJS-16135 Store removedRecords doesn't remove erased records

+ EXTJS-16293 Ext.util.Collection sometimes adds records at an incorrect position when adding multiple items to a grouped collection

+ EXTJS-16326 getField doesn't return the correct field when changing the idProperty with subclass

+ EXTJS-16337 Ext.data.reader.Reader copyFrom incomplete

+ EXTJS-16347 Autoload=false and stateful grid store always loads

+ EXTJS-16356 Ext.data.field.Field convert should not be called for the defaultValue

+ EXTJS-16361 Exception when attempting deep copy a TreeNode

+ EXTJS-16369 Remote sorting ignored in grouped grid

+ EXTJS-16388 Buffered Store does not execute callback for empty data set or on error

+ EXTJS-16451 NodeInterface.removeAll does not account for nodes that do not have treestore

+ EXTJS-16492 Modifying a record so that it becomes filtered out causes the record to be added to the removed collection

+ EXTJS-16493 Tree root node shouldn't be included in TreeStore's rejected records list

+ EXTJS-16494 The constructor of Ext.data.Model fails to set me.data on older iPads (4th gen and below - Safari JIT bug)

+ EXTJS-16497 Polling Tree Store Memory Leak

+ EXTJS-16505 Model getData does not pass options (serialize/changes etc) when getting associated data

+ EXTJS-16655 Ext.data.Validation.isValid returns incorrect value

+ EXTJS-16695 Store update event has old value of reference fields. Reference not set correctly when key already exists

+ EXTJS-16786 Session.update drop does not handle writeAllFields:true

+ EXTJS-16790 loadData does not clear entire store when filter exists

+ EXTJS-16824 When using inline, linear data, tree store load() throws error

+ EXTJS-17062 TreeStore#commitChanges does not clear removedNodes

+ EXTJS-17168 In sandbox mode, application of default values to fields calls 'Ext.clone' and results in 'Ext is not defined' error

+ EXTJS-17230 Connection onStateChange has bad check for "isXDR" (needs to use the accessor)

+ EXTJS-17238 rejectChanges() throws if store has one or more sorters

+ EXTJS-17270 Store currentPage not always synced with actual loaded page.

+ EXTJS-17360 On a filtered store, changing an item so it no longer matches the filter unjoins it from the store

+ EXTJS-17441 Fields with convert methods are marked as persist: false

DataView (2)

+ EXTJS-17233 Ext.view.View - adding  new record to store adds element in wrong place when using a template with a wrapping element

+ EXTJS-17317 MultiSelect grid. Pre selected items are not checked in the selection grid.

Draw (3)

+ EXTJS-16383 SpriteEvents Plugin Doesn't Fire Events

+ EXTJS-16405 createLighter/createDarker method does not respect factor of 0

+ EXTJS-16745 spriteevents plugin fires mouse events in reverse order of spritemouseover before spritemouseout

Events (3)

+ EXTJS-15169 TreeStore.clearFilters ignores the supressEvent param

+ EXTJS-16189 Ext.util.Observable static methods "capture", "releaseCapture", and â€œobserveâ€ moved to Ext.mixin.Observable

+ EXTJS-17271 Click event added to anchor element no longer triggered for IE 

Examples (15)

+ EXTJS-12984 Phone field should not accept string in Kitchen Sink\ Field container example 

+ EXTJS-14710 Kitchensink: Main page doesn't correctly show icons for groups of examples IE8

+ EXTJS-15729 Locking Grouping Summary Grid example - Toggle button does not work

+ EXTJS-15855 Cannot read property 'tBodies' of null when navigating between examples on tablets

+ EXTJS-16187 Page Analyzer throws error and won't load

+ EXTJS-16725 Ext.ux.event.Recorder uses old Ext.EventObject.setEvent method

+ EXTJS-16726 Ext.ux.event.Recorder click event sets button to true

+ EXTJS-16810 Missing icons for examples in KitchenSink

+ EXTJS-16956 Ext.ux.event.Player does get the speed when events are being played

+ EXTJS-17001 Live search grid example doesn't focus results

+ EXTJS-17037 Ext.ux.google.Api hardcoding http protocol so get: was loaded over HTTPS...blocked;

+ EXTJS-17135 Grouping feature assumes that groupField lookups in the record results in a String

+ EXTJS-17326 KitchenSink chained combos - selecting a new contry doesn't clear the previous country's state

+ EXTJS-17605 Kitchen Sink throws error and will not load when navigation is collapsed

+ EXTJS-17607 Double click on remove button opens row editor

Forms (50)

+ EXTJS-13033 ComboBox - hideTrigger not working when set in initComponent

+ EXTJS-15204 Filefield allows user to enter text 

+ EXTJS-15330 Ext.form.field.File does not fire the focus or blur event

+ EXTJS-15473 Can't Set Initial Value for ComboBox with Empty Store

+ EXTJS-15476 Ext.form.field.Picker - Picker incorrectly aligned after window resize.

+ EXTJS-15497 Calling setReadOnly beforeshow results in trigger processing being skipped.

+ EXTJS-15664 emptyText not removed on focus

+ EXTJS-15936 Readonly form fields and comboboxes should not react to keyup event

+ EXTJS-16005 Tagfield does not calculate height correctly in some cases when auto heighting with wrapping

+ EXTJS-16027 tagfield backspace/delete erase all selected items

+ EXTJS-16046 datepicker collapses when month picker selected after showing tooltip

+ EXTJS-16126 HTMLEditor adds duplicate lines in IE10 and below

+ EXTJS-16152 Picker collapses on ENTER key when the picker is a grid and is editable and is being edited

+ EXTJS-16155 ComboBox - findRecordByValue and findRecordByDisplay return undefined when record not found instead of false

+ EXTJS-16156 Ext.form.field.ComboBox.doSetValue() - typo in warning message

+ EXTJS-16188 Textfield's selectOnFocus handling can cause infinite loop

+ EXTJS-16190 ComboBox autoLoadOnValue. If value had been set using a record, and load payload does not contain a match, rawValue is reverted to the valueField

+ EXTJS-16206 Setting forceSelection breaks timefield

+ EXTJS-16277 ComboBox value does not clear correctly on reset()

+ EXTJS-16279 ComboBox should not listen for store's filterchange event if store filtering is remote

+ EXTJS-16290 ComboBox does not honour autoLoadOnValue is displayField === valueField

+ EXTJS-16292 Combo setValue doesn't resolve record on load when displayField == valueField

+ EXTJS-16304 Combobox sensitive to store/value order in binding statement

+ EXTJS-16322 ComboBox: Nothing displayed when one-dimensional store is provided and no displayField is specified

+ EXTJS-16323 ComboBox: clearValue() does not clear the input field

+ EXTJS-16324 Combo box with inline store no longer works

+ EXTJS-16414 Delete button does not work in a numberfield when allowDecimals and allowExponential are both false

+ EXTJS-16468 ComboBox.checkValueOnChange should not clear value if the store is not loaded...

+ EXTJS-16491 Combobox with bind: { } for value renders with pickers expanded on IE11

+ EXTJS-16599 Cannot read property 'pointerType' of undefined when hiding bound list of picker

+ EXTJS-16645 ComboBox: Unable to reselect same value after clearing display text

+ EXTJS-16658 ComboBox defines redundant getStore() method 

+ EXTJS-16682 Removing a tagfield from its container throws an error

+ EXTJS-16711 ComboBox does not restore previous valid value if forceSelection is true

+ EXTJS-16729 Destroying combobox in select listener causes error

+ EXTJS-16760 Combobox validator not active after selecting entered value from dropdown

+ EXTJS-16766 Multiselect combo should not deselect prior selections on container click

+ EXTJS-16767 Fields can switch validity states without firing validitychange

+ EXTJS-16795 forceSelection does not function correctly on combo box after value is blanked out

+ EXTJS-16817 TagField generates corrupted markup for tags if their display value contains markup characters

+ EXTJS-16820 Tagfield does not realign picker when height changes

+ EXTJS-16825 allowOnlyWhitespace on TagField doesn't work

+ EXTJS-16988 Wrong combobox item focused after filtering

+ EXTJS-17015 field labelAlign: 'right' is incorrect in RTL mode

+ EXTJS-17049 Combo clearValue broken when forceSelection is true

+ EXTJS-17157  Tagfield doesn't apply values set by growMax or growMin

+ EXTJS-17180 Tagfield with allowblank false always returns errors

+ EXTJS-17208 Hiding and showing widget columns in grouped headers can throw exception

+ EXTJS-17216 Tagfield with binding to view model store throws 'Ext.data.Store created with no model' warning

+ EXTJS-17390 Document comobox's getSelection method

Grid (97)

+ EXTJS-11073 Grouping: selecting 'Show in groups' doesn't toggle grouped column when configured with hideGroupedHeader

+ EXTJS-14112 Empty text does not expand the container it is in.

+ EXTJS-14967 Listeners in RowEditing plugin do not reach grid's ViewController using "controller" scope

+ EXTJS-15105 Grid - date filter: does not disable filters on store correctly 

+ EXTJS-15259 Summary feature not updating on record.set()

+ EXTJS-15267 Grid groupingsummary does not display when grid filtered

+ EXTJS-15288 Adding a record to an associated store fails with a grouping grid

+ EXTJS-15490 Number filter accepts invalid values if pasted from the clipboard

+ EXTJS-15541 tdCls not working on widgetcolumn

+ EXTJS-15547 Grouping summary does not update correctly on reload

+ EXTJS-15563 Showing a tooltip throws on locked grid when delegating

+ EXTJS-15641 Summary not triggered when bound store updated

+ EXTJS-15685 checboxmodel + IE scrolling issue in grid

+ EXTJS-15755 Feature groups that were filtered are always expanded after filter(s) are removed

+ EXTJS-15762 Containers in a WidgetColumn do not layout properly when async loading the store

+ EXTJS-15880 Textarea used as an editor completes edit on enter

+ EXTJS-15892 Locked grid scrolls badly in Firefox with mouse wheel

+ EXTJS-15907 Spreadsheet selection model > Multi-cell selection with SHIFT breaks selection

+ EXTJS-15925 Grid Panel getRowClass no longer updates

+ EXTJS-15962 Grid with buffered rendering does not correctly scroll group into view

+ EXTJS-15964 Menus do not hide on mouse down outside the menu in some cases

+ EXTJS-15998 Grid throws an error when columns with child components are interacted with

+ EXTJS-15999 Cell editing on a dropdown list completes when a list selection is made using the ENTER key

+ EXTJS-16022 LiveSearchGridPanel - Uncaught TypeError: Cannot read property 'down' of null

+ EXTJS-16024 Grid with locked columns can misalign the headers and data at far end of horizontal range

+ EXTJS-16041 Widget column class not added to cell correctly after reconfigure when using locking

+ EXTJS-16109 Summary feature does not overflow cell, causing out of sync cell widths

+ EXTJS-16139 Keyboard navigation is wrong in Grid after focusing a row

+ EXTJS-16140 Locking grid with BufferedStore can generate an error if scrolled rapidly to the bottom

+ EXTJS-16141 Grouping summary loses aggregate record information when toggling groups on and off

+ EXTJS-16150 Row is selected when clicking on checkcolumn and templatecolumn is present

+ EXTJS-16162 CheckboxModel column insertion is affected by default xtype on columns

+ EXTJS-16166 Can't use arrow/home/end keys in grid editor text fields

+ EXTJS-16192 Ext.grid.filters.filter.Number doesn't clear Filters checkbox when filters removed programmatically

+ EXTJS-16195 Grouping grid does not properly remove group when last record is removed from store

+ EXTJS-16201 TriFilter gridfilters aren't respecting the active config

+ EXTJS-16203 Grid widgetcolumn using an Ext.Component (instead of Ext.Widget) derived type does not call onBoxReady method

+ EXTJS-16213 Grid cell dirty class not added when field of WidgetColumn updated

+ EXTJS-16218 If CellEditor's beforestartedit event receives a false response, editing will never start again.

+ EXTJS-16221 DownArrow in an input field in a grid header throws error.

+ EXTJS-16223 The widget config object given to a widgetcolumn should not be modified

+ EXTJS-16230 AbstractSummary has a trailing comma

+ EXTJS-16231 setProperty errors when property does not exist and create=true

+ EXTJS-16248  Column header is not displaying text ellipsis when overflowing

+ EXTJS-16249 Buffered renderer with buffered store doesn't properly reposition grid rows when filtered

+ EXTJS-16251 Grid Column renderer causes constant dirty state if unused fields returned in sync response

+ EXTJS-16252 Adding to bottom of store when buffer rendered block smaller than view size doesn't work.

+ EXTJS-16267 After first drag of scrollbar on grid with buffered store, grid results scroll back to first row

+ EXTJS-16294 Ext.detachedBodyEl is undefined on widgetcolumn when enableColumnMove is set to false

+ EXTJS-16312 Checkboxmodel selecting all from header checkbox fails in grid bound to viewmodel store

+ EXTJS-16314 Summary feature on buffered grid produces duplicate summary rows

+ EXTJS-16325 Summary feature doesn't correctly react to reconfigure

+ EXTJS-16336 Grid: Setting minHeight on viewConfig causes layout failure with a shrinkWrap grid

+ EXTJS-16364 Grid selection binding is not cleared when store reload occurs and no matching record is found

+ EXTJS-16372 SpreadsheetModel throws "Cannot read property 'selectedRecords' of null" errors when grid is using a buffered store

+ EXTJS-16397 Grid column autosize creates cell overflow in FF in nightly builds

+ EXTJS-16436 framework error is thrown when a gridpanel has "scrollable" config set to false

+ EXTJS-16461 Locking grid with buffered store and variable height rows scrolling error

+ EXTJS-16576 Error when reconfigure columns on lockable grid before render

+ EXTJS-16608 Shift click to multi-select doesn't work with cellediting

+ EXTJS-16629 Reordering column of grouped header in locking grid throws error (handleUpdate)

+ EXTJS-16644 When scrolling a grid horizontally using trackpad, headers are misaligned with columns

+ EXTJS-16652 Trifilter: the store filter collection is updated twice when the grid filter sets its value from an inactive state

+ EXTJS-16661 Cannot focus textfield widget column in FireFox

+ EXTJS-16666 Scroll area does not resize when grid dimensions are changed on mobile only

+ EXTJS-16686 Touch scrolling prevents scrolling in other components

+ EXTJS-16689 Reordering columns causes column sorting IE11

+ EXTJS-16719 Clicking on the > or 

+ EXTJS-16728 Cannot read property 'headerCt' of undefined on filtered, locked column

+ EXTJS-16731 progressbarwidgetcolumn should cast non-numeric values to 0

+ EXTJS-16735 Grid filters: reconfigure needs to null out reference(s) to the Filters top-level menu

+ EXTJS-16774 Column move event is not working as expected 

+ EXTJS-16787 RowEditor error tip misaligned

+ EXTJS-16843 Unspecified error in Element.js is thrown after editing cell in grid and scrolling on IE8

+ EXTJS-16850 Ext.view.View can leave layouts suspending when destroying during a begin/endUpdate cycle

+ EXTJS-16871 Grid should remain filtered after reconfigure

+ EXTJS-16969 Cannot copy multi-line cell content from grid (bad CSV encoding)

+ EXTJS-17034 Trifilter: Setting filter value prior to menu creation doesn't filter store

+ EXTJS-17053 cellWrap is making rows go out of sync

+ EXTJS-17105 Adding cellediting after grid init caused error on cellclick

+ EXTJS-17110 Error in Ext.grid.NavigationModel.onCellMouseDown when using widget columns

+ EXTJS-17114 Grouped grid header is broken after hiding columns with widgets

+ EXTJS-17218 BufferedRenderer evaluates a row 1px above the viewport as the first visible row when using variableRowHeight

+ EXTJS-17278 autoSizeColumn not working with column index

+ EXTJS-17305 RowEditor is in dirty state when fields are loaded, so will not move to new row.

+ EXTJS-17321 Column resizing goes to locked size when resizing the leftmost grouped header on the non-locked size

+ EXTJS-17324 Spreadsheet selection model does not fire change event on clearing selection

+ EXTJS-17343 CellEditing exits edit mode when tabbing onto non-editable cell.

+ EXTJS-17349 Row editor isn't positioned correctly when adding and editing last row in view

+ EXTJS-17382 When user clicks on focusable widget, NavigationModel steals focus and places it on the cell.

+ EXTJS-17463 Edited cell stays visible after scrolling

+ EXTJS-17470 Removal of record with Widget column does not remove widget, so it is destroyed.

+ EXTJS-17485 Grid refresh with buffered renderer causes an error on Windows 8 touch devices

+ EXTJS-17488 isFocusable() not a function error when rating widget focused

+ EXTJS-17592 Removal of grid row causes widgets to disappear from grid in IE8

+ EXTJS-8172 {renderedGroupValue} in groupHeaderTpl not working

+ EXTJS-9953 Stateful locking grid does not restore column state for columns with a stateId config

Layouts (15)

+ EXTJS-14754 Button menu isn't scrolling with its button

+ EXTJS-15282 Center layout fails in some cases when shrink wrapping

+ EXTJS-15868 Collapsed header panel does not render correctly in box layout

+ EXTJS-16056 Layout targetCls not applied correctly when framing

+ EXTJS-16101 Viewport fails to fill entire viewable area on Safari iOS 8.1

+ EXTJS-16227 Displaying a modal window triggers page-level horizontal and vertical scroll bars

+ EXTJS-16233 Grid scroll bars are reset when coming back from another tab

+ EXTJS-16350 VBox Layout Form field blur causes container to scroll to top

+ EXTJS-16394 Column layout items do not wrap properly if an item is too tall

+ EXTJS-16596 layout causes panel to reset scroll position when editing form

+ EXTJS-16758 Card layout fails if child item is a widget

+ EXTJS-16802 VIewport reports incorrect SizeModel before render

+ EXTJS-17115 bodyPadding is not applied on panel - center layout

+ EXTJS-17536 Form reset breaks layout in IE8

+ EXTJS-9843 Ext.cache leak in Table Layout

Locale (2)

+ EXTJS-15990 Missing italian localization of negativeText of Ext.locale.it.form.field.Number

+ EXTJS-16696 Wrong Italian format of Ext.grid.NumberColumn in ext-locale-it.js

Menu (12)

+ EXTJS-16178 Menu onFocusLeave event hides menu with floating: false

+ EXTJS-16183 Other floating menus stay visible when menu is shown

+ EXTJS-16219 Menu hide on focusLeave should only be for floating menus

+ EXTJS-16257 Menu causes a crash in IE10/11 when clicking on an empty area

+ EXTJS-16288 Floating menu not hidden when clicking outside the menu if it was never focused

+ EXTJS-16319 Disabled Menuitem still shows its menu

+ EXTJS-16643 Submenus don't disappear when moving mouse from item to item quickly

+ EXTJS-16646 MenuItems show problem

+ EXTJS-16784 Moving item from toolbar overflow back to visible position disables menu on buttons with menu

+ EXTJS-17039 Nested menus that are not direct children of menu items cause the parent to hide when shown

+ EXTJS-17094 Cannot read property 'owns' of undefined at Ext.menu.Manager.checkActiveMenus

+ EXTJS-17284 ColorMenu throws exception when selecting item

Misc (2)

+ EXTJS-16395 Breadcrumb menu throws "TypeError: Cannot read property '_breadcrumbNodeId' of undefined" when scrolled up or down via arrow buttons

+ EXTJS-16762 Ext.view.DragZone.onValidDrop callParent missing arguments

Panel (7)

+ EXTJS-16116 Panel hide when in placeholder float out mode fails.

+ EXTJS-16173 Component scroll position is reapplied from previously destroyed component (Gecko)

+ EXTJS-16284 addDocked method does not insert an array of items at correct index

+ EXTJS-16476 Ext.toolbar.Toolbar does not allow dock left but align buttons horizontally.

+ EXTJS-16864 addDocked fires dockedadd event out of order before onDockedAdd template method

+ EXTJS-17161 Dynamically setting panel title does not update layout

+ EXTJS-9505 collapseMode: 'mini' misbehaves in west/north regions (webkit)

Scroller (3)

+ EXTJS-16072 Scrollbar retains focus when clicking other components once when using IE10 and IE11 on Windows 7

+ EXTJS-16416 Click event firing only after second click after scrollbar click/drag for IE10/11 on Windows 7

+ EXTJS-16637 Component render exception in touchScroll: 1 mode.

Selection Model (5)

+ EXTJS-14726 SelectionModel doesn't allow deselect without Space bar

+ EXTJS-15525 When syncing created records, the returned record is entered into the SelectionModel's collection erroneously and cannot be removed.

+ EXTJS-16164 CheckboxModel selectionchange doesn't fire when deselect rows

+ EXTJS-16175 Drag selection of cells within a single row does not work on Chrome

+ EXTJS-16340 selectionchange event no longer fired when store is loaded with new data

Tabs (7)

+ EXTJS-14738 "Unable to get property 'dom' of undefined or null reference" changing the tabs position or rotation on IE8 and IE9 (RTL)

+ EXTJS-15402 Active tab should scroll into view when text, icon or glyph changes

+ EXTJS-15862 Tab switching requires dblclick in classic and gray themes in Firefox

+ EXTJS-16054 Active tab is not being set when calling setActiveTab during a pending load

+ EXTJS-16721 Vetoing beforetabchange suspends layouts incorrectly

+ EXTJS-17289 TabPanel doesn't move tab bar items for moveBefore/moveAfter methods

+ EXTJS-17408 Reorderable tabs are broken - drops on wrong positions / become invisible

Theme (2)

+ EXTJS-13704 Error Icon background should be transparent

+ EXTJS-16016 x-grid-cell-special gets two values for border-right-width

ToolTips (1)

+ EXTJS-16348 Tooltip shows when disabled if the first show causes the tip to be rendered

Toolbars (1)

+ EXTJS-16317 Toolbar buttons in panel disabled from viewmodel binding remain masked when panel is enabled

Tree (13)

+ EXTJS-12593 Scrollbar height miscalculated upon treepanel w/ bufferered renderer treestore load

+ EXTJS-14396 TreeStore 'context' argument is missing from remove event

+ EXTJS-14812 GridFilters' onMenuBeforeShow reference to the grid is not present on treegrids

+ EXTJS-16007 TreeGrid not working with latest nightly build when reordering columns

+ EXTJS-16148 Adding new record at the top of a tree with locked columns and rootVisible:false throws exception

+ EXTJS-16212 NodeInterface serialize method throws an error

+ EXTJS-16600 setRootNode for tree repeatedly will cause memory to grow

+ EXTJS-16744 Expand/Collapse icon of last tree node does not reflect correct state

+ EXTJS-17265 defaultListenerScope doesn't work in TreePanel-TreeColumn renderer

+ EXTJS-17401 KS>Trees> Tree Reordering - throws js exception when dnd is performed

+ EXTJS-17402 Ks>Trees> Check Tree - parent nodes can't be collapsed

+ EXTJS-17406 Trees with drag and drop functionality  - nodes are dropped into wrong folders, or not changing positions at all

+ EXTJS-17593 TreeStore not registering child nodes when hierarchy is produced using parentIdProperty

Window (5)

+ EXTJS-14076 Window position moves upwards after restore

+ EXTJS-15448 Window does not remember H/W if percent is used

+ EXTJS-16330 Window does not restore to defined size percentages

+ EXTJS-16936 Window in center region of boderlayout looks off center when there is a west region

+ EXTJS-17120 Constrained window is not positioned within parent window

Total: 342

##Known Issues

Accessibility (1)

+ EXTJS-14427 Date picker dropdown calendar causes navigation issues with JAWS

Button (1)

+ EXTJS-16118 Kitchen Sink - Form Fields: Browse local files button doesn't work on iOS8

Charts (1)

+ EXTJS-10739 RTL Charts do not correctly display bidirectional text

Core (1)

+ EXTJS-12058 Sandbox mode is not working

DataView (1)

+ EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad

Examples (1)

+ EXTJS-13879 Dashboard Portal drag-n-drop experience is not optimal especially on tablets

Layouts (1)

+ EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container

Tabs (1)

+ EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0

Total: 8

#Release Notes for Ext JS 6.0.0 Preview

## New Features

Accessibility (5)

+   EXTJS-13478 Windows should prevent tabbing out 
+   EXTJS-13481 Panel header tools should participate in tab order 
+   EXTJS-13485 Fieldset expand/collapse buttons should be in tab order 
+   EXTJS-13486 Accordion layout should support keyboard interaction 
+   EXTJS-14138 Panel tools should react to keyboard 

Charts (6)

+   EXTJS-16370 Charts should provide an 'itemedit' interaction to allow visual editing 
+   EXTJS-16797 3D Pie series should support bevels 
+   EXTJS-16867 3D pie charts should support legend 
+   EXTJS-17044 Series labels should support declarative renderers 
+   EXTJS-17045 Series items should support declarative renderers 
+   EXTJS-17046 Series tooltips should support declarative renderers 

Core (2)

+   EXTJS-16472 Ext.Component and Ext.Widget should support a "delegate" event option 
+   EXTJS-17028 Element should support CLIP visibility mode 

Draw (1)

+   EXTJS-16865 Should be able to specify a function name as a valid sprite updater value 

Forms (1)

+   EXTJS-14327 Slider field more compliant keyboard handling 

Grid (4)

+   EXTJS-13484 Grids should support Actionable mode 
+   EXTJS-16841 Tab key should navigate across rows and span the locked/normal boundary 
+   EXTJS-16915 Spreadsheet selection should be extensible by dragging bottom-right corner 
+   EXTJS-16971 Spreadsheets should support cell value replication by dragging bottom-right corner 

Panel (2)

+   EXTJS-16859 Panels should have default ARIA role of region in a viewport and appropriate heading 
+   EXTJS-17038 ButtonGroup should be accessible 

Total: 21

## Bugs Fixed

Accessibility (4)

+   EXTJS-10452 ARIA - Accordion is not supported 
+   EXTJS-10457 ARIA - NVDA is not supported 
+   EXTJS-14435 ARIA: Keyboard Navigation: Grid: Unable to open the message of the icon in the last two columns on the grid using the key "Enter" 
+   EXTJS-17275 Focus in modal window goes to address bar 

Animation (1)

+   EXTJS-17117 Modern toolkit - Animation - Flip - Animation is diffrent than in touch 2.4\. Should by the the same 

Bind (2)

+   EXTJS-15041 Number field with binding can cause the user typed value to be overwritten with a trimmed to decimalPrecision value 
+   EXTJS-16579 Setting a field in an associated record via a binding doesn't work correctly 

Charts (14)

+   EXTJS-15255 Memory leaks with charts 
+   EXTJS-15978 Column chart - With renderer - Icons with values are shifted down - firefox 
+   EXTJS-16851 Start angle for 3d pie series should be noon, not 3 o-clock 
+   EXTJS-16873 Filled radar chart doesn't render 
+   EXTJS-16993 Pie chart - Basic - Chart shows wrong values 
+   EXTJS-17057 Chart saving server: PDF options are not recognized 
+   EXTJS-17081 When a MarkerHolder is destroyed, the Markers it holds are not destroyed with it 
+   EXTJS-17082 Series has typo "itemhightlight" 
+   EXTJS-17097 Chart with both tooltip and itemhighlight interaction does not highlight properly 
+   EXTJS-17207 Center is not defined - polar charts - modern KS 
+   EXTJS-17209 Error in tooltip renderer - Pie basic chart 
+   EXTJS-17226 Series should not animate into view when the chart is created 
+   EXTJS-17227 Axes should not animate into view when the chart is created 
+   EXTJS-17274 Series cannot be dynamically updated. 

Core (3)

+   EXTJS-16573 KeyMap keeps propagating a stopped event 
+   EXTJS-16969 Multiline cell copy-paste from grid 
+   EXTJS-16984 Ext.Widget listeners declared in subclasses get cached on their superclass 

Data (11)

+   EXTJS-11490 TreeStore: added sub-children nodes are not phantoms 
+   EXTJS-16135 Store removedRecords doesn't remove erased records 
+   EXTJS-16356 Ext.data.field.Field convert should not be called for the defaultValue 
+   EXTJS-16451 NodeInterface.removeAll does not account for nodes that do not have treestore 
+   EXTJS-16493 Tree root node shouldn't be included in TreeStore's rejected records list 
+   EXTJS-16497 Polling Tree Store Memory Leak 
+   EXTJS-16695 Store update event has old value of reference fields. Reference not set correctly when key already exists 
+   EXTJS-16790 loadData does not clear entire store when filter exists 
+   EXTJS-17062 TreeStore#commitChanges does not clear removedNodes 
+   EXTJS-17138 Store reload hangs if the new dataset size does not encompass requested range. 
+   EXTJS-17230 Connection onStateChange has bad check for "isXDR" (needs to use the accessor) 

Draw (5)

+   EXTJS-16822 Complex paths are not properly rendered in all cases 
+   EXTJS-16854 Unable to process font families with spaces in them 
+   EXTJS-16975 Animation modifier's 'animationend' event is not always passed the modifier itself 
+   EXTJS-16978 Several easings are missing from draw package animation functions 
+   EXTJS-16981 Sprites are not destroyed when the Surface is destroyed 

Events (1)

+   EXTJS-17147 Double tap should not zoom page in modern toolkit - iOS 

Examples (10)

+   EXTJS-12984 Phone field should not accept string in Kitchen Sink\ Field container example 
+   EXTJS-14321 Unable to access item selector using tab key or arrows key - Aria examples 
+   EXTJS-14345 ARIA: Screen Reader: Description expand(FieldSet): Jaws not announced(Not reading) that is in expand description. 
+   EXTJS-16726 Ext.ux.event.Recorder click event sets button to true 
+   EXTJS-16956 Ext.ux.event.Player does get the speed when events are being played 
+   EXTJS-17001 Live search grid example doesn't focus results 
+   EXTJS-17016 Uncaught error in Ticket app example 
+   EXTJS-17017 Wrong path resolving in include-ext.js for classic examples 
+   EXTJS-17023 Grids - From Markup Grid Example - Button should create a grid from tab 
+   EXTJS-17058 Theme Viewer example is not loaded due to typo in index.html 

Forms (9)

+   EXTJS-10300 ARIA - [Screen Readers] Radio Button groupings are not identified as radio groupings 
+   EXTJS-16468 ComboBox.checkValueOnChange should not clear value if the store is not loaded... 
+   EXTJS-16711 ComboBox does not restore previous valid value if forceSelection is true 
+   EXTJS-16760 Combobox validator not active after selecting entered value from dropdown 
+   EXTJS-16766 Multiselect combo should not deselect prior selections on container click 
+   EXTJS-16988 Wrong combobox item focused after filtering 
+   EXTJS-17015 RTLfield labelAlign: 'right' is incorrect 
+   EXTJS-17150 Modern picker should not stop between 2 values 
+   EXTJS-17208 Hiding and showing widget columns in grouped headers can throw exception 

Grid (20)

+   EXTJS-10282 ARIA: Grid: Unable to set a row or a cell into Edit mode on pressing "F2" hot key in key board 
+   EXTJS-10764 ARIA - Links within cell are unusable with keyboard controls 
+   EXTJS-10765 ARIA - Components within grids are not focused 
+   EXTJS-15547 Grouping summary does not update correctly on reload 
+   EXTJS-15907 Spreadsheet selection model > Multi-cell selection with SHIFT breaks selection 
+   EXTJS-15962 Grid with buffered rendering does not correctly scroll group into view 
+   EXTJS-15964 Menus do not hide on mouse down outside the menu in some cases 
+   EXTJS-15988 Spreadsheet selection model does not change cursor while hovering on rows, columns or select all 
+   EXTJS-15999 Cell editing on a dropdown list completes when a list selection is made using the ENTER key 
+   EXTJS-16314 Summary feature on buffered grid produces duplicate summary rows 
+   EXTJS-16661 Cannot focus textfield widget column in FireFox 
+   EXTJS-16787 RowEditor error tip misaligned 
+   EXTJS-16850 Ext.view.View can leave layouts suspending when destroying during a begin/endUpdate cycle 
+   EXTJS-17034 Trifilter: Setting filter value prior to menu creation doesn't filter store 
+   EXTJS-17059 Grid - Widget grid - Data in grid does't load. 
+   EXTJS-17114 Grouped grid header is broken after hiding columns with widgets 
+   EXTJS-17130 Spreadsheet SelectionModel throws an error when used with a BufferedStore 
+   EXTJS-17218 BufferedRenderer evaluates a row 1px above the viewport as the first visible row when using variableRowHeight 
+   EXTJS-17278 autoSizeColumn not working with column index 
+   EXTJS-8172 {renderedGroupValue} in groupHeaderTpl not working 

Layouts (1)

+   EXTJS-17115 bodyPadding is not applied on panel - center layout 

Locale (1)

+   EXTJS-15990 Missing italian localization of negativeText of Ext.locale.it.form.field.Number 

Menu (2)

+   EXTJS-16784 Moving item from toolbar overflow back to visible position disables menu on buttons with menu 
+   EXTJS-17094 Cannot read property 'owns' of undefined at Ext.menu.Manager.checkActiveMenus 

Misc (1)

+   EXTJS-16762 Ext.view.DragZone.onValidDrop callParent missing arguments 

Tabs (2)

+   EXTJS-15402 Active tab should scroll into view when text, icon or glyph changes 
+   EXTJS-17222 Tabs in TabBar should react to Space key 

Tree (2)

+   EXTJS-16744 Expand/Collapse icon of last tree node does not reflect correct state 
+   EXTJS-17047 Tree column custom renderer does not honour scope correctly 

Window (4)

+   EXTJS-15448 Window does not remember H/W if percent is used 
+   EXTJS-16330 Window does not restore to defined size percentages 
+   EXTJS-17004 Window shown using animation does not honor focusOnToFront 
+   EXTJS-17120 Constrained window is not positioned within parent window 

Total: 93

## Known Issues

Accessibility (1)

+   EXTJS-14427 Date picker dropdown calendar causes navigation issues with JAWS 

Button (1)

+   EXTJS-16118 Kitchen Sink - Form Fields: Browse local files button doesn't work on iOS8 

Charts (1)

+   EXTJS-10739 RTL Charts do not correctly display bidirectional text 

Core (1)

+   EXTJS-12058 Sandbox mode is not working 

DataView (1)

+   EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad 

Examples (1)

+   EXTJS-13879 Dashboard Portal drag-n-drop experience is not optimal especially on tablets 

Grid (2)

+   EXTJS-10494 ARIA - Grid Grouping Feature is not supported 
+   EXTJS-10495 ARIA - Locking Grid is not supported. 

Layouts (1)

+   EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container 

Misc (18)

+   EXTJS-10397 ARIA - Datepicker is not supported 
+   EXTJS-10456 ARIA - VoiceOver for Mac is not supported 
+   EXTJS-10467 ARIA - Menu overflow scrollers are not navigable using the keyboard 
+   EXTJS-10472 ARIA - Charts are not supported 
+   EXTJS-10477 ARIA - HtmlEditor is not supported 
+   EXTJS-10479 ARIA - LoadMask is not supported 
+   EXTJS-10480 Color Picker is not accessible 
+   EXTJS-10490 ARIA - Progress Bar is not supported 
+   EXTJS-10491 ARIA - Property Grid is not supported 
+   EXTJS-10492 ARIA - DragDrop is not supported 
+   EXTJS-10493 ARIA - Paging Toolbar is not supported 
+   EXTJS-10496 ARIA - Grouped Grid Headers are not supported 
+   EXTJS-10497 ARIA - Grid Row Expander is not supported 
+   EXTJS-10498 ARIA - Grid RowBody Feature is not supported 
+   EXTJS-10499 ARIA - Grid CheckboxSelectionModel is not supported 
+   EXTJS-10502 ARIA - Grid Summary is not supported 
+   EXTJS-10503 ARIA - Grid headers cannot be resized using the keyboard 
+   EXTJS-10504 ARIA - Grid Headers cannot be reordered using the keyboard 

Tabs (1)

+   EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0 

Theme (1)

+   EXTJS-9806 ext-theme-aria does not support Windows high-contrast mode 

ToolTips (1)

+   EXTJS-10475 ARIA - ToolTip is not supported 

Tree (1)

+   EXTJS-10451 ARIA - The Tree component is not supported. 

Total: 31

#Release Notes for Ext JS 5.1.0

Release Date: December 10, 2014

Version Number: 5.1.0.107

##New Features

Data (1)

+ EXTJS-15969 XmlWriter should be able to rebuild nested XML structure by reversing mapping selectors.

Direct (1)

+ EXTJS-15222 Direct Manager should support loading Providers

Total: 2

##Bugs Fixed

Bind (2)

+ EXTJS-15579 Field with a value binding can get out of sync with the view model in certain scenarios
+ EXTJS-16067 Selection model does not properly handle removal of records from a chained store

Button (1)

+ EXTJS-15949 Button Menu: First menu item does not expand sub menu unless first deactivated

Charts (3)

+ EXTJS-15310 Columns are not placed correctly over time axis
+ EXTJS-15882 Sencha Charts do not set defaultBindProperty (should be "store")
+ EXTJS-15930 Sencha Charts - series label not rendered when value is 0

Core (8)

+ EXTJS-12844 Loader does not process loadOrder uses[] from manifest w/o uses directive
+ EXTJS-15781 Example builds should not have "callParent has no target" warnings
+ EXTJS-15830 Combobox requires two taps to select on touch devices.
+ EXTJS-15941 Checkboxes cannot be checked or unchecked by tapping them on iPad and Android
+ EXTJS-15970 Ext.Number.sign inconsistent w/ Math.sign
+ EXTJS-15972 Ext.DomHelper.createDom removes content of previous created nodes in IE9
+ EXTJS-15973 Custom tags added in beforeLoad do not affect platformConfig statements
+ EXTJS-16075 Touch Scroller throws an error when configured with an element that has a text node as its first child

Data (8)

+ EXTJS-12202 Session getChanges still returns a deleted record after being committed to the a server
+ EXTJS-14145 Records deleted in previous saveBatch appear again in subsequent saveBatch
+ EXTJS-14338 Extending a base model generates redundant id fields if idProperty is modified by derived class
+ EXTJS-15454 Unwanted GET call when binding associated store to combobox
+ EXTJS-15753  versionProperty not sent in server request unless writeAllFields: true
+ EXTJS-15954 Generated idProperty from superclass remains when overridden by an idProperty declared as a field in a subclass
+ EXTJS-16083 Store.load() does not allow start option of 0
+ EXTJS-6712 TreeStore handle child phantom records wrong

DataView (1)

+ EXTJS-14878 Ext.ux.DataView.Animated throws exception if changed too quickly

Direct (1)

+ EXTJS-12363 Direct method can't be resolved when inside a Provider namespace

Draw (1)

+ EXTJS-16038 Mouse click on draw container (such as a chart) generates JS error with latest nightly build in IE

Events (2)

+ EXTJS-13982 EventObject.button is undefined in IE8/9
+ EXTJS-15953 Ext.Element listeners added during propagation will not fire if the target is not already in the element cache

Examples (6)

+ EXTJS-13874 Grid binding example has broken link
+ EXTJS-13901 Unable to select any of the calendar's predefined events on IE - ExtJs Calendar
+ EXTJS-15847 Ticket app example: Error occurs when tab is closed
+ EXTJS-15951 No focus treatment for the grid cells in the news grid in the Executive Dashboard
+ EXTJS-16032 KS>Image Viewer>Drag and drop of multiple items fails
+ EXTJS-16120 Form/Checkout example throws error on iPad

Forms (13)

+ EXTJS-14235 If a record is removed from a store, the combobox does not clear it's value
+ EXTJS-14507 Combo with forceSelection doesn't always force selection.
+ EXTJS-14747 File input field doesn't work on Android/iOS7
+ EXTJS-15045 Can't select first record from remote-filter combo after narrowing selection.
+ EXTJS-15069 Updated selected record not reflected in the combobox
+ EXTJS-15371 Picker closes if opened from editor in IE
+ EXTJS-15577 Chained Combobox does not remove invalid value
+ EXTJS-15764 Combo does not show display value when a record value is passed and the store is loading
+ EXTJS-15767 Combobox doesn't always collapse properly after selecting in IE10 / IE11
+ EXTJS-15943 iPad. Combo dropdowns have to be tapped twice to select.
+ EXTJS-15968 Date Picker disappear after click on Month Picker.
+ EXTJS-16047 ComboBox can't setValue correctly when store is populated via adding records as opposed to loading
+ EXTJS-16079 JavaScript error on tabbing in MultiSelect field

Grid (25)

+ EXTJS-13552 Columns are unable to move if the position of the browser's scroll bar is set to any other position different than the top - Data Binding (RTL)
+ EXTJS-13726 Ext.grid.feature.GroupStore store listener leaks
+ EXTJS-13741 GridFilters aren't replacing existing store filters when calling addFilter API
+ EXTJS-14745 Grid filter active state can get out of sync with sub-menu
+ EXTJS-15115 grid.getView().disable() incorrectly masks tbar and other dockedItems
+ EXTJS-15155 Column editor configured as textarea has top of editor hidden under column header
+ EXTJS-15266 Widget column causes error when a record.set call alters the group
+ EXTJS-15294 Datepicker not working correctly when month selected in IE
+ EXTJS-15569 Date filter and Number filter do not add menu separator 
+ EXTJS-15610 PropertyGrid with Combobox(forceSelection:true) throws null error when renderer is called
+ EXTJS-15675 Local grid filtering does not compare dates correctly
+ EXTJS-15740 Locked grid rows will have unequal heights when scrolled if a column contains a widget above a certain height
+ EXTJS-15761 Child items of columns aren't being displayed
+ EXTJS-15770 Hiding a grid column during construction causes an exception
+ EXTJS-15865 Variable height rows in buffered rendered, locked grids do not always synchronize their heights
+ EXTJS-15902 Ext.grid.filters.filter.List doesn't accept store id or store config
+ EXTJS-15937 Action columns with items on class body cause errors at destroy time
+ EXTJS-15946 Typing SPACE in a grid column which does not stop the event scrolls the grid.
+ EXTJS-15963 RowEditor does not reorder fields on column reorder
+ EXTJS-15965 List filter includes call to Array.indexOf which is not supported in IE8
+ EXTJS-16048 Cannot enter a space in cell edit grid
+ EXTJS-16071 Date gridfilter throws in onFilterRemove listener when bound store removes filters
+ EXTJS-16082 Adding a TriFilter (Date, Number) using the addFilter API fails
+ EXTJS-16158 Mouse drag selection fails on SpreadSheet with Locking example
+ EXTJS-8965 CheckboxModel's checkOnly:true is not respected by grid editing plugins

MVC (1)

+ EXTJS-15463 Default scope of functions literals in component listeners should be the component not the ViewController

Menu (6)

+ EXTJS-13717 All references to a menu should be removed from its owner when it is destroyed
+ EXTJS-13972 Sub-menus cannot be opened on touch devices
+ EXTJS-15127 Clicking menu items can cause window.location.hash to set to '#' in IE
+ EXTJS-15950 Selection in submenu doesn't close primary menu
+ EXTJS-15958 Menu default highlighting behaviour is incorrect for mouse users
+ EXTJS-16103 Ext.menu.Menu not auto hiding when clicking non-focusable components

Misc (2)

+ EXTJS-14981 Stub ext*.js files in root folder cause confusion (users should use build/ext*.js instead)
+ EXTJS-15784 Ext.application method is missing from ext-debug.js

Panel (1)

+ EXTJS-15974 East collapsible panel isnt visible

Selection Model (5)

+ EXTJS-14092 CheckboxSelectionModel should not selectByPosition if checkOnly and the requested position is not the check column.
+ EXTJS-14487 User should be able to use the keyboard to check all rows of a grid with checkbox selection model
+ EXTJS-15625 Checkbox selection models do not allow select / deselect when allowDeselect:true
+ EXTJS-15921 Checkbox selModel column header cannot be toggled using keyboard.
+ EXTJS-16015 Selection model loses selection on sort

Tabs (1)

+ EXTJS-15791 setActiveTab and activate event not fired when tabs are added via the loader config

Tree (6)

+ EXTJS-14780 Tree expand/collapse cause too many extra layouts
+ EXTJS-14881 When tree store is filtered refresh event on view is fired twice
+ EXTJS-15241 Treepanel broken after editing in IE8
+ EXTJS-15834 DragAndDrop in Tree causes tree to scroll to top
+ EXTJS-15944 Locked tree panel missing header
+ EXTJS-16149 TreeSelectionModel fails when used in a locking TreeGrid

Window (2)

+ EXTJS-14811 loadmask on component inside window not visible
+ EXTJS-16014 MessageBox on top of a modal Window breaks key navigation when MessageBox closes

Total: 95

##Known Issues

Accessibility (1)

+ EXTJS-14427 Date picker dropdown calendar causes navigation issues with JAWS

Button (1)

+ EXTJS-16118 Kitchen Sink - Form Fields: Browse local files button doesn't work on iOS8

Charts (1)

+ EXTJS-10739 RTL Charts do not correctly display bidirectional text

Core (1)

+ EXTJS-12058 Sandbox mode is not working

DataView (1)

+ EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad

Examples (1)

+ EXTJS-13879 Dashboard Portal drag-n-drop experience is not optimal especially on tablets

Layouts (1)

+ EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container

Tabs (1)

+ EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0

Total: 8

#Release Notes for Ext JS 5.1.0 Beta

Release Date: November 25, 2014

Version Number: 5.1.0.47

##Notable changes

For Ext.data.Model, it is no longer necessary to specify null as the idProperty for an abstract base model.
Any generated id field in the superclass will be replaced by a generated id field in the subclass.

    Ext.define('Super', {
        extend: 'Ext.data.Model',
        fields: ['name']
    });

    Ext.define('Sub', {
        extend: 'Super',
        idProperty: 'customId'
    });

    var fields = Super.getFields();
    // "name", "id", 2
    console.log(fields[0].name, fields[1].name, fields.length);

    fields = Sub.getFields();
    // "name", "customId", 2
    console.log(fields[0].name, fields[1].name, fields.length);

    // if you explicitly declare the id field in the fields definition, then it will be untouched
    Ext.define('Super', {
        extend: 'Ext.data.Model',
        fields: ['id', 'name']
    });

    Ext.define('Sub', {
        extend: 'Super',
        idProperty: 'customId'
    });

    var fields = Super.getFields();
    // "id", "name", 2, "id"
    console.log(fields[0].name, fields[1].name, fields.length, Super.idProperty);

    fields = Sub.getFields();
    "id", "name", "customId", 3, "customId"
    console.log(fields[0].name, fields[1].name, fields[2].name, fields.length, Sub.idProperty);


The Ext.container.Container "move" event to indicate that a child component has had the 
index moved has been renamed to 'childmove'. The reasoning for this change is that the 
existing event collides with the Ext.Component "move" event.
                
##New Features

Bind (1)

+ EXTJS-14721 Ext.mixin.Bindable should expose twoWayBindable as a public config

Charts (6)

+ EXTJS14616 Create a dark theme for Charts
+ EXTJS14846 Charts should support events for series items in sencha-charts (via chartitemevents plugin)
+ EXTJS15431 Changes in the visible range of an axis should fire a 'visiblerangechange' event (sencha-charts)
+ EXTJS15535 Make "bar3d" a proper series type for charts
+ EXTJS15701 Axis should support a depth for 3D Cartesian charts
+ EXTJS15901 Box sprite should have 'saturationFactor' and 'brightnessFactor' attributes.

Core (2)

+ EXTJS15464 All containers should support a defaultFocus config not just Ext.window.Window
+ EXTJS15635 Component.setScrollX / Y should support animation argument

Data (1)

+ EXTJS14794 ChainedStore should support insert

Direct (1)

+ EXTJS9987 Direct proxy actions other than read (create, update, delete) should support metadata

Draw (6)

+ EXTJS14509 Promote the Draw engine config to be public
+ EXTJS14531 Paths should provide an API to perform hit testing against points or other paths
+ EXTJS14857 Text sprite's 'text' attribute should support animation.
+ EXTJS15421 Charts should provide a hitTest method that respects overlapping sprites
+ EXTJS15422 Draw component should support sprite events in sencha-charts
+ EXTJS15708 Ext.draw.Color should support HSV and HSB color space

Forms (2)

+ EXTJS13182 Advanced color picker component
+ EXTJS15898 Provide a rating widget for setting numeric values limited to a small range

Grid (6)

+ EXTJS13950 Widget column: getWidgetRecord and onWidgetAttach methods should be public
+ EXTJS14797 Grids (and trees) should have a method that scrolls a record into view (ensureVisible)
+ EXTJS14956 Grids and trees should relay before/itemkeypress and before/itemkeyup from Ext.view.View
+ EXTJS15083 Create grid selection model that mimics a spreadsheet
+ EXTJS5144 Cell selection model does not support multi-select (see "spreadsheet" selection model)
+ EXTJS8183 Grid CellEditing should provide enable/disable methods

Misc (2)

+ EXTJS15260 Clipboard plugin to add copy/cut/paste support to grids with spreadsheet selection model
+ EXTJS15261 Provide utility class to encode and decode CSV and TSV (comma/tab separated value)

Total: 27

##Bugs Fixed

Accessibility (2)

+ EXTJS14714 Explicit call to .focus() loses priority against present floatable components
+ EXTJS15499 Using ext-aria package generates "ariaUpdate undefined" error

Animation (1)

+ EXTJS5487 accordion animation doesn't always complete if you click frequently

Bind (15)

+ EXTJS14313 Both Store's remoteSort and remoteFilter in ViewModel makes store load twice
+ EXTJS14528 Segmented buttons don't have defaultBindProperty
+ EXTJS14552 Setting the value on an association binding does not update foreign keys or associated record reference
+ EXTJS14704 Two-way bindings can override ViewModel data with component's default config value
+ EXTJS14766 Association stores for phantom records load when used in bindings
+ EXTJS14806 Setting a two-way formula of a parent ViewModel via a child ViewModel does not call the setter
+ EXTJS15016 Combo with bound value always clears typed value
+ EXTJS15022 Binding a store to grid disables the loadmask
+ EXTJS15150 Destroying a viewport with a viewmodel leaves the viewmodel in the hierarchy
+ EXTJS15258 Filter unable to set value to empty string
+ EXTJS15488 Radiogroup is only bound to inline viewModel
+ EXTJS15549 Clearing model in a view model does not trigger field bindings to fire
+ EXTJS15595 ViewModel formulas with spaces inside the parens of get() calls don't bind correctly
+ EXTJS15720 Binding to a chained store causes error when the store is modified in latest nightly
+ EXTJS15745 Menu and tab break with binding not found in nightly build

Button (4)

+ EXTJS14106 button setHref/setParams doesn't check if rendered before touching DOM
+ EXTJS14451 changeHandler (Ext.button.Cycle) can't reference ViewController function
+ EXTJS14626 CycleButton fires multiple change events for a single change
+ EXTJS15395 Buttons cannot be made floating

Charts (41)

+ EXTJS11852 Legacy scatter chart does not properly handle filtered store
+ EXTJS13098 NaN values passed to lineTo/moveTo methods result in line not rendering
+ EXTJS13336 package: sencha-charts! Sprites aren't rendered
+ EXTJS13996 Sprite attributes can get stuck in an intermediate highlight state if hovered during chart initial animation
+ EXTJS14395 Chart legend gets one extra 1x1 div for each store refresh
+ EXTJS14529 Crosszoom interaction bounds are wrong with chart.innerPadding > 0.
+ EXTJS14618 Chart themes should not update configs if instances configure them as well.
+ EXTJS14651 chart.background config is not updated properly.
+ EXTJS14652 Chart background is not animated when switching themes.
+ EXTJS14695 The scale param can only be an integer with chart.download()
+ EXTJS14885 ext-chart package not ext-theme-base should contain CSS necessary for VML
+ EXTJS15010 Floating axes are not positioned properly when chart.innerPadding is used
+ EXTJS15011 Line series 'fill' config fills the series to the bottom of the chart instead of to the axis
+ EXTJS15012 Series renderer cannot be dynamically changed
+ EXTJS15018 Line series configs `fill`, `smooth` and `step` cannot be changed dynamically.
+ EXTJS15027 Line series don't render if there are any very large coordinates present
+ EXTJS15048 SVG engine context does not support setLineDash and getLineDash methods.
+ EXTJS15049 VML engine does not support setLineDash/getLineDash methods.
+ EXTJS15064 PieSlice sprites are not filled properly with gradients.
+ EXTJS15089 Switching to a theme that styles the grid marker sprite makes the grid disappear
+ EXTJS15090 TypeError: 'undefined' is not a function (evaluating 'l.setLineDash(s)') and all Ks- charts examples crash 
+ EXTJS15106 Chart background should not animate its position
+ EXTJS15118 Sprite highlights can create instance-level attributes and no longer respond to theme changes
+ EXTJS15144 Kitchen Sink Charts - 3D Columns - Switch Theme button crash application
+ EXTJS15216 Legacy Charts: Uncaught ReferenceError: lastFocused is not defined. When try to save the chart.
+ EXTJS15236 KS: Charts - LineChart w/ Image Markers : Uncaught TypeError: Array.prototype.indexOf causes app crash
+ EXTJS15249 Series 'title' updater tries to get chart series when they are being applied.
+ EXTJS15251 Series 'renderer' updater shouldn't be called during chart initialization.
+ EXTJS15276 Chart fails to render if series title is specified before yAxis
+ EXTJS15300 Axis values incorrectly computed for yField of line chart using an array
+ EXTJS15423 Series 'marker: true' config doesn't work (an exception is thrown).
+ EXTJS15441 Bar sprite hit detection is wrong (highlighted when it shouldn't).
+ EXTJS15456 Radar series animation is misising.
+ EXTJS15458 Radar series tooltips and highlighting doesn't work
+ EXTJS15479 Axis label alignment other than center renders incorrectly
+ EXTJS15480 Legacy charts exceptions when more than one Gauge series is present
+ EXTJS15493 Legacy chart destroys surface twice
+ EXTJS15661 Axis constructor has harmless but redundant call to initConfig
+ EXTJS15783 ItemEvents plugin should fire itemclick with chart or series as first argument based on target of the listener
+ EXTJS15794 Ext.chart.axis.Numeric - linkedTo can't be 0 index
+ EXTJS9615 Pie chart legend item does not change to bold on mouse over in IE8

Cmd (2)

+ EXTJS15801 Viewport plug-in not included in production build in latest nightly
+ EXTJS15829 Executive Dashboard, Portal Demo, Responsive desing demo Examples Fails to load

Core (35)

+ EXTJS10166 disable/enable touch scroller when component setAutoScroll/setOverflowXY called
+ EXTJS12418 Dynamic loader fails to load CSS in Safari 5
+ EXTJS12947 Ext.Layer and Ext.LoadMask no longer support shim
+ EXTJS13193 Draggable components are not resizable
+ EXTJS13925 Undefined width and height in boxready event
+ EXTJS13931 Changing the group key can cause group items to be out of order in some scenarios
+ EXTJS14505 Ext.util.Format.number returns wrong value with a negative zero and trimming zeros
+ EXTJS14614 Ext.callback and Ext.env.Ready.invokeAll should call Ext.elevateFunction
+ EXTJS14675 Modal mask disables tabbing for the modal window
+ EXTJS14707 mixin.Observable won't resolve class level listeners to methods on the class
+ EXTJS14779 Delegate element selectors can fire out of DOM order
+ EXTJS14856 setMin/setMax width/height fails on components with liquidLayout before render
+ EXTJS14887 Capture of previous focus on Floating show causes problems.
+ EXTJS14893 5.0.1 can delay opening modal window or Ext.Msg.alert for 1-2 seconds
+ EXTJS14908 relayEvents does not stop firing when a handler returns false with single: true
+ EXTJS14946 Collection does not update map correctly when adding multiple records when the collection is sorted
+ EXTJS15060 Textbox keeps focus and is editable after loading mask set on parent
+ EXTJS15063 Listeners not merged correctly when extending from Ext.util.Observable
+ EXTJS15081 Class system should set name property on functions, instead of displayName
+ EXTJS15119 Typo in Ext.util.Filter.isInvalid
+ EXTJS15138 Tab key not working when the (deprecated) Ext.FocusManager is enabled.
+ EXTJS15176 Ext.Img overrides style config when using a glyph
+ EXTJS15290 Ext.Img.setGlyph does not work when called multiple times
+ EXTJS15349 Cannot remove a Sorter object from a Sorter collection
+ EXTJS15373 TouchScroller does not include absolutely positioned items in scroll size
+ EXTJS15389 Fix LoadMask maskCls property
+ EXTJS15390 isFocusable() should return true for documentElement in IE
+ EXTJS15515 DD's "ddel" element gets collected as garbage unexpectedly.
+ EXTJS15538 Ext.util.Collection does not update indexes correctly in some cases when adding multiple items while sorted
+ EXTJS15548 Focus cls is removed from wrong element
+ EXTJS15728 Component move event conflicts with Container move event (rename Container's to "childmove")
+ EXTJS15743 IE8 view.getNodes returns empty array
+ EXTJS15763 ZIndexManager activates topmost in stack regardless of visibility.
+ EXTJS15802 Container fires remove event when moving an item to the same container
+ EXTJS15836 Collection.clear does not clear down extraKeys

Dashboard (1)

+ EXTJS15467 Unable to show() a dashboard portlet after closing it

Data (36)

+ EXTJS10899 LRU should compare keys, not values
+ EXTJS13894 MyApp.model.MyModel.load(null, options) throws 'Cannot load phantom record' error
+ EXTJS14010 Model erase should not conflict with store sync
+ EXTJS14131 Generated UUIDs replaced with sequential id when saved via LocalStorageProxy
+ EXTJS14150 Unable to load a single record from the model via a WebStorageProxy
+ EXTJS14399 Store.find does not match the start of strings as a default
+ EXTJS14406 Applying a noop filter to TreeStore with rootVisible : true changes the node count
+ EXTJS14432 Tree selection doen't work after 'id' was changed on the server
+ EXTJS14485 Reader should not generate a new model from metaData unless it contains fields
+ EXTJS14515 Ext.Direct store method with quotes does not work with data binding filter
+ EXTJS14560 Calculated fields in child model do not work if parent model instance was created
+ EXTJS14595 Upon return from a sync, Operations should not always fire a refresh event.
+ EXTJS14611 Global variable introduced by validate method of Ext.data.field.Field
+ EXTJS14654 Rest proxy does not urlencode the id
+ EXTJS14696 Cellediting does not work on additional columns in treegrid when the treepanel has a reference config
+ EXTJS14732 Ext.data.writer.Json.transform incorrectly sets JSON data for POST requests when encode is true
+ EXTJS14740 isLoaded method in TreeStore always returns false
+ EXTJS14769 hasMany association does not respect storeConfig when specifying a name
+ EXTJS14890 Chained store filters do not notify correctly when the source is a chained store
+ EXTJS14903 TreeStore with autoLoad triggers a duplicate load
+ EXTJS14905 LoadMask missing on grids with chained store
+ EXTJS14969 TreeStore folderSort does not work correctly
+ EXTJS14988 JSON writer does not use field's name as fallback on destroy operations if nameProperty has no value
+ EXTJS15059 Store remove events do not fire after calling removeAll
+ EXTJS15076 sorterFn not respected when using grouping
+ EXTJS15170 Self referential associations pollute reader when loading nested data
+ EXTJS15369 Insert does not sync on filtered store unless inserted record matches the filter
+ EXTJS15394 Unable to bind store on Ext.view.View in latest nightly
+ EXTJS15428 FilterCollection find method cannot find filter instances (similarly for sorter/collection)
+ EXTJS15444 Store fires unnecessary events when modifying the sortBy field.
+ EXTJS15487 Warnings shown when overriding a Model field
+ EXTJS15519 manyToMany association overwrites custom associationKey for nested loading
+ EXTJS15542 ManyToMany does not update inverse store when doing a removal
+ EXTJS15580 Proxy not destroyed properly when store is destroyed
+ EXTJS15616 remoteSort: true doesn't ignore sortOnLoad like it should
+ EXTJS15741 Session.adopt fails when loading nested data for a ManyToMany relationship

DataView (4)

+ EXTJS13607 Sorting a view using the Ext.ux.DataView.Animated plugin causes item DOM order to not match Store order
+ EXTJS14631 SelModel pruneRemoved:false incorrectly removes records on store refresh
+ EXTJS14808 Ext.view.View focuschange event is not fired
+ EXTJS15026 DataView doesn't map records to nodes correctly after store reload

Direct (2)

+ EXTJS14580 rootProperty on DirectStore is ignored
+ EXTJS14843 API functions not resolved when both api and directFn configs are used

Draw (3)

+ EXTJS14746 Sprite rotation is not handled properly due to Ext.draw.Matrix.split method
+ EXTJS15385 Surfaces added to draw container via getSurface method don't render until draw container is resized
+ EXTJS15631 Ext.draw.sprite.Ellipse has the wrong type property

Events (9)

+ EXTJS12977 Calling Element's addListener (or "on") method throws an error if called before onReady
+ EXTJS13266 LoadMask class should check its hierarchy state before hiding and showing
+ EXTJS13487 Ext.mixin.Observable can easily cause memory leaks because it does not track its own direct listeners
+ EXTJS14701 Listeners declared on class have an incorrect default scope when passing a function reference
+ EXTJS14945 Click event can stop touch events from firing on multi-input devices
+ EXTJS15103 Ext.util.Observable does not respect the "args" event option
+ EXTJS15735 Ext.event.publisher.Dom#dispatch appends the event target to the args list every time it is called.
+ EXTJS15759 Managed listeners are not always removed when the managing Ext.util.Observable instance is destroyed
+ EXTJS15825 Controller events are case sensitive

Examples (9)

+ EXTJS12914 Drawing Example. Browser Logos are cut in IE8
+ EXTJS14136 Restaurants store - storeId typos
+ EXTJS14562 Ks: Form fields: Tag field: TypeError: 'undefined' is not a function (evaluating 'h.setLastFocused(null)') when selecting a state, change to another code view, go back to the grid and try to write something
+ EXTJS14564 Keyboard Navigation: KitchenSink: Form fields: Multi-selector grid: TypeError: 'null' is not an object (evaluating 'm.isNonData') when opening the example and press "tab" key
+ EXTJS14576 Buffered store sometimes requests invalid range when using the scrollbar
+ EXTJS14715 Multi-lang example: Theme isn't being persisted across page loads
+ EXTJS15197 Failed to load resource: the server responded with a status of 404 (Not Found) when opening any example on Ext js 5 except Ks and some combination examples 
+ EXTJS15356 "KitchenSink > Data Binding > Associations" example is missing code preview for Customer and Order models
+ EXTJS15879 Some Combination Examples is not loaded on firefox

Forms (46)

+ EXTJS12364 selectOnFocus does not work on firefox
+ EXTJS13127 Remotely loading grid combo editor doesn't reset editor inputEl dom value if interrupted during load.
+ EXTJS13331 Form action callbacks should verify that the form is not destroyed
+ EXTJS13796 HtmlEditor with value binding resets cursor position when typing
+ EXTJS14119 Slider widget's vertical, value, minValue and maxValue configs are not documented
+ EXTJS14431 Combobox didn't get empty string value when the field is backspace to empty.
+ EXTJS14530 TagField throws error when setValue is used
+ EXTJS14599 Icons for Center align and right align interchanged
+ EXTJS14607 Datefield Picker lost on month/year click
+ EXTJS14637 Display fields do not allow multi line text
+ EXTJS14638 ComboBox AutoComplete selection lost
+ EXTJS14688 Form validation causes focus to jump
+ EXTJS14722 DisplayField will not display a value if it is boolean false
+ EXTJS14803 Text field does not always remove the emptyUICls when text is added
+ EXTJS14928 The scroller of an editable combobox can't be clicked if the component is focused on IE11
+ EXTJS15000 Combo change event does not fire when last character removed
+ EXTJS15017 combobox - growToLongestValue no longer works
+ EXTJS15021 Combobox doesn't update display value when the source of a chained store loads
+ EXTJS15043 Combobox SPACE key triggers selection
+ EXTJS15065 [5.0.1] A HTML Editor Field in Modal Window Causes an Exception when Pressing Tab.
+ EXTJS15066 Validation error hidden with visibility with ext-all and display with ext-all-debug
+ EXTJS15125 combo listbox collapses after clicking next page btn, scrollbar etc.
+ EXTJS15159 [5.0.1] Form errors make the fields lose focus
+ EXTJS15235 Ext.ux.form.MultiSelect doesn't allow deselection on IE9m
+ EXTJS15239 Cannot use HtmlEditor as an Ext.Editor field
+ EXTJS15275 MultiSelect throws exception when an item is selected
+ EXTJS15286 TagField triggerOnClick no longer working
+ EXTJS15289 ComboBox fires select when value is set without user interaction
+ EXTJS15291 ComboBox.setValue doesn't return itself in nightly build
+ EXTJS15292 Typo in combo updateValue
+ EXTJS15374 ComboBox closes when hovering over tooltip
+ EXTJS15397 Combo collapses list when setting a value not in the store with forceSelection: false
+ EXTJS15398 Fields in field container do not display their labels
+ EXTJS15414 Datefield still allows selection of date beyond maxValue
+ EXTJS15501 Combo auto-reset while typing with query and forceSelection
+ EXTJS15561 Ext.form.field.ComboBox valueCollection is not destroyed in combobox onDestroy method
+ EXTJS15593 Combobox is not refreshing selection when store's filters change
+ EXTJS15633 Formbind needs to be recalculated after field enable/disables
+ EXTJS15639 Tab when DatePicker calendar focused throws error.
+ EXTJS15656 Tag fields with allowBlank:false and a value still fail validation.
+ EXTJS15705 HtmlEditor doesn't resize iframe correctly when switching sizing from shrinkWrap to fixed
+ EXTJS15748 Using chainedstore in combobox causes failure on doSetValue
+ EXTJS15778 Double var declaration in combo
+ EXTJS15928 Cannot use arrow keys in CellEditor and RowEditor.
+ EXTJS6398 Collapsed fieldset in v/hbox does not layout properly
+ EXTJS9943 Form submit does not properly handle a "target" that is a reference to the target iframe

Grid (83)

+ EXTJS10378 Wrong cellEditing context after preventing editing from beforecomplete event
+ EXTJS11150 Wrapping grid cell's contents doesn't work properly when locked columns and bufferedrenderer are configured
+ EXTJS11661 Stateful grouped headers cause layout error when toggling hidden state on group
+ EXTJS11885 Last grouped header doesn't align with its data column after being moved out of its group
+ EXTJS12752 CellEditing plugin stops working when within a collapsed container
+ EXTJS13032 Locking grid not respecting certain cfg's
+ EXTJS13299 List grid filter store gets out of sync with grid store
+ EXTJS13408 Reconfiguring a locking grid doesn't shrinkwrap its columns if there is a checkbox column
+ EXTJS13851 On Safari6, clipping the RowEditor when close to top/bottom of view breaks the RowEditor.
+ EXTJS13871 Grid RowExpander plugin breaks RowEditor plugin
+ EXTJS13924 Grid grouping not functioning when grouping field not specified in store
+ EXTJS14173 The setStore method of grids and trees should be public
+ EXTJS14180 Grouping feature becomes unresponsive to mouse events when changing model id
+ EXTJS14207 Grid filters - updateBuffer config option doesn't work
+ EXTJS14304 Grid column menu shows sub menu when it has no hideable columns and is empty
+ EXTJS14405 Number grid filter treats value=0 as blank
+ EXTJS14408 Row height synchronization fails with locked column
+ EXTJS14415 Grid filters active styling not added to column after refreshing the page when using state
+ EXTJS14557 Row Editing: Grid: Cannot read property 'getAttribute' of null When you render click on add employee button  and scroll down
+ EXTJS14594 Grouping grid does not accept ungrouped Store
+ EXTJS14604 HideHeaders has no effect for PropertyGrid
+ EXTJS14632 Can't select text in grid editor fields
+ EXTJS14634 Toggling grid summary does not refresh in a non-locking grid
+ EXTJS14681 BufferedRenderer can fail to restore focus from an editor if row has been "derendered"
+ EXTJS14684 Checkox Multi Select bug in 5.0.1
+ EXTJS14727 Kitchensink example: Big data grid - Sorting blocks dropdown menus (IE,FF,Chrome)
+ EXTJS14761 Ext.grid.filters.filter.List documentation for "store" wrong
+ EXTJS14768 Grid's horizontal scroll will never go away in Classic theme
+ EXTJS14795 Dirty flag in grid does not disappear when record is committed or rejected
+ EXTJS14819 Selection is wrongly cleared if click misses rows
+ EXTJS14820 Grid's sortableColumns set to false does not turn off column sort
+ EXTJS14831 Grid columns don't line up when there is no scrollbar
+ EXTJS14844 Grid summary column widths are wrong if the store is empty
+ EXTJS14854 Using hideHeaders causes horizontal scrollbar in tree and grid
+ EXTJS14858 Hiding grid column during initComponent for locking grid causes exception
+ EXTJS14859 checkOnly doesn't work on Ext.selection.CheckboxSelectionModel
+ EXTJS14863 Click on action column causes first grid cell to be focused
+ EXTJS14870 Hidden nested group headers are shown when its group is shown
+ EXTJS14874 Widgetcolumn cells are empty when the store is reloaded / loadData
+ EXTJS14875 Cannot deselect grid rows in IE9
+ EXTJS14879 Minimal updating of grid cells causes Element data cached to become unsynchronized.
+ EXTJS14888 The today button on datefield editor does not work
+ EXTJS14889 Month trigger on datefield editor closes immediately
+ EXTJS14892 When expanding a grid row while at the bottom of scroll range, scroll range does not get expanded.
+ EXTJS14896 KS - Grouped Grid:  Groups are not expanding correctly - nightly build 29/Aug
+ EXTJS14901 Picker used in grid cell editor closes instantly on click
+ EXTJS14907 Grid columns not positioned correctly after resize and refresh.
+ EXTJS14950 grid header shifts to left when sort button pressed
+ EXTJS14965 Views should defer saving children tabbable state until TAB key is first used (perf issue)
+ EXTJS14970 Scroll position jumps to top on initial group collapse, failing the action, when inside "auto-grow" height grid
+ EXTJS15028 Property grid - ComboBox can not be open on IE8,IE9
+ EXTJS15034 Grid header get higher z-index than floating window
+ EXTJS15100 Timing issue when rapid scrolling back to rendered area after scrolling into unloaded regions of a Buffered Store.
+ EXTJS15104 RowEditor retains previous values when value not defined in model
+ EXTJS15117 Buffered renderer erroneously moves buffered block in certain cases where new records inserted above the rendered block.
+ EXTJS15177 Boolean column is not refreshing after data changed
+ EXTJS15190 Issues with stateful grid on grouping
+ EXTJS15221 KS - grid plugins check-box model: button disabled state based on selected rows does not work correctly
+ EXTJS15226 BufferedStore#reload does not cause view refresh.
+ EXTJS15284 Moving a header to the locked partner of a locking grid will break if there are no current items in the locked partner's headerCt
+ EXTJS15329 grid filters type:list does not track changes in store content
+ EXTJS15368 KS: Grid plugin - Unchecked checkbox -  CheckboxModel do not call selectionchange event
+ EXTJS15388 Row Selection does not work when grouping a Buffered Store
+ EXTJS15443 Grid reconfigure with locking fails when initially configured with no columns
+ EXTJS15475 Grid selection events fire twice in some cases
+ EXTJS15522 Property grid methods getConfig/setConfig conflict with Ext.Base
+ EXTJS15524 Reloading a BufferedStore causes grids to throw
+ EXTJS15600 Locking view is not relaying tableview row* events
+ EXTJS15643 Scrolling is broken after quickly reloading buffered store several times
+ EXTJS15646 Buffered renderer cannot position the rendered block properly on IE9m
+ EXTJS15680 Calling reconfigure on a grid with locked column throws a js error starting in Nov5 nightly build
+ EXTJS15690 Inserted grid columns lose their position when restoring column state
+ EXTJS15696 Ext.view.Table fails to remove row stripes on store endUpdate
+ EXTJS15769 Ext.selection.CheckboxModel throws exception on range selection
+ EXTJS15779 Grid gets two checkboxmodels in locked grid in nightly build
+ EXTJS15780 Buffered renderer causes exception when store load is called in specific parts of render cycle
+ EXTJS15853 Grid filter plugin error on grid reconfigure with null store
+ EXTJS15878 XML grid and tree - Broken Example, getNodes is not defined
+ EXTJS15917 Hiding and showing group headers are not refreshing the view
+ EXTJS9425 Error on Grouped Grid with Remote Summary when empty
+ EXTJS9525 Grid paging bug when using the grouping feature
+ EXTJS9537 Grid with Grouping Checkboxes - 2 page selection does not work
+ EXTJS9546 remoteRoot in summary feature does not work by itself but only with grouping

Layouts (9)

+ EXTJS13870 boxLabel doesn't layout correctly with form layout
+ EXTJS13918 Collapse/expanding panels with animation do not position sibling items in layouts correctly
+ EXTJS14470 Setting margin on a panel goes to the body, not the element
+ EXTJS14947 scrollable viewport with anchor layout does not account for scrollbar width when sizing children
+ EXTJS15114 A collapsed region in a border layout will layout incorrectly if it is currently floated at the time of the layout
+ EXTJS15192 Button with fix width in column layout causes layout failure
+ EXTJS15335 Components sized by a layout manager can layout wrongly if layout is triggered by changes in their descendant items
+ EXTJS15545 Component.isVisible() with deep: true returns incorrect value in card layout
+ EXTJS9982 VBox align stretch prevents horizontal scrolling even if there is minWidth

Locale (2)

+ EXTJS14636 move locale data from RTL class
+ EXTJS14680 Hebrew thousand/decimalSeparator incorrect

MVC (2)

+ EXTJS11684 The global domain listener doesn't catch idle events from controller.listen()
+ EXTJS14653 Destroying a view with ViewController attached disables listen: {..} handlers

Menu (2)

+ EXTJS15640 Menu focusing and hiding does not properly track focus change
+ EXTJS15873 Grid header menu is not dismissed on mousedown within view

Panel (2)

+ EXTJS12476 Sizing panel from top border does not resize panel correctly
+ EXTJS15361 Panel#setTitle crashes when used in beforeRender hook

Selection Model (5)

+ EXTJS14800 Checkbox selection model config checkOnly is not respected
+ EXTJS14909 Grid Checkbox - once selected checkbox can not be unselected.
+ EXTJS14994 tree selection still remains when parent node removed
+ EXTJS15612 deselectOnContainerClick defaults to true for RowModel/CellModel
+ EXTJS15911 checkboxmodel not clickable with mode: SINGLE

Tabs (7)

+ EXTJS14524 RTL: Ks: Tabs: Side Navigation tabs: Tabs look cut off 
+ EXTJS14733 Cancel tab change event doesnt work correctly
+ EXTJS14835 Clicking custom button in TabBar causes exception
+ EXTJS15381 Tab Panel activates disabled tabs on click
+ EXTJS15727 Tab is preventing card item from being focused
+ EXTJS15791 setActiveTab and activate event not fired when tabs are added via the loader config
+ EXTJS15895 Tab panel with header config and tabBarHeaderPosition mutates the header object

Testing (1)

+ EXTJS15578 Jasmine is broken

Theme (4)

+ EXTJS14627 TagField uses unscoped class name "selected" but should use "x-tagfield-item-selected"
+ EXTJS15496 Misspelled SASS Variable in Ext-Theme-Neutral
+ EXTJS15683 Improve documentation for how to set a UI for panels for both default and -framed
+ EXTJS15904 RTL vertical toolbars don't apply correct margins

ToolTips (2)

+ EXTJS12482 QuickTip isn't shown when interceptTitles is configured
+ EXTJS13313 RowEditor Tooltip stays static in X,Y,Z space if Window containing grid is moved or resized.

Toolbars (1)

+ EXTJS14469 Binding a store to a pagingtoolbar does not update the child components properly

Tree (16)

+ EXTJS13133 Tree panel: clicking on expander icon also selects the node
+ EXTJS13281 setRootNode, collapse node will not allow expand
+ EXTJS13733 Programmatic expansion of a node below collapsed ancestors should work.
+ EXTJS13886 Trees sometimes get horizontal scrollbar even if there is no overflow
+ EXTJS14287 Treepanel using gray theme is horizontally scrollable by default
+ EXTJS14398 rootchange not fired by TreeStore
+ EXTJS14496 Cells in a tree grid are not focusable using the keyboard
+ EXTJS14558 Ext.tree.View - NodeStore unnecessarily required
+ EXTJS14823 Local filter in constructor for TreeStore causes exception
+ EXTJS14913 TreeStore getNodeById cannot be used from nodeappend listener
+ EXTJS14949 Ext.tree.Panel.selectPath does not work when using numeric ids or subclassing the tree panel
+ EXTJS15053 Incorrect scroll position when using buffered rendering tree
+ EXTJS15085 Tree render / expand broken
+ EXTJS15367 TreePanel setRootNode renders nodes incorrectly where TreeStore setRootNode works as expected
+ EXTJS15447 Expanding Tree Node throws error in nightly build
+ EXTJS15876 Drag and drop or collapsing of item in tree causes following items to disappear

Window (12)

+ EXTJS12636 Initially maximized window lays out twice. But is initially small (48x8).
+ EXTJS14665 WindowManager.bringToFront throws an error when an id of a hidden component is passed as argument
+ EXTJS14700 Showing a load mask in when a window has a defaultFocus causes an exception
+ EXTJS14767 Ext.Msg.show() waitConfig not respected
+ EXTJS14825 MessageBox doesn't auto width correctly with large content in IE8
+ EXTJS14925 Window defaultFocus produce an error if combined xtype#id selector used
+ EXTJS15110 Close on window not working when ARIA package included
+ EXTJS15357 Ext.window.Toast should not be focusable
+ EXTJS15392 window header lacks cursor indication "move"
+ EXTJS15477 monitorResize adjusts window size, but not shadow
+ EXTJS15650 Window with maximized: true & constrainHeader: true causes an exception
+ EXTJS15688 Initially maximized window shows maximize tool instead of restore

Total: 358
            
#Release Notes for Ext JS 5.0.1

Release Date: August 5, 2014

Version Number: 5.0.1.1255

##New Features

Accessibility (9)

+ EXTJS-13476 Focused buttons should have a distinct style in all themes
+ EXTJS-13480 Grids and Trees should be in tab order
+ EXTJS-14068 View should focus and navigate with a NavigationModel, not the SelectionModel
+ EXTJS-14183 Focused tabs should have a distinct style in all themes
+ EXTJS-14184 Focused grid cells should have a distinct style in all themes
+ EXTJS-14185 Focused grid headers should have a distinct style in all themes
+ EXTJS-14190 Focused slider thumbs should have a distinct style in all themes
+ EXTJS-14191 Focused dataview items should have a distinct style in all themes
+ EXTJS-14356 Grid header should be tabbable separately from grid view

Bind (2)

+ EXTJS-13763 Selection two-way binding should work consistently across all components that have selection
+ EXTJS-13934 ViewModels should provide a declarative way to create new records

Charts (5)

+ EXTJS-12277 Support themes in Chart, Series, Axes, Sprites and Markers
+ EXTJS-14051 Should provide default markers: Arrow, Square, Triangle, Tick, Diamond, Plus, Cross.
+ EXTJS-14256 Axis 'label' and 'title' config defaults should be controlled from theme
+ EXTJS-14257 Chart themes should follow fonts, sizes and weights of application's Sass theme by default
+ EXTJS-14363 Custom axis label renderer should have an easy way to call the default renderer

Core (3)

+ EXTJS-13664 Should allow minWidth/maxWidth/minHeight/maxHeight configs to be used as responsive configs or in binds
+ EXTJS-13893 Responsive mixin/plugin should provide a way to share calculations (responsiveFormulas)
+ EXTJS-8305 Should provide a way to elevate user code to enable building platform-specific apps (such as Windows 8)

Grid (1)

+ EXTJS-9451 Have option to place RowBody either before or after the data row

MVC (1)

+ EXTJS-13734 Store event domain should provide matching for store aliases like the Controller domain

Tree (1)

+ EXTJS-13611 TreeStore should add parentIdProperty to read linked linear data, and create a tree structure.

Window (1)

+ EXTJS-14046 Floating components should support an "alwaysOnTop" config

Total: 23

##Bugs Fixed

Accessibility (8)

+ EXTJS-13210 Slider thumb does not receive focus
+ EXTJS-13477 Masking should disallow tabbing into masked elements
+ EXTJS-13801 Masked Components should be removed from tab order
+ EXTJS-13802 Viewport should support masking with proper keyboard navigation
+ EXTJS-14316 Invalid input in text field stretches parent container in ext-theme-aria
+ EXTJS-14333 ARIA theme colors are wrong for Grids
+ EXTJS-14351 ARIA: Screen reader: When navigating through the tab panel, voice repeat the elements twice
+ EXTJS-14374 ARIA: Keyboard Navigation: Toolbar: Unable to access to "Choose a date option" in Button menu- Toolbar tab

Bind (10)

+ EXTJS-13303 viewModel binding and fieldLabel, causing wrong message aligment
+ EXTJS-13711 Binding tab title fails for inactive tabs
+ EXTJS-13762 Binding deeply into an object does not always produce the proper value
+ EXTJS-13804 Binding time field prevents typing because of validation
+ EXTJS-13875 Cannot bind to dynamic menu
+ EXTJS-13889 Datefield clears value with specified binding
+ EXTJS-13933 Forms using bind and modelValidation display errors before any fields are modified
+ EXTJS-13935 Bindings are not processed if viewModel data contains an empty record
+ EXTJS-13980 Model validation should prevent putting invalid field values back into the record
+ EXTJS-14276 ViewModel does not respect Model's COMMIT event

Button (4)

+ EXTJS-11964 Links still work after buttons are disabled if tapped on border.
+ EXTJS-13592 Segmented button styling is wrong in RTL mode
+ EXTJS-14297 Aria example - unable to choose an element on menu button in Safari
+ EXTJS-9490 Focused buttons have the same appearance as hovered buttons

Charts (26)

+ EXTJS-12742 Line Chart With Image Markers - fill should be below the stroke
+ EXTJS-13396 Pie chart slices get wrong colors when data is loaded from remote
+ EXTJS-13504 Build of charts code has classes out of order - fails to load
+ EXTJS-13564 There are references to Sencha Touch in some of the Ext JS 5 charts API docs
+ EXTJS-13589 Charts tooltips are not positioned right in IE8 in RTL mode
+ EXTJS-13600 Creating a chart and using renderTo body creates an element without a height
+ EXTJS-13663 Selection from left to rigth is inverted on RTL mode in IE8 and IE9 - Column Charts (RTL)
+ EXTJS-13674 Pareto example left y-axis goes into negative territory when 'Causes' are turned off in the legend
+ EXTJS-13691 3D pie chart doesn't render segments correctly at certain angles.
+ EXTJS-13722 Charts don't render correctly in Firefox with SVG engine.
+ EXTJS-13739 Two SVG text elements are created (for fill and stroke) even when stroke is invisible.
+ EXTJS-13760 Calling store.removeAll() on a chart will not clear the chart series (hangs the browser in Touch)
+ EXTJS-13831 Radar series show with a delay during which markers are visible in the top left corner.
+ EXTJS-13836 Line series marker labels created, but not rendered
+ EXTJS-13848 Series theme styling isn't updated on store changes
+ EXTJS-13882 Setting a store on a chart that hasn't been rendered yet produces no result.
+ EXTJS-13960 Chart tooltips do not show without the itemhighlight interaction
+ EXTJS-14002 textBaseline behavior is not consistent across all browsers and draw component engines.
+ EXTJS-14058 Bound store not working with PolarChart
+ EXTJS-14061 Callout lines are not visible or black when series makes use of gradients.
+ EXTJS-14229 Text is not measured correctly in Safari, Firefox and IE8 in fast mode.
+ EXTJS-14253 All series should provide correct legend info based on the value of their 'hidden' config.
+ EXTJS-14274 Financial Charts doesn't work, candlestick.js not found
+ EXTJS-14290 Scatter chart labels do not always clip properly
+ EXTJS-14340 Crosshair interaction labels don't always align with axis labels.
+ EXTJS-14379 Sencha Charts is not currently pre-built in Ext JS 5, which necessitates Cmd to build the package

Cmd (6)

+ EXTJS-13683 Browser + Cmd warnings on a clean app generated by Cmd
+ EXTJS-14200 Sandbox builds should use "Ext5" for JS root namespace (not "Ext4")
+ EXTJS-14201 Sandbox builds should use "x5" for CSS root namespace (not "x4")
+ EXTJS-14204 Sass lookup fails if classname repeats the namespace (e.g., "MyComponent.MyComponent")
+ EXTJS-14278 Kitchen sink examples broken in RTL mode - Kitchen Sink (RTL)
+ EXTJS-14359 Framing metadata generated for the slicer can conflict with user's pseudo elements

Core (16)

+ EXTJS-13130 Resize handles do not work when nested
+ EXTJS-13559 Class system is not properly handling statics in a privates block
+ EXTJS-13623 Element.isFocusable does not consider tabIndex and does not recognize all focusable elements
+ EXTJS-13676 iOS floating keyboard appears on drag start of a Window
+ EXTJS-13687 Ext.util.Cookies.get isn't unescaped
+ EXTJS-13705 Ext.util.Observable adds an undefined listener if there are none declared
+ EXTJS-13707 Global variable leaks in ClassManager
+ EXTJS-13716 Drop indication line positioned wrong when TouchScroller used
+ EXTJS-13797 Automatic iframes should be non-focusable
+ EXTJS-13822 contentEditable elements should match as tabbable
+ EXTJS-13854 Generated app warns that targetCls is missing in console
+ EXTJS-13861 Container defaults are not properly merged with instance configs of child items that use the config system
+ EXTJS-13952 'mousemove' not fired during drag drop
+ EXTJS-13961 floatingItems remain in memory after being destroyed
+ EXTJS-13966 Object template processes functions as objects.
+ EXTJS-14072 Resizing Windows is constrained to the owning container even when constrain is not configured true

Data (22)

+ EXTJS-13228 Grid using BufferedStore does not update sorters
+ EXTJS-13369 Ext.data.Field mapping does not properly interpret complex expressions
+ EXTJS-13684 ProxyStore throws an error reporting bad usage (Ext.Error.warn should be Ext.log.warn)
+ EXTJS-13689 Models with idProperty causes error on Load
+ EXTJS-13692 TreeStore no longer relays node events.
+ EXTJS-13749 useDefaultXhrHeader on a proxy has no effect
+ EXTJS-13784 Associations fail create duplicate association names
+ EXTJS-13808 Store rejectChanges not removing new records
+ EXTJS-13813 Stores no longer fire the beforesort event
+ EXTJS-13845 TreeStore load event signature does not match Ext.data.Store & Node not passed to load event
+ EXTJS-13983 Records created using WebStorage proxy are not added to the session
+ EXTJS-13992 getAssociatedData does not recurse beyond one level of association
+ EXTJS-13993 Nested association data is not being removed from Model's "data" object
+ EXTJS-13999 Child session serializes dates incorrectly for saving to parent session
+ EXTJS-14003 ManyToOne association broken after removing item from associated store
+ EXTJS-14005 AbstractStore.isDestroyed inconsistent with Ext.Component.isDestroyed
+ EXTJS-14033 Session.adopt does not adopt any associated records
+ EXTJS-14097 Many To One Association with session does not keep track of associated records when directly adding to the session
+ EXTJS-14141 Store load method does not respect "url" option
+ EXTJS-14170 Unable to define a default reader in a custom proxy class
+ EXTJS-14286 XmlReader fails when reading tree data
+ EXTJS-14513 Configuring a TreeStore with a model that is not a TreeModel throws an error

Draw (1)

+ EXTJS-14045 "Uncaught TypeError: Cannot read property 'path' of undefined" when trying to draw a line from the inside to the outsides of the drawable window - Free Paint

Events (1)

+ EXTJS-14142 IE9 event.browserEvent member not found

Examples (32)

+ EXTJS-13001 Ext JS Portal Example  - Dashboard does not maintain Column/Row transitions properly
+ EXTJS-13352 has no method 'doComponentLayout'  - when you try to change from Month to week or day
+ EXTJS-13489 TypeError: 'undefined' is not an object (evaluating 'target.className.indexOf') when opening any example 
+ EXTJS-13531 If a draggable field is set empty, its message box looks cut off when is dragged in to a grid - Field to Grid
+ EXTJS-13548 Slider example should update colour on drag rather than at end. Needs minValue:0
+ EXTJS-13565 Drag and drop does not working in RTL mode - IE8,IE9
+ EXTJS-13569 Grids - Array Grid (RTL Hebrew) By placing the mouse pointer on the column header, it does not allow to sort asc/desc or move on IE8 and IE9
+ EXTJS-13618 "Uncaught TypeError: object is not a function" when trying to open Interactive Dashboard - Combination Charts
+ EXTJS-13639 Unable to move element from one tree to another in RTL mode on IE8 and IE9 - Two Trees (RTL)
+ EXTJS-13670 Excutive Dashboard, The grid doesn't collapse and open the groups
+ EXTJS-13693 Dashboard layout does not properly cleanup removed items
+ EXTJS-13699 TypeError: 'null' is not an object (evaluating 'me.dom.id') and crashes when clicking on Accordion Windows and then clicking on the refresh button many times 
+ EXTJS-13761 "Uncaught TypeError: Cannot read property 'type' of undefined" when trying to use the functionality within the example - Summary Grid
+ EXTJS-13765 Ext.ux.IFrame should updated to avoid usage of renderSelectors.
+ EXTJS-13841 Ajax Tool tip does not load when clicking - QuickTip example
+ EXTJS-13852 "Uncaught SyntaxError: Invalid regular expression" when used parentheses in search - Live Search
+ EXTJS-13853  "Uncaught TypeError: Cannot read property 'apply' of undefined" when trying to alter data within the example in RTL - Summary Grid (RTL)
+ EXTJS-13856 Unable to show window if "Insert Image" button is clicked twice - Advance Dataview
+ EXTJS-13945 Executive Dashboard Example fails to load with 404
+ EXTJS-13959 Ks crashes when opening Interactive Dashboard and try to sort any column
+ EXTJS-13964 Uncaught TypeError: Cannot read property 'getSurface' of undefined and unable to use Free paint example
+ EXTJS-14195 Unable to use desktop example when changing the theme 
+ EXTJS-14244 Text Boxes inside the windows look cut off (ARIA example)
+ EXTJS-14248 Unabled to access to DataView Content using tab key - ARIA Examples
+ EXTJS-14283 JavaScript errors in ARIA demo
+ EXTJS-14292 The grid resize to the minimum size when you select the checkbox "Editable" and press Tab Key - Aria Examples 
+ EXTJS-14296 Cannot read property 'appendChild' of null, when you navigate to the example - Simple Tasks example
+ EXTJS-14385 KS - Main menu cannot scroll on Ipad
+ EXTJS-14422 Kitchen Sink - Only two categories are displayed in the tree before collapsing some of them (Ipad)
+ EXTJS-14423 ARIA:Center Panel: Window Tab : When you kept the window open and change the tab, the components does not render the css correctly 
+ EXTJS-14442 Loading ExtJS Examples in any IE version generates AppCache Fatal Error
+ EXTJS-14516 Page Analyzer fails to load

Forms (23)

+ EXTJS-13495 Slider widget allows text selection upon mousedown
+ EXTJS-13675 Multiselect grid, touch themes. The "remove" ActionColumn escapes the grid.
+ EXTJS-13713 Form field triggers do not render correctly in classic theme/RTL mode
+ EXTJS-13752 In Firefox, multi-line labels cause input and triggers to expand vertically
+ EXTJS-13770 Spinner triggers in neptune-touch and crisp-touch wrap when the field is too narrow
+ EXTJS-13793 HtmlEditor iframe does not respect height config
+ EXTJS-13803 Fields with "grow:true" cannot have their size configured or set by layout
+ EXTJS-13818 DisplayField's body element should have vertical-align:top
+ EXTJS-13915 labelStyle no longer applied to label's style
+ EXTJS-13957 combobox does not scroll when using keyboard
+ EXTJS-14000 Combo boundlist duplicates content outside tpl tags
+ EXTJS-14004 Datepicker does not blur when clicking outside the component if showToday is false
+ EXTJS-14077 Numberfield crashes when holding the mouse down over one trigger and switching to another
+ EXTJS-14110 tagfield config filterPickList implementation doesn't filter list correctly
+ EXTJS-14154 TagField cannot be bound to a store dynamically
+ EXTJS-14157 Slider prevents tabbing out of the thumb
+ EXTJS-14163 Time field throws JavaScript error on validation
+ EXTJS-14259 inputType: 'search' causes text field to be rendered incorrectly
+ EXTJS-14305 HtmlEditor destroys iframe element twice which causes spurious warning
+ EXTJS-14310 HiddenName for ComboBox does not create hidden field
+ EXTJS-14312 Ext.picker.Date cannot be rendered as disabled
+ EXTJS-14450 Slider movement not reversed in RTL
+ EXTJS-14467 Date field trigger icon is wrong in RTL

Grid (32)

+ EXTJS-10667 Column resize restrictions should not apply on locked columns when locked view is resizable or can scroll horizontally
+ EXTJS-13020 Ext.grid.locking.View: Listener leak
+ EXTJS-13290 Multi-selector grid does not load data when adding Employees 
+ EXTJS-13519 Summary values are not being updated if summary is hidden before change values - Summary Grid
+ EXTJS-13580 Grids with auto height are created with buffered renderer enabled which does not support auto height
+ EXTJS-13688 GridFilters throws an error when removing custom filters
+ EXTJS-13703 Row Editing only updates the tooltip with the first invalid field.
+ EXTJS-13715 Reconfigure should move the buffer rendered body to the top.
+ EXTJS-13753 Grid - Summary feature not working with convert/calculate fields
+ EXTJS-13759 Rownumberer/Action Column causes error when updating row
+ EXTJS-13773 Grid reconfigure on a locked grid does not resize locked side correctly
+ EXTJS-13787 Grid filters store does not react after reconfigure
+ EXTJS-13805 Grid itemCls is set to 'x-dataview-item' but should be 'x-grid-item'
+ EXTJS-13814 Grouping/Summary grid features enable/disable broken
+ EXTJS-13816 Columns in "Quarter" category are unable to show after following certain steps - Executive Dashboard
+ EXTJS-13819 Typing spaces in a grid cell editor toggles checkbox in other column
+ EXTJS-13826 Resizing grid column with wrapping content causes random errors or misplaced grid view
+ EXTJS-13859 Grouping collapse crashes when using a custom groupFn on the grouper
+ EXTJS-14024 Gridfilters initialized with a value of Boolean false are not set as active
+ EXTJS-14073 widgetcolumns won't work with flex
+ EXTJS-14084 Horizontal scrollbar doesn't appear on Grid Reconfigure for empty Store (in FF and Chrome)
+ EXTJS-14227 Grid reconfigure with a new store fails when the store goes from grouping to no grouping
+ EXTJS-14232 Grid grouping headers can create invalid identifiers
+ EXTJS-14252 Big Data Grid Example - Cannot use check boxes 
+ EXTJS-14258 Grid cell editors not destroyed when editors have not been activated
+ EXTJS-14262 getWidgetRecord() not binding correctly when adding records
+ EXTJS-14285 BufferedRenderer.onReplace sets refreshing flag incorrectly
+ EXTJS-14309 List filter should properly implement loadOnShow functionality
+ EXTJS-14387 Cell focus styling blocks mouse events
+ EXTJS-14440 Arrow key navigation does not select cells properly in IE
+ EXTJS-14441 Date picker focus conflicts with grid cell editing
+ EXTJS-14536 Locking grids cannot disable buffered rendering

Layouts (1)

+ EXTJS-13751 Ext.layout.container.Box should require Ext.resizer.Splitter

MVC (3)

+ EXTJS-13747 Plugins are not processed if the component is used in autoCreateViewport
+ EXTJS-13867 defaultListenerScope:true does not work on a View that has a ViewController
+ EXTJS-14282 ViewControllers do not clear listeners on destroy

Menu (3)

+ EXTJS-13849 Unable to create menu before onReady
+ EXTJS-13895 Clicking a menu item with href config causes two click events
+ EXTJS-14298 The menu expanded does not close when change to another example in ARIA example 

Misc (2)

+ EXTJS-12096 The constructor of Ext.resizer.Resizer is missing a variable reassignation and results in an error
+ EXTJS-14295 Responsive plugin throws error when created from config object

Panel (2)

+ EXTJS-13776 Ghost panel header does not respect titlePosition during drag
+ EXTJS-13791 Panel collapsed config cannot be used in data binding (need to have setCollapsed method)

Selection Model (2)

+ EXTJS-13850 Ctrl+A not triggering 'selectionchange' event in grid
+ EXTJS-14255 Grid doesn't select newly synced records

Tabs (3)

+ EXTJS-13679 Tab bar loses height when all tabs are closed
+ EXTJS-13723 Cannot add non-tab items to tabBar.
+ EXTJS-14366 Using tabPosition with non-tab items throws undefined error

Theme (3)

+ EXTJS-13786 "Trial" text covers App Name in RTL mode
+ EXTJS-13899 Neptune's $grid-header-trigger-background-color-open cannot be overridden
+ EXTJS-14126 Checkboxgroup error border css incorrect

ToolTips (6)

+ EXTJS-12041 Tooltips get overly wrapped on Safari
+ EXTJS-12511 Narrow tooltips in Safari Mac
+ EXTJS-13334 Tooltip is horizontally squished in Safari
+ EXTJS-13890 Error Quicktips not showing on floating form's fields when the form created at runtime
+ EXTJS-14086 IE9 tooltip layout cutting off text
+ EXTJS-14438 Tooltips don't accommodate text properly in IE9

Toolbars (1)

+ EXTJS-13941 Navigation disappears when opening any form, Toolbars or layout example and change to another example 

Tree (11)

+ EXTJS-12962 TreeStore datachanged is not fired when data is changed
+ EXTJS-13049 Tree singleExpand is lost when store is changed via reconfigure
+ EXTJS-13346 Reader typeProperty is not respecting reader's namespace
+ EXTJS-13509 Appended nodes are not correctly parsed
+ EXTJS-13673 Buffered rendering is not enabled by default in Trees.
+ EXTJS-13727 Loading a Tree on demand doesn't work
+ EXTJS-13858 Tree navigation disappears when opening Hbox layout example and then change to another form example
+ EXTJS-13908 Rows disappear after collapsing and expanding the first row on the grid in Tree examples
+ EXTJS-14107 Tree fires double sortchange event when sort changes
+ EXTJS-14268 Treepanel relays old treestore node event names
+ EXTJS-9364 Cannot hide loadMask when using BufferedRenderer plugin on Tree

Window (3)

+ EXTJS-13799 Ext.Window's maximizable config modifies the title position, causing the title position to move while dragging
+ EXTJS-14001 Windows do not constrain properly when maximized
+ EXTJS-14291 Unable to use the keys when opening window and close it (Aria example)

Total: 221

##Known Issues

Accessibility (1)

+ EXTJS-14427 Date picker dropdown calendar causes navigation issues with JAWS

Charts (1)

+ EXTJS-10739 RTL Charts do not correctly display bidirectional text

Core (3)

+ EXTJS-12058 Sandbox mode is not working
+ EXTJS-12418 Dynamic loader fails to load CSS in Safari 5
+ EXTJS-12947 Ext.Layer and Ext.LoadMask no longer support shim

DataView (1)

+ EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad

Examples (2)

+ EXTJS-12089 Grouped tab examples for 5.0 is broken
+ EXTJS-13879 Dashboard/Portal needs (tablet friendly) Drag/Drop Ghosting experience

Layouts (1)

+ EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container

Tabs (1)

+ EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0

Total: 10
            
# Release Notes for Ext JS 5.0.0

Release Date: May 31, 2014

Version Number: 5.0.0.967

## New Features

Bind (1)

+ EXTJS-12657 ViewModel formulas should be given a "get" function as a parameter rather than a data object

Charts (6)

+ EXTJS-12375 Gauge charts don't support 'axes' config
+ EXTJS-12699 The sencha-charts package should support IE8 (VML)

+ EXTJS-12725 Sencha Charts package should support tooltips 
+ EXTJS-12891 Sencha Charts package should support RTL
+ EXTJS-13072 Sencha charts should support image download service
+ EXTJS-13074 Implement image download server for sencha-charts package

Core (2)

+ EXTJS-12628 Observable listeners need to be merged or better aggregated to support declarative listeners
+ EXTJS-13231 Provide a mixin and plugin to support declarative syntax for specifying responsive config values

Data (3)

+ EXTJS-12085 Ext.data.Model should onLoad template method when nested associations are finished loading
+ EXTJS-12932 Reader and Writer should provide a way to transform data prior to use
+ EXTJS-12981 Pass full response in an Operation exception

Grid (2)

+ EXTJS-11505 Update Grid Filters from user extension to framework plugin
+ EXTJS-12306 Ext.view.View class should have a refreshNode method that can accept index or record

MVC (1)

+ EXTJS-13064 ViewController should support routing

Misc (1)

+ EXTJS-13027 Add utility class for base64 encoding/decoding

Tabs (1)

+ EXTJS-13265 Tab panels should allow combining title and tabbar

Toolbars (1)

+ EXTJS-13236 Small form factors need a breadcrumb component that operates on a TreeStore

Total: 18

## Bugs Fixed

Bind (1)

+ EXTJS-13373 Replacing objects in a ViewModel breaks binds to contents of that object

Button (2)

+ EXTJS-13574 Buttons with a width do not render framing correctly in IE8
+ EXTJS-13601 Disabled buttons lose rounded corners and show a dark border in IE8 (affects all themes)

Charts (20)

+ EXTJS-11926 Ext.draw.engine.Svg - undeclared cfg variable
+ EXTJS-12282 Charts: Two canvas elements are created for each surface.
+ EXTJS-12283 Sencha charts should support adjustByMajorUnit like legacy charts
+ EXTJS-12352 Labels are not displayed in scatter charts
+ EXTJS-12517 Charts download without title - Android
+ EXTJS-12549 Free Paint Example broken in Android and IOS
+ EXTJS-12746 Hovering/Clicking with Scatter Chart causes other items to highlight
+ EXTJS-12753 Charts in Accessibility Theme look bad
+ EXTJS-12825 Using chart.sprites instead of chart.items config results in different position for sprites.
+ EXTJS-12847 Touch Charts Kitchen Sink dont load in IE8
+ EXTJS-12917 Legend item text is not displaying correctly
+ EXTJS-12996 Box of company selected is cut in Combination charts - Interactive Dashboard (Ipad)

+ EXTJS-13085  Chart is not updated when a single store record is changed.
+ EXTJS-13257 Sencha Charts does not support RTL in IE8
+ EXTJS-13309 Cannot create an unrendered chart
+ EXTJS-13444 Touch charts examples does not loaded on IE8 - Object doesn't support this property or method
+ EXTJS-13467 Pie chart labels should use a callout when label.display config is set to 'outside'.
+ EXTJS-13470 Image sprites do not support transformations other than translation in IE8 (excanvas bug).
+ EXTJS-13471 Image sprites are not rendered if width and height are not specified.
+ EXTJS-9280 Scatter series isn't shown on legend click

Cmd (2)

+ EXTJS-13007 Warnings in console from basic app generated by cmd
+ EXTJS-13372 basic application skeleton Ext.application fails

Core (14)

+ EXTJS-12514 Drag-drop does not constrain to viewport
+ EXTJS-12720 ComponentQuery.query doesn't accept commas
+ EXTJS-12878 Tapping on a menu item does not open the sub menu in IE10 on touch screen device
+ EXTJS-12945 Touch scroller position is not correctly updated when scrolling using the mouse on a multi-input Windows8 device
+ EXTJS-12946 Focus causes the browser to scroll using scrollTop. If touchScroll === 2, this causes a "stuck" UI
+ EXTJS-12949 Ext.util.CSS.createStyleSheet fails on IE11
+ EXTJS-13019 Portal examples loads but then the layout goes wrong and all content disappears on iPad
+ EXTJS-13029 Element and Fly do not wrap nodes consistently and should be more compatible with 4.x for certain types
+ EXTJS-13043 Menus are not referencing their proper menuItem owner when using child combinators in a selector for Component EventDomains
+ EXTJS-13051 Dashboard's columns do not reallocate columnWidths correctly after column removal.
+ EXTJS-13055 Mixin.Observable allows mixed case events
+ EXTJS-13111 Ext.Object.each does not iterate several properties on old IE like "constructor" or "toString"
+ EXTJS-13195 Impossible to clear cookies or set cookie to empty with IE
+ EXTJS-13279 EventObject.hasModifier() returns undefined instead of false

Data (8)

+ EXTJS-12979 Models with inherited reference fields do not create their own assocation
+ EXTJS-13006 Cannot subclass a Model properly
+ EXTJS-13061 metachange listener isn't called on Store and Proxy
+ EXTJS-13129 missing 'operation' parameter in Ext.data.proxy.Memory#destroy function declaration
+ EXTJS-13226 Grid using BufferedStore sometimes renders wrong rows
+ EXTJS-13407 Chained stores don't seem to reflect changes to parent store filter
+ EXTJS-13535 TypeError: 'null' is not an object (evaluating 'Ext.fly(c).getStyle') and data is not loading when opening the example 
+ EXTJS-4494 WebStorage proxy does not correctly handle read Operations with filters and sorters

DataView (1)

+ EXTJS-13546 DataView non-record nodes repeat on refresh

Draw (1)

+ EXTJS-13419 Draw's TextMeasurer tries to access the document body before Ext is ready

Examples (31)

+ EXTJS-12158 Portal example. Dropping a Panel focuses it which causes the browser to scroll it into view.
+ EXTJS-12346 MVC feed viewer - Go to post button not working
+ EXTJS-12417 Kitchen Sink doesn't work in Android 
+ EXTJS-12641 Organizing Images into Albums Example - Tree does no work correctly
+ EXTJS-12678 In the Slider Examples the customized CSS slider is not styled correctly.
+ EXTJS-12739 Cannot read property 'id' of null  - MultiSelect & ItemSelector
+ EXTJS-12772 Touch charts - Free Paint Cannot draw lines on touch. Cannot make dots with mouse.
+ EXTJS-12785 TypeError: 'undefined' is not a function (evaluating 'fs.each') after click on edit detail event and try to save in Combination\ Calendar Sample 
+ EXTJS-12790 Failed to load resource: 404 (Not Found) after add Cnn's  Feed and try to expand it in Combination/  Portal 
+ EXTJS-12792 Toggle button on Basic Panel with Toolbars looks cut in Combination\ Themes example 
+ EXTJS-12796 West panel does not marked the correct number of elements inside the folder/List after add other folder/List  in Simple Task example 
+ EXTJS-12797 Cannot read property 'message' of undefined - Ext.data.writer.Writer JsonP Example
+ EXTJS-12799 Portal example crashes after close all windows and add a new feed.  TypeError: 'undefined' is not an object (evaluating 'n.items') 
+ EXTJS-12812 KS grid filtering example does not fit in screen in android
+ EXTJS-12814 The error message tool tip is not working correctly or validating - Ext.Direct Form Integration
+ EXTJS-12849 KS - Drawing ->  Browser Logos Example expands code preview when expanding the "draw component" window
+ EXTJS-12895 MultiSelect & ItemSelector Example popup window has clipped content
+ EXTJS-12915 Message's TextBox on Mixed Layout Form in LayOut example  looks cut  - blue line should appear in the complete text box
+ EXTJS-12972 Size column looks cut in ListView Example (iPad) 
+ EXTJS-12974 One patient cannot be registered more than once in a hospital, Patient Hospital Assignment example
+ EXTJS-12983 Grid filtering example has clipped content
+ EXTJS-13091 Cannot read property 'apply' of undefined When clicking any tabs - Tabs KitchenSink
+ EXTJS-13092 Drag and drop fail in all examples (Ipad, PC with Smart Touch)

+ EXTJS-13167 TypeError: 'null' is not an object (evaluating 'this.getNodeContainer().childNodes') and never stop loading
+ EXTJS-13202 TypeError: 'null' is not an object (evaluating 'l.bind') when clicking a row in Data binding- Associations example
+ EXTJS-13363 Charts Touch Examples does not loaded - Cannot read property 'on' of undefined
+ EXTJS-13371 Writer and Writer JsonP:  The ID is "Write" when you add a new row
+ EXTJS-13401 Ticket example crashes after login ...TypeError: 'undefined' is not an object (evaluating 'f.getLegendStore().on') 
+ EXTJS-13603 Uncaught ReferenceError: me is not defined - When navigate to Multi Sort Grid Example 
+ EXTJS-13649 Ticket App example charts no longer load
+ EXTJS-8089 Combination examples : Theme viewer : Text "Editor" getting  disturbed upon clicking "Source" button.

Forms (9)

+ EXTJS-10150 Radio buttons don't allow selection by tapping label on iPad
+ EXTJS-11673 IE8 textarea scroll issues
+ EXTJS-12613 Form field "grow" functionality does not work.
+ EXTJS-12666 DateField doesn't select today on SPACE
+ EXTJS-12843 Clicking boxLabel doesn't select check/radio in IE10/11.
+ EXTJS-13048 Thumbs in multi sliders can get "stuck" when all set at extreme upper bounds.
+ EXTJS-13058 Combo does not show listConfig.emptyText on first expand
+ EXTJS-13062 Timefield clears seconds back to 00 
+ EXTJS-6360 ComboBox's setValue call with a remotely loaded Store issues

Grid (36)

+ EXTJS-11118 FiltersFeature Filter doesn't apply value for initial filtering
+ EXTJS-11885 Last grouped header doesn't align with its data column after being moved out of its group
+ EXTJS-11886 Make grid's buffered renderer work correctly with rowbody feature
+ EXTJS-12056 Grids do not display columns properly in RTL
+ EXTJS-12134 Grid preview and rowexpander break scroller when expanded or collapsed
+ EXTJS-12633 Reconfigure on metachange fails on buffered store
+ EXTJS-12779 Property grid duplicates fields during editing
+ EXTJS-12829 Grid filter example does not load data (Failed on Android) 
+ EXTJS-12842 Grid row drag/drop using mouse does not work on Windows8/IE10+ when a touch-screen is present
+ EXTJS-12871 Not enought space for buttons in Grid Filter example
+ EXTJS-12880 Grid header lags on horz scrolling in IE8
+ EXTJS-12960 isCollapsedPlaceholder is undefined
+ EXTJS-12963 Components in the header of a hidden column stay hidden once the column is shown
+ EXTJS-12968 KitchenSink - Basic Associations throws JS error when sorting Orders grid prior to selecting Customer
+ EXTJS-12998 Resizing columns to the left of its border makes them unable to see or use.
+ EXTJS-13002 RowEditing's editors misaligned if setEditor called onBeforeEdit
+ EXTJS-13010 Grid reconfigure not working
+ EXTJS-13016 RowEditing doesn't start the first time if no editor defined on (dbl)clicked cell
+ EXTJS-13050 LoadMask does not appear when asynchronously loaded stores initiate a load request.
+ EXTJS-13052 Widget combobox does not have drop down selection menu in Grid
+ EXTJS-13110 The grid summary row exists, but no summary value is displayed
+ EXTJS-13142 Grid reconfigure doesn't work with widget column
+ EXTJS-13171 Roweditor does not reorder columns correctly when there are hidden columns
+ EXTJS-13272 Grid selection property does not support two-way binding
+ EXTJS-13322 RowEditor startEdit does not start editing
+ EXTJS-13350 Expand/Collapse (grouping) causing grid rows to go blank
+ EXTJS-13375 Summary values are not changing when modifying a row in Summary Grid example 
+ EXTJS-13388 Binding data/columns does not work with grid grouping
+ EXTJS-13405 Summary values are not showing the correct value in Remote summary Grid example
+ EXTJS-13461 Grouped grid cell edit is broken if sorting enabled
+ EXTJS-13506 Saving record in the grid that has actioncolumn throws an error
+ EXTJS-13518 onReplace handling of buffer renderer leaves view in incorrect state
+ EXTJS-13532 Data is not loading when opening the example, collapse the grid, change to another and back to the example in XML Grid example   
+ EXTJS-13599 Grids do not lay out when the data height changes.
+ EXTJS-7273 FiltersFeature does not respond to the grid's reconfigure event
+ EXTJS-9492 Grid Filters Feature clears existing filters on store

Layouts (4)

+ EXTJS-13099 Border layout resize issue (if touchscreen is present)

+ EXTJS-13119 iOS6 viewport body height is 0 resulting in unusable UX
+ EXTJS-13164 Portal example crashes after open the example and wait for few seconds in portrait mode (Android 4.4.2) and Windows 8.1 with smart Touch
+ EXTJS-13253 Accordion layout doesn't expand/collapse when clicked on tool or title

MVC (3)

+ EXTJS-12090 Controller vs Component - event name casing is not consistent
+ EXTJS-12488 Back button is not enabled in history examples
+ EXTJS-12853 MVC- FeedViewer example,  "Go to post" button is not working in IE8 

Menu (1)

+ EXTJS-13044 Menu alignment fails for first click (grid header menus appear at wrong location)

Panel (1)

+ EXTJS-12705 Body does not allow scroll when grid is disabled in IE

Tabs (1)

+ EXTJS-13496 TypeError: 'null' is not an object (evaluating 'this.lookupReference("positionBtn").setValue') and crashes when clicking in "Auto Cycle" button and change to another example 

Theme (3)

+ EXTJS-12621 Framed panels do not render correctly in IE8 using Crisp theme
+ EXTJS-13084 Slicer fails due to missing assets for Cell button.
+ EXTJS-13392 Sliders in Crisp Touch have visual artifacts and repeating backgrounds

ToolTips (1)

+ EXTJS-12942 Ext.tip.Tip is missing "tip" xtype

Tree (3)

+ EXTJS-12837 Tree sorting with buffered rendering does not work
+ EXTJS-13191 In Custom Tree Drop Logic example cannot Drop (Android 4.4.2) 
+ EXTJS-13212 XML Tree example does not load data 

Window (4)

+ EXTJS-12738 Windows Example, Header-constrained window is not contained within its parent
+ EXTJS-12927 MessageBox does not properly shrinkWrap the height of text
+ EXTJS-13003 Desktop Combination Example - TypeError: Cannot call method 'isFocusable' of null 
+ EXTJS-13082 Toast component sass is referencing wrong image format leading to compile errors. Image assets are corrupted

Total: 146

## Known Issues

Charts (1)

+ EXTJS-10739 RTL Charts do not correctly display bidirectional text

Core (3)

+ EXTJS-12058 Sandbox mode is not working
+ EXTJS-12418 Dynamic loader fails to load CSS in Safari 5
+ EXTJS-12947 Ext.Layer and Ext.LoadMask no longer support shim

DataView (1)

+ EXTJS-12345 ComboBox's bound list becomes transparent on second show on iPad

Examples (1)

+ EXTJS-12089 Grouped tab examples for 5.0 is broken

Layouts (1)

+ EXTJS-4768 Border Layout : regions overlap when size (or size constraint) won't allow all regions to fit container

Tabs (1)

+ EXTJS-13538 Ext.ux.TabScrollerMenu does not work with Ext JS 5.0

Total: 8

# Release Notes for Ext JS 5.0.0 Beta

Release Date: April 2, 2014

Version Number: 5.0.0.732

## Bugs Fixed

Accessibility (1)

+ EXTJSIV-12708 Key Feed Viewer example does not load, TypeError: 'undefined' is not a function (evaluating 'b.getKeyNav.enable()')

Bind (3)

+ EXTJSIV-12454 Cannot bind tab title using view model
+ EXTJSIV-12660 Formulas cannot be inherited from a mixin
+ EXTJSIV-12765 KitchenSink binding formulas example throws error

Button (2)

+ EXTJSIV-11967 Kitchen Sink Buttons - In the classic theme the buttons have two icons
+ EXTJSIV-12684 Kitchen Sink - Multisort DataView Example sort buttons(Type, Name) are not working correctly on iPad 

Charts (37)

+ EXTJSIV-11907 Save chart button not working
+ EXTJSIV-12125 Chart component stops displaying
+ EXTJSIV-12126 Charts Series do not hide correctly via the legends
+ EXTJSIV-12211 On hiding series via chart legend, the charts doesn't reappear correctly
+ EXTJSIV-12267 Users should be able to use chart.items config to add custom sprites to the chart.
+ EXTJSIV-12273 Charts: Line series Markers are not displayed
+ EXTJSIV-12275 Charts: Axis label renderers don't work
+ EXTJSIV-12278 Charts: Interactions don't work
+ EXTJSIV-12280 Charts: Implement the 'clockwise' config to control the sense of rotation of the Pie slices
+ EXTJSIV-12281 Charts: Polar chart labels are clipped
+ EXTJSIV-12328 Legend item titles don't update correctly when series titles do
+ EXTJSIV-12341 Save Chart button stops working on 'Custom Pie chart' example
+ EXTJSIV-12354 Charts: animations are broken
+ EXTJSIV-12381 The downloaded image does not have format
+ EXTJSIV-12392 Touch Charts labels on Pie chart doesn't fit correctly
+ EXTJSIV-12428 Line chart with Image markers not loading markers
+ EXTJSIV-12448 Charts do not reconfigure properly using a store bind from the viewModel
+ EXTJSIV-12490 Download chart issues in IE9, IE10, IE11
+ EXTJSIV-12516 Kitchen sink crashes when selecting Interactive Dash example
+ EXTJSIV-12519 3D pie chart rare refreshing error
+ EXTJSIV-12564 Chart legend does not layout properly when items are added to the store
+ EXTJSIV-12566 Charts Kitchen Sink - Chart does not download 
+ EXTJSIV-12590 Chart interactions don't work
+ EXTJSIV-12643 Chart does not redraw when the store changes
+ EXTJSIV-12709 Charts Kitchen Sink - After pressing Save Chart Button the Chart Preview does not load correctly on iPad(iOS 7.1)
+ EXTJSIV-12724 Broken dialog in basic charts example
+ EXTJSIV-12726 Visual jitter effect when enabling/disabling legend items in charts
+ EXTJSIV-12727 3D column chart axis intermittently displays
+ EXTJSIV-12743 Charts with Zoom will not zoom on first click 
+ EXTJSIV-12745 Charts downloaded image has no background
+ EXTJSIV-12751 Combination Charts - Interactive Dashboard labels visually cut off
+ EXTJSIV-12768 Charts throw JS error due to getId accessing this.initialConfig
+ EXTJSIV-12784 Touch Charts "save chart" button not working in Firefox
+ EXTJSIV-12826 IE8: Legacy Charts Array.indexOf unsupported throughout examples
+ EXTJSIV-12827 Legacy Charts labels on Pie chart doesn't fit correctly
+ EXTJSIV-12846 Ticks should never render at axis intersection points.
+ EXTJSIV-12874 Labels are not rendered in bar series.

Cmd (2)

+ EXTJSIV-11772 Mixins cannot reliably be overridden in dev mode
+ EXTJSIV-12382 KitchenSink buttons examples fail due to missing table layout in build output

Core (13)

+ EXTJSIV-9348 Ext.onReady(function(){console.log('ready!');}, null, {delay: 500}) causes infinite loop
+ EXTJSIV-11842 Dom publisher does not automatically remove all of its listeners on window unload
+ EXTJSIV-12043 Gestures stop working when an element is removed from the DOM mid-gesture.
+ EXTJSIV-12300 Image Organizer throws error when adding images to folders
+ EXTJSIV-12447 New loader metadata not yet present in ext.js and ext-debug.js - use ext-all for now.
+ EXTJSIV-12546 Kitchen Sink  - Drag And Drop fails  
+ EXTJSIV-12561 data.Connection::upload method uses Flyweight to set 'load' listener on IFRAME
+ EXTJSIV-12596 ComponentQuery throws an error when loadMask:true is specified on some child component
+ EXTJSIV-12774 Updating HTML content does not always refresh touch scroller to make that content available.
+ EXTJSIV-12788 Element.repaint timer exceeds life of the Element
+ EXTJSIV-12789 IE11 now uses standard CSS API breaking old IE workarounds
+ EXTJSIV-12924 Standalone in-page examples scroll the document when a component is touchscrolled
+ EXTJSIV-9267 XTemplate applyOut should not swallow exceptions

Data (11)

+ EXTJSIV-11557 Modifying model instance field can change defaultValue
+ EXTJSIV-12237 Store does not serialize sorters unless there is a grouper too.
+ EXTJSIV-12398 In Data Binding, Formulas doesn't calculate correctly in IE9, IE10 and IE11
+ EXTJSIV-12466 KS - Advanced Data examples crash KS
+ EXTJSIV-12565 Store sort is not toggling/promoting existing sorters
+ EXTJSIV-12592 Date field in a Model returns string instead of Date object
+ EXTJSIV-12595 Grouping does not work on BufferedStore
+ EXTJSIV-12658 Collection#itemChanged when changing a field which changes position reports the wrong index in the itemchange events.
+ EXTJSIV-12673 Binding traversal of associations ignores nested data that's already there
+ EXTJSIV-12905 BufferedStore does not respond to remoteFilter:true or remoteSort:true
+ EXTJSIV-12913 cell to cell DnD example, grid showing NAN value

DataView (8)

+ EXTJSIV-12062  Unable to close Image chooser
+ EXTJSIV-12063 Unable to resize window dataview 
+ EXTJSIV-12066 Unable to select insert image button
+ EXTJSIV-12215 Advanced DataView Example crashes often
+ EXTJSIV-12266 Dataview Chooser example fails to load
+ EXTJSIV-12372 Dataview Example fails to load correctly.
+ EXTJSIV-12475 Animated DataView Example fails to load due to 'size is not defined' error
+ EXTJSIV-12518 Multiselect DataView example not scrolling

Direct (2)

+ EXTJSIV-12030 The accordion does not fit well to the screen
+ EXTJSIV-12401 Direct Tree example crashes

Draw (3)

+ EXTJSIV-12217 Draw Examples IE8 Images not displaying
+ EXTJSIV-12309 Rotate text Example not rotated
+ EXTJSIV-12481 Sprite does not call Observable constructor

Events (1)

+ EXTJSIV-12835 Gestures do not work in IE10/11 when the gesture target is inside a scrollable container

Examples (59)

+ EXTJSIV-12031 Styles not being applied correctly on 'Checkbox / Radio Groups' sample
+ EXTJSIV-12044 KS - Slider example ghost images on Ipad
+ EXTJSIV-12047 Styles not being applied correctly on 'Rest Proxy' example
+ EXTJSIV-12059 Input errors/calendar are not in dutch
+ EXTJSIV-12061 Some fields in fieldcontainer example are clipped on iPad
+ EXTJSIV-12064 Error icon not displaying correctly on registration form example
+ EXTJSIV-12075 Layout browser example scrollbar not working on details panel
+ EXTJSIV-12087 Title Update Error in Reconfigure Grid example
+ EXTJSIV-12088 Clicking the RTL button on the examples' theme picker seems to crash the page
+ EXTJSIV-12102 Closing the theme/ RTL switcher in Examples leaves behind its shadow
+ EXTJSIV-12106 Some text gets clipped in the multisort dataview example on tablets
+ EXTJSIV-12112 5.x Resizable Examples page styling is off
+ EXTJSIV-12123 Scroll not working on 'Custom Drag and Drop' example
+ EXTJSIV-12136 State example has clipped text on tablets
+ EXTJSIV-12150 Feed Viewer - Can not disable summary View
+ EXTJSIV-12151 Events do not render in Calendar example
+ EXTJSIV-12152 Incorrect Calendar example display
+ EXTJSIV-12153 Portal example overlapping problem
+ EXTJSIV-12209 Feed viewer - Tab scroller issue
+ EXTJSIV-12230 Can't add feed by URL on MVC Feed Viewer example
+ EXTJSIV-12238 Advanced DataView example filter bar error
+ EXTJSIV-12302 Calendar Example IE10,IE11 issues
+ EXTJSIV-12303 Calendar Example drag events issue
+ EXTJSIV-12316 Can't edit form label on 'Editor' example
+ EXTJSIV-12349 Multiple Language example cannot load
+ EXTJSIV-12407 Simple-Tasks example fails to load
+ EXTJSIV-12458 Simple Task Example cannot save the task or new item
+ EXTJSIV-12463 Remote Summary grid example fails to load
+ EXTJSIV-12471 Custom form example not loading
+ EXTJSIV-12521 Live Search Grid Example looks cut 
+ EXTJSIV-12539 Ticket App example crashes
+ EXTJSIV-12547 Toolbar with Menus - Button with Menu does not show completely in Crisp theme
+ EXTJSIV-12617 Custom Layouts-> Abolsute Layout form looks cut
+ EXTJSIV-12654 Hard Deprecation of triggerField breaks 5 examples
+ EXTJSIV-12662 Examples ( DD / UX) call deprecated methods
+ EXTJSIV-12668 Vertical Slider does not  work - Slider Example
+ EXTJSIV-12674 Form Field Types Example fails to load
+ EXTJSIV-12685 File upload field button displaying incorrectly
+ EXTJSIV-12693 Kithcensink uses single quote in app.json
+ EXTJSIV-12701 Header Text is clipped - Drag/Drop Zones Example
+ EXTJSIV-12710 Rest Proxy Example puts incorrect id after add new row, id should be number type
+ EXTJSIV-12716 Feed Viewer only loads the title of a post after adding a new Feed on iPad no content nor author is shown.
+ EXTJSIV-12717 Combination Example - Right-to-Left(RTL) is not loading, throws a console error on all browsers 
+ EXTJSIV-12721 Panel header w/ no title and wrong icon color 
+ EXTJSIV-12722 View tab looks like a button in Crisp and needs an improved tooltip
+ EXTJSIV-12734 Simple Task Example doesn't load
+ EXTJSIV-12744 Examples layout issue with IE11 on laptop/small screens
+ EXTJSIV-12754 Feed Viewer example tree listing items need more space in Neptune and Crisp
+ EXTJSIV-12791 Legacy Charts Kitchen Sink - Interative Dashboard - throws a console error on all browsers
+ EXTJSIV-12809 Search field in the KS example does not clear
+ EXTJSIV-12816 The fieldcontainer is Clipped - FieldContainer Example
+ EXTJSIV-12855 Adding a new group to user in Ticket App example removes all other groups
+ EXTJSIV-12856 Top of ticket display is clipped in Ticket App edit ticket
+ EXTJSIV-12859 Cannot double click to drill down on My Active Tickets in Ticket App
+ EXTJSIV-12884 Grid filter menu input field icons are not displayed
+ EXTJSIV-12885 Grid filter menu is shown as empty
+ EXTJSIV-12894 Uncaught RangeError: Maximum call stack size exceeded - Widget Grid - KS
+ EXTJSIV-12907 Grouped Grid example should be resized
+ EXTJSIV-12931 Ticket App fails to login - missing required classes

Forms (30)

+ EXTJSIV-10148 In iPad browser form fields don't focus or show virtual keyboard when tapped 
+ EXTJSIV-11932 Can't see age numberfield on 'Named Arguments' sample
+ EXTJSIV-12068 Form number 3 becomes unusable
+ EXTJSIV-12069 Text editors appear disabled
+ EXTJSIV-12071 Tooltip error message displays on the bottom of the screen
+ EXTJSIV-12137 File upload in form examples throws error
+ EXTJSIV-12140 The item selector doesn't display correctly
+ EXTJSIV-12263 Contact form. Tooltip icons not displaying
+ EXTJSIV-12355 Changes to record fields do not always trigger change event
+ EXTJSIV-12366 XML form example broken
+ EXTJSIV-12380 The textbox doesn't work in IE10 and IE11
+ EXTJSIV-12387 Date/Month Picker example looks cut
+ EXTJSIV-12473 Vbox form example scrolling issues
+ EXTJSIV-12500 KS- Login form: Wrong Field styling,  IE10/11 inputs Inoperable
+ EXTJSIV-12515 Typing into the textarea in Field Types example throws error on IE9
+ EXTJSIV-12606 Reimplement text field "size" config with deprecated warning
+ EXTJSIV-12608 FieldContainer calculates incorrect owner height when shrink wrapping
+ EXTJSIV-12609 "side" and "under" aligned form field errors do not lay out correctly when the field has labelAlign: 'top'
+ EXTJSIV-12610 TextArea is not sized correctly on IE8/9
+ EXTJSIV-12611 BoxSelect is sized incorrectly on initial layout
+ EXTJSIV-12612 Make sure labelWidth and labelPad behave in ways that are compatible with 4.x
+ EXTJSIV-12665 Contact Form Example does not layout correctly
+ EXTJSIV-12677 Kitchen sink- contact form looks cut, Message text box can't see completely
+ EXTJSIV-12680 Can not choose radiogroup in all examples on kitchen sink---Safari 
+ EXTJSIV-12681 Textarea does not display correctly - Absolute Layout with Forms Example 
+ EXTJSIV-12758 Radio button visual checked state only correct while the radio button has focus.
+ EXTJSIV-12808 Combo does not publish initial empty value
+ EXTJSIV-12818 Kitchen sink\ CheckOut form is completely cut 
+ EXTJSIV-12848 TimeWorked is not working in Field container example, can not choose+/- buttons to add hours and mins
+ EXTJSIV-12956 Sliders do not update their bound values

Grid (52)

+ EXTJSIV-11936 After I move a column, I cannot move another
+ EXTJSIV-12015 In theme Crisp the table size is very small, cannot be visualized
+ EXTJSIV-12017 Drag and Drop fails on all grids and Trees in IE10/11
+ EXTJSIV-12022 Can't use columns down arrow options for sorting/locking/unlocking 
+ EXTJSIV-12025 KS - Cell editing example fails to load grid
+ EXTJSIV-12028 The menu of the column only is visible in the last column(Android)
+ EXTJSIV-12035 KS - Row Expander example fails to expand rows
+ EXTJSIV-12046 Select all checkbox not working on touch devices
+ EXTJSIV-12055 Cell editing example doesn't load correctly
+ EXTJSIV-12128 Locking Grid display issues 
+ EXTJSIV-12228 The border of the tooltip in the Sliding Pager example stay in all the kitchen sink
+ EXTJSIV-12295 The menu of the grids doesn't work in iOs 7.0.4
+ EXTJSIV-12296 The example of infinite scroll stops the scrolling
+ EXTJSIV-12307 Grouping/summaries broken
+ EXTJSIV-12312 Drag-and-drop target DOM element is incorrect in IE10/11
+ EXTJSIV-12314 Hospital drag and drop fails on IE10/11
+ EXTJSIV-12330 Can't sort property grid on 'Complex Layout' example
+ EXTJSIV-12351 Property grid cell editing is canceled wrongly in certain situations
+ EXTJSIV-12368 paging grid example & Infinite Scrolling with remote filtering examples broken
+ EXTJSIV-12369 Row editing grid example unable to add employee
+ EXTJSIV-12370 Buffered Grid example - jump to row not working
+ EXTJSIV-12371 Locking Group Grid with Summary fails to load
+ EXTJSIV-12396 Browser State Management example doesn't remember sort state of the grid
+ EXTJSIV-12399 The menu of the grids is displayed when you click for resize- IE10 IE11
+ EXTJSIV-12429 Editable big data Grid crashes Kitchen Sink when using filters
+ EXTJSIV-12459 Custom Grid Filters Example not loading
+ EXTJSIV-12460 Summary grid example summary broken
+ EXTJSIV-12461 Infinite scroll grid example fails to load
+ EXTJSIV-12464 Locking, Group Summary Grid Example fails to load
+ EXTJSIV-12478 sort_desc.gif and sort_asc.gif not found on Multiple grid sorting example
+ EXTJSIV-12522 Kitchen Sink  - Stock Ticker - Grid starts flashing when attempting to sort columns
+ EXTJSIV-12524 Kitchen Sink - Widget Grid - Slider Column does not sort 
+ EXTJSIV-12532 Multiple sort Grid sorts incorrectly when clicking the tab to sort
+ EXTJSIV-12603 Grid Plugins Example - error when expanding rows
+ EXTJSIV-12622 Fields don't stretch to cell size using cell editing.
+ EXTJSIV-12655 Grouping Feature does not react properly to moving of record from one group to another.
+ EXTJSIV-12663 Kitchen sink crashes after clicking the Sliding pager example  - TypeError: 'undefined' is not an object (evaluating 'h.inputContext.getPaddingInfo')
+ EXTJSIV-12731  has no method 'getPageX'  - Multiple grid sorting example
+ EXTJSIV-12762 Scrolling to a certain row in a grid does not sync the touch scroller
+ EXTJSIV-12764 Widget grid example throws JS error
+ EXTJSIV-12775 Hiding grid preview leaves touch scroller in incorrect state
+ EXTJSIV-12782 Dragging slider in widget grid does not update the other widgets.
+ EXTJSIV-12783 Grid paging example throws error
+ EXTJSIV-12794 Cannot call method 'getStyle' of null - Infinite Scrolling with remote filtering
+ EXTJSIV-12810 TypeError: 'undefined' is not a function (evaluating 'h.apply(a||Ext.global,b)') after placing the mouse's pointer over the graph on Rating column in KitchenSink/Grid/BigData 
+ EXTJSIV-12811 Status of 404 (Not Found) after try to edit a row in KitchenSink/Grid/BigData
+ EXTJSIV-12872 TypeError: 'undefined' is not an object (evaluating 'operation.records[0]') after delete a row in Rest Proxy Example
+ EXTJSIV-12877 Widget grid causes flicker on iPad when slider dragged and other columns updated.
+ EXTJSIV-12912 The "Show in groups" menu option injected by the Grouping Feature is not working.
+ EXTJSIV-12922 On Win8 (touchscroll AND scrollbars), the buffered rendering scroll area stretcher is not sized.
+ EXTJSIV-12957 KS Big Data Example Crashes Kitchen SInk
+ EXTJSIV-8917 RowEditor does not position properly in RTL

Layouts (9)

+ EXTJSIV-12395 The regions do not fit well in layout border example
+ EXTJSIV-12416 VBox layout fails when used with viewport
+ EXTJSIV-12445 Layout browser example won't load due to missing file
+ EXTJSIV-12467 Center layout is generating layout failures in Layout browser example
+ EXTJSIV-12541 Custom Layouts-> Center Example not working
+ EXTJSIV-12761 Toolbar overflow example, toolbar disappearing when resizing or selecting checkbox 
+ EXTJSIV-12777 HtmlEditor with overflowing menu items fails to layout successfully after initial layout
+ EXTJSIV-12867 Form layout with shrinkwrap width expands to infinity
+ EXTJSIV-7497 Form layout with shrink-wrapping in either dimension produces a layout failure

Locale (2)

+ EXTJSIV-12597 Fix Latvian language locale
+ EXTJSIV-12733 Multi Lang example does not change language, components are always in english

MVC (5)

+ EXTJSIV-10482 Action in route has action argument
+ EXTJSIV-12413 Keyboard Navigation example looks bad in Opera19
+ EXTJSIV-12446 HasMany.js and BelongsTo.js not found on Nested Loading example
+ EXTJSIV-12529 Data binding not working in sencha generated app w Cmd v5.0.0.71
+ EXTJSIV-5006 suspendEvents did not affect to Ext.app.Controller.control

Menu (3)

+ EXTJSIV-11948 Scrolling menu doesn't work on browsers other than Chrome
+ EXTJSIV-12005 Can't see whole menu in 'Toolbar with Menus' sample
+ EXTJSIV-12317 toolbar with menus - Some components fail to load

Misc (1)

+ EXTJSIV-5258 Documented config allowContainerDrops is not implemented

Panel (2)

+ EXTJSIV-10256 On iPad browser, Accordion flickers after each collapse/expand
+ EXTJSIV-12289 Portal Example unable to move windows

Selection Model (1)

+ EXTJSIV-12883 Grid selection binding is not updated when selected record is removed

Tabs (2)

+ EXTJSIV-12293 Tab fonts in Crisp theme look bold on IE9
+ EXTJSIV-12845 Tab Panel renders/activates children during removeAll

Theme (2)

+ EXTJSIV-12763 Close icons difficult to see in Crisp theme
+ EXTJSIV-12939 HtmlEditor "right align" and "center align" button icons are switched round in the toolbar and menu.

ToolTips (3)

+ EXTJSIV-12108 Tooltips do not vanish
+ EXTJSIV-12250 The description of the elements doesn't show in tree reorder Example
+ EXTJSIV-12819 Tooltips do not display in any validation form 

Toolbars (1)

+ EXTJSIV-12060 Vertical Toolbar Example fails to load

Tree (18)

+ EXTJSIV-10569 KS - Tree Reorder and other Tree examples not fully displayed 
+ EXTJSIV-10814 NodeInterface.appendChild() should NOT update the view for every new child node.
+ EXTJSIV-11810 Tree filtering leaves connector lines wrong.
+ EXTJSIV-12117 Can't drop 'Child' nodes
+ EXTJSIV-12139 KS - Heterogeneous Tree doesn't add items in correct order
+ EXTJSIV-12236 TreeModel's internal fields not being converted when raw data is string
+ EXTJSIV-12374 Tree column sort fails with infinite recursion
+ EXTJSIV-12403 Unable to drag and drop nodes
+ EXTJSIV-12405 Locking buffered rendered tree grid performance/view Issue
+ EXTJSIV-12406 KS - Basic Trees example breaks all other Tree examples
+ EXTJSIV-12432 treegrid.json not found on Tree Grid example
+ EXTJSIV-12433 check-nodes.json not found on Check Tree example
+ EXTJSIV-12436 Add Region button not working in Heterogeneous Tree example
+ EXTJSIV-12499 BufferedRenderer gets out of sync when removing large numbers of records in the rendered range
+ EXTJSIV-12508 Kitchen sink- Tree grid crashes when try to edit 
+ EXTJSIV-12526 Kitchen Sink - Tree Reorder - The Tree disappear when pressing Collapse All on iPad
+ EXTJSIV-12534 Kitchen Sink Example - Two Tree, cant move folder
+ EXTJSIV-12815 Kitchen sink crashes when sorting by user in Filtered tree example, TypeError: 'undefined' is not an object (evaluating 'v.parentNode')

Window (2)

+ EXTJSIV-12802 Windows are shifted when the browser is resized.
+ EXTJSIV-12918 Layout window Example, panel separator/resizer not rendering.

#Release Notes for Ext JS 4.2.2

Release Date: September 18, 2013

Version Number: 4.2.2.1144

##New Features

Charts (1)

+ EXTJSIV-8991 Pie charts should support callouts

Grid (2)

+ EXTJSIV-3316 Ext.ux.grid.FiltersFeature should support statefulness
+ EXTJSIV-3940 Grouping Feature should support statefulness

Total: 3

##Bugs Fixed

Button (2)

+ EXTJSIV-10376 Cannot navigate to a link button's url by clicking in IE
+ EXTJSIV-9827 SplitButton doesn't support href functionality

Charts (9)

+ EXTJSIV-10355 Tooltip on a chart series: showDelay doesn't work
+ EXTJSIV-10879 Chart labels misaligned when hiding series with stacked bar chart
+ EXTJSIV-6740 Line chart does not draw properly when repeated categories are present
+ EXTJSIV-8147 Chart mask doesn't appear
+ EXTJSIV-8169 Charts: labels incorrectly aligned with rtl:true
+ EXTJSIV-8442 Chart legend colors overlap text in RTL mode
+ EXTJSIV-8531 Bar and Column series with configured width/height place bars/columns incorrectly
+ EXTJSIV-9517 Zoom mask is not positioned correctly on line charts
+ EXTJSIV-9742 Time Axis incorrectly maps months

Core (6)

+ EXTJSIV-10103 ScrollManager does not process all direction flags properly
+ EXTJSIV-10106 Component Query no longer trims spaces in attribute matching expressions
+ EXTJSIV-10401 Overrides do not properly link up to inherited methods
+ EXTJSIV-8122 "Permission Denied" when trying to access an XPCNativeWrapped object from unprivileged code
+ EXTJSIV-9934 Calling setPosition() on a component with animations turned on does not set the correct left and top position
+ EXTJSIV-9995 DelayedTask.delay - can't accept 0 delay

Data (4)

+ EXTJSIV-10271 Sorting without the optional parameter clears the data from a buffered store
+ EXTJSIV-4576 Send only the idProperty on calls for destroying a record
+ EXTJSIV-8693 No metachange event firing for stores configured via setProxy()
+ EXTJSIV-9973 HasMany association with no id on parent removes all associated records

DataView (1)

+ EXTJSIV-10249 Mouse enter/leave processing for view items can reference wrong view

Documentation (7)

+ EXTJSIV-10051 Component weight should be a public config
+ EXTJSIV-10937 Ext.EventObject.getTarget()'s maxDepth can be set to 1 to test the first element
+ EXTJSIV-11273 Ext.tip.Tip maxWidth - docs wrongly say that the max supported width is 500
+ EXTJSIV-9726 chart series does not fire itemmousemove event
+ EXTJSIV-9836 ColorPicker menu button example in docs has broken style
+ EXTJSIV-9841 Documentation for calculateCategoryCount and categoryNames configs on Category axis
+ EXTJSIV-9899 Using tab to forward between cell editing with RowBody present causes focus to jump

Draw (1)

+ EXTJSIV-9540 Draw: adding a sprite to a surface isn't shown

Examples (4)

+ EXTJSIV-10612 ExtJS 4.2 examples fail to load properly in Windows 8.1 Preview release/ IE11
+ EXTJSIV-10831 Tree Reorder example scrolls down but not up, when dragging
+ EXTJSIV-9664 Combobox picker does not display when clicking on the trigger in Opera
+ EXTJSIV-9684 Loadmask styling is incorrect

Forms (22)

+ EXTJSIV-10302 Long boxLabels start a new line instead of floating
+ EXTJSIV-10354 Combobox is not auto selecting when queryMode is local
+ EXTJSIV-10744 submitValue:false ignored when jsonSubmit enabled on form
+ EXTJSIV-10805 Transform removes margin on bottom of combo
+ EXTJSIV-11050 Firefox left alignment is incorrect on label with absolute position
+ EXTJSIV-11179 Entering invalid value in Time Field causes JS error
+ EXTJSIV-11224 Forms: Dynamic Forms: The icons are overlapped with labels under "Overflow toolbar" button's drop down menu in form 3
+ EXTJSIV-11290 multiSelect: true comboboxes do not allow deselect on ENTER
+ EXTJSIV-6133 FieldSet with anchor fields causes incorrect scrolling
+ EXTJSIV-6685 ComboBox with multiSelect enabled clears last value on tab
+ EXTJSIV-7324 HtmlEditor: Placing the cursor after text that was broken with a br tag puts the cursor at the beginning of the text in FF
+ EXTJSIV-7556 Combo Box : Basic Combo Box:  Displaying  Horizontal scroll bars in combo Boxes.
+ EXTJSIV-7608 Calling setValue on a timefield doesn't format the display
+ EXTJSIV-8124 "Cancel" does not fire change event for file input field in Chrome
+ EXTJSIV-9608 Menu separator position is incorrect in IE9 RTL mode
+ EXTJSIV-9703 Combo with multi-select not setting last value when tab to blur
+ EXTJSIV-9789 Uncontrollable flicker between textfields that have selectOnFocus
+ EXTJSIV-9792 setValue in htmleditor does not fire change event properly
+ EXTJSIV-9895 Tooltip text escapes the border in RTL mode
+ EXTJSIV-9936 fileuploadfield marked as invalid on submit w/ pollForChanges set to true
+ EXTJSIV-9969 'value' config does not work for Ext.form.field.Checkbox
+ EXTJSIV-9974 Ext.picker.Month bottom cut off

Grid (66)

+ EXTJSIV-10022 Grouping Feature - calling reconfigure isn't calling the correct GroupStore bindStore() API
+ EXTJSIV-10026 Exception when editing a cell of previously hidden column
+ EXTJSIV-10027 Collapsing grouping row causes subsequent row to be unselectable
+ EXTJSIV-10055 Auto-sizing doesn't recalculate column widths in a forceFit grid
+ EXTJSIV-10063 Editors canceledit event doesn't return the canceled value
+ EXTJSIV-10089 grouped header grid - wrong column width
+ EXTJSIV-10125 Extending RowNumberer does not inherit as expected
+ EXTJSIV-10130 Inserting record does not behave correctly
+ EXTJSIV-10137 Row style is not correct when expanding rows in a tree grid
+ EXTJSIV-10171 Collapsing group on summary grid does not allow selection
+ EXTJSIV-10177 RowEditor does not show column if it was hidden in config
+ EXTJSIV-10226 Problem when scrolling at the bottom of a grid with buffered store
+ EXTJSIV-10228 Dynamically setting a column editor (calling setEditor) does not work with the RowEditing plugin
+ EXTJSIV-10245 Grid with cell/row Editor in IE 8,9,10
+ EXTJSIV-10262 Hidden columns in stateful grids are out-of-sync with the view when shown
+ EXTJSIV-10316 Grid doesn't scroll when dragging records
+ EXTJSIV-10352 column.getHeaderIndex() is broken
+ EXTJSIV-10361 Store defined groupDir state is not maintained when you disable and then enable grouping
+ EXTJSIV-10374 Grouped headers aren't filtering out hidden sub columns when moving
+ EXTJSIV-10396 Grid view (scroll bar) jumps to beginning when selecting row.
+ EXTJSIV-10506 Hiding column group doesn't hide grouped columns
+ EXTJSIV-10548 If grid is configured with Checkbox selection model, rowexpander's colspan is incorrect
+ EXTJSIV-10570 Initially selected rows are not rendered with selected classes added.
+ EXTJSIV-10571 Records display is lost when scrolling buffered grid
+ EXTJSIV-10681 Grid panel with hidden column group does not render properly
+ EXTJSIV-10686 HeaderContainer subtracts scrollbarWidth from container width even when overflow-y is hidden
+ EXTJSIV-10688 Cell selection model errors out on store.removeAll()
+ EXTJSIV-10722 Locking grid should not shrinkwrap column widths if horizontal scroll enabled.
+ EXTJSIV-10724 Buffered stores only handle priming at page 1
+ EXTJSIV-10813 Expand / Collapsing of groups make them disappear
+ EXTJSIV-10847 Tab key navigation is not working when grid cells are in editable mode
+ EXTJSIV-10850 Cell editing and tabbing breaks if there is a hidden column
+ EXTJSIV-10851 Grid cell click return incorrect colIndex if there is hidden column
+ EXTJSIV-10861 Mouseover events not working on grouping grids with buffered stores.
+ EXTJSIV-10869 Kitchen Sink: Grids: Grouped Grid: Expanding any group under the grid displays JS error
+ EXTJSIV-10871 Cell editor is misaligned if underlying cell is empty or contains only spaces
+ EXTJSIV-10888 grid column missing dividing line after DnD
+ EXTJSIV-10953 columnManager.getColumns() does not include hidden columns
+ EXTJSIV-10955 group header column showing when all sub-columns are hidden
+ EXTJSIV-10993 GroupingSummary feature attempts to update last row in group event when showSummary is false.
+ EXTJSIV-11032 Incorrect column widths in grid when using both rowwrap and bufferedrenderer
+ EXTJSIV-11079 Checkboxmodel does not multi-select on checkbox selection
+ EXTJSIV-11121 RowEditor can't be "Canceled" if row is invalid and enter is pressed
+ EXTJSIV-11243 Columns with no dataIndex should not display "Group by this" menu item
+ EXTJSIV-11252 Scroll position jumps to selected grid row when a group is expanded or collapsed
+ EXTJSIV-11281 Grid row focus/selected borders do not get properly synced in some cases
+ EXTJSIV-7694 When using RowExpander and RowNumberer, RowNumberer is not getting proper CSS on expand
+ EXTJSIV-7866 RowExpander plugin broken if subclassing Grid
+ EXTJSIV-8967 Buffered Renderer reconfigure,loadData functions not working properly
+ EXTJSIV-8975 GridPanel+ IE: scrollbar jumps to beginning on select in unlocked area
+ EXTJSIV-9061 BufferedRenderer.scrollTo throws an error when called on a grouped grid.
+ EXTJSIV-9096 FiltersFeature DateFilter initiates request on picker click without filter
+ EXTJSIV-9130 Bufferedrenderer can lose track of scroll position if user scrolls grid rapidly
+ EXTJSIV-9204 Horizontal scrollbar missing on grid with no height
+ EXTJSIV-9219 Row editor's "Update" and "Cancel" left aligned under row editor in IE 6 and do not respond to click
+ EXTJSIV-9297 CheckboxModel: editor.startEdit() shouldn't be called when checkbox is clicked 
+ EXTJSIV-9396 Row editor does not display in IE6/7 in some cases
+ EXTJSIV-9426 Ellipsis no longer appear in grid column header when column title is long
+ EXTJSIV-9482 First row of a locking grid dos not correctly align with the column headers
+ EXTJSIV-9496 Grid groups are not collapsible after hiding a column
+ EXTJSIV-9499 column headers flicker when hovered in RTL Mode.
+ EXTJSIV-9605 Shrinkwrap column header displays an incomplete border
+ EXTJSIV-9874 Grid group header should not have focus outline when clicked
+ EXTJSIV-9878 Cannot use the Tab key to move the cell editor in IE when the grid only has one column
+ EXTJSIV-9957 Ext.grid.RowEditor doesn't disabled form buttons based on invalid status
+ EXTJSIV-9991 Grid with Infinite Scrolling - Reload Function

Layouts (4)

+ EXTJSIV-10678 Accordion layout calls wrongly named onComponentExpand method
+ EXTJSIV-10859 Window with vbox layout: First setHeight() collapses width.
+ EXTJSIV-11034 ExtJs 4.2.1: HtmlEditor always overflow its parent container
+ EXTJSIV-9885 Issue when removing expanded item for accordion layout

Locale (1)

+ EXTJSIV-10276 Locales use non-existent classname to override Ext.grid.feature.Grouping

Menu (1)

+ EXTJSIV-9920 Default scope of menu CheckItem checkHandler should be CheckItem

Misc (17)

+ EXTJSIV-10309 Destroying a record when represented in a view generates an error: Uncaught TypeError: Cannot read property 'className' of undefined 
+ EXTJSIV-10530 Cannot get filefield value from the Form on submit
+ EXTJSIV-10560 DatePicker does not respect the padding config
+ EXTJSIV-10726 Mask does not cover full height when browser is scrollable
+ EXTJSIV-10911 startEditByPosition triggers error with hidden columns
+ EXTJSIV-11155 Ext.Editor overrides the field's msgTarget
+ EXTJSIV-5647 Filtered out records are missing from new and modified collection to sync.
+ EXTJSIV-7499 Boundlist bug with long display value(s) in IE9
+ EXTJSIV-8119 Remove redundant show/hide calls in Ext.Layer constructor
+ EXTJSIV-9165 NodeInterface.updateInfo doesn't set the 'modified' properties
+ EXTJSIV-9263 columnLines: true applies columnLines to any grids that are docked onto that grid
+ EXTJSIV-9313 Datepicker is not navigable using the keyboard in opera 12
+ EXTJSIV-9533 TreeStore.load does not rerender an expanded node's children after a successful load.
+ EXTJSIV-9577 Calling non-existent method in Ext.data.Store
+ EXTJSIV-9695 Miscellaneous: History: The Border line of the sub tab bar under "Tab1" is truncated.
+ EXTJSIV-9765 Ext.data.Store.rejectChanges
+ EXTJSIV-9801 Anchor tags should have proper Aria role specified

Panel (3)

+ EXTJSIV-10546 Accordion layout stops responding when expanding/collapsing in some cases
+ EXTJSIV-11166 Removing a component under a collapsed panel throws setStyle error
+ EXTJSIV-9917 Constraining Window inside Panel not working if animateTarget is in use

Performance (1)

+ EXTJSIV-7488 Menu item activation/deactivation very CPU intensive on IE9

Selection Model (2)

+ EXTJSIV-9118 De-selecting from MultiSelect w/selection mode: "single" throws exception
+ EXTJSIV-9138 Unable to reload buffered grid when rows are selected

Tabs (2)

+ EXTJSIV-10909 Tab's default closeText is overridden incorrectly
+ EXTJSIV-9350 Cannot close tabs using the close icon in opera 11

Theme (6)

+ EXTJSIV-10033 Neptune's grid header trigger images are not referenced correctly using theme-background-image()
+ EXTJSIV-11082 The $include-ie sass variable doesn't properly exclude all IE-specific rules when set to "false"
+ EXTJSIV-11119 CSS precedence for button's "focus" and "over" states is incorrect, "over" should take precedence over "focus"
+ EXTJSIV-9723 Add support for linear-gradient in IE10
+ EXTJSIV-9888 ellipsis is displayed in the header when using a rowexpander column
+ EXTJSIV-9970 Neptune tool spritesheet inconsistencies

ToolTips (2)

+ EXTJSIV-10833 Qtip doesn't stretch to fit its title
+ EXTJSIV-9901 Tooltip text is cut off in Firefox on Mac OS

Toolbars (2)

+ EXTJSIV-10623 Checkboxes do not retain state in overflow menu
+ EXTJSIV-9588 Keyboard navigation no longer works with toolbar buttons

Tree (6)

+ EXTJSIV-10270 Tree node drag scrolls in wrong direction
+ EXTJSIV-11284 Multi-select drag/drop tree allows multiple nodes to be dragged simultaneously
+ EXTJSIV-6080 Cell editor sometimes not hidden when external mousedown is on a DragZone
+ EXTJSIV-8237 Tree: non-leaf nodes aren't given proper styles and functionality when id or children isn't set
+ EXTJSIV-9544 Tree events are not being relayed through the TreeStore
+ EXTJSIV-9867 Tree expansion. Repeating right arrow key during animated node expand blurs tree.

Window (7)

+ EXTJSIV-10107 Window's drag proxy is not shown with the correct z-index in some cases
+ EXTJSIV-10566 Closing a panel with draggable:false incorrectly assumes it has a DragSource
+ EXTJSIV-5957 Window stays in front of modal Messagebox
+ EXTJSIV-6229 zIndexManager.bringToFront() called multiple times
+ EXTJSIV-9018 Window header ghost does not mirror actual header during drag
+ EXTJSIV-9704 window resize event stops firing after restore
+ EXTJSIV-9984 MessageBox Icon alignment incorrect in RTL

Total: 176

#Release Notes for Ext JS 4.2.1

Release Date: May 16, 2013

Version Number: 4.2.1.883

##General

The final release of Ext JS 4.2.1 contains numerous fixes and small
enhancements requested by customers and the community. While the
details are below, there are several items worth calling out.

###New Big Data Example

The new Big Data example shows off all of the major grid features
and plugins working together in a single grid. It also shows off a
text field in a grid column header! Head over and check it out!

###Sencha Cmd 3.1.2

To coincide with this release, Sencha Cmd 3.1.2 is also now available.
The primary change with regards to Cmd is that the packages produced
by Ext JS now stay inside the "ext" folder when you generate a new
application or workspace. The "ext-*" packages previous saved to your
"packages" folder can be removed. For details see the
release notes
for Sencha Cmd 3.1.2. If you are using Sencha Cmd, it is
recommended that you upgrade to the new version.

###Locale Package Consolidation

In Ext JS 4.2.0 we migrated the locale files in to Sencha Cmd packages
to facilitate switching between locales. The downside is that this
produced a lot of small packages that needed to be required in your
"app.json" (or used as pure JS files). As an enhancement to
this process in Ext JS 4.2.1 we have consolidated all of the locales
into the ext-locale package. The legacy file paths are still
preserved, but if you are using locale packages, you can now just do
this in your "app.json" file:
    
    "requires": [
    'ext-locale'
    ]

You will still need to set app.locale to pick up the proper
locale overrides. They are just all located in the one package in
this release.

##New Features

Core (1)

+ EXTJSIV-8123 Enhance Ext.util.Format.fileSize to calculate gigabytes (GB)

Layouts (1)

+ EXTJSIV-9509 A splitter's collapseOnDblClick cannot be disabled via the object's config

Locale (1)

+ EXTJSIV-9653 Locales should be consolidated to a single ext-locale package instead of requiring each locale independently

Misc (1)

+ EXTJSIV-9389 Add SASS variables that can be used to prevent "default" UIs from being generated.

Total: 4

##Bugs Fixed

Button (3)

+ EXTJSIV-9323 Focus is not set on buttons in IE
+ EXTJSIV-9658 Button layout fails when button component height is too small
+ EXTJSIV-9864 Disabled buttons can still receive focus using TAB

Charts (4)

+ EXTJSIV-7235 Series label color is not applied and location is incorrect
+ EXTJSIV-9393 Series instance cannot be initialized properly
+ EXTJSIV-9422 Issues with custom font, padding, itemSpacing of chart legend box
+ EXTJSIV-9536 Stacked Column Chart with Missing Y Value has Incorrect Maximum

Core (10)

+ EXTJSIV-8286 Element.switchOff() and other animation methods do not call users callback on complete
+ EXTJSIV-8764 Element.on/un and Observable.un should accept function names as Observable.on does
+ EXTJSIV-9339 TextMetrics ignores container styles
+ EXTJSIV-9405 CSS reset style rule remains on the body that sets border box
+ EXTJSIV-9469 Ext.Date format creates global variables
+ EXTJSIV-9535 Ext.util.Format.number incorrect result with custom locale and value < 1000
+ EXTJSIV-9590 mouseoverItem in Ext.view.View
+ EXTJSIV-9604 Ext.clone needs hasOwnProperty check for IE browsers with enumerable bug
+ EXTJSIV-9630  Ext.destroy should support destroying stores
+ EXTJSIV-9689 Resizable: resize handles are always transparent

Data (6)

+ EXTJSIV-8977 PagingMemoryProxy's load mask is never removed
+ EXTJSIV-9326 The removeAll method does not completely clear a buffered store
+ EXTJSIV-9523 Changing id in filtered store skips snapshot
+ EXTJSIV-9550 Store removeAll doesn't clear snapshot
+ EXTJSIV-9811 Stores configured with autoDestroy: true may produce JavaScript errors in certain cases
+ EXTJSIV-9815 AbstractMixedCollection does not filter out records with duplicate id's when added in bulk

Direct (3)

+ EXTJSIV-7766 Timeout is ignored if form is submitted with DirectSubmit
+ EXTJSIV-9250 DirectLoad and DirectSubmit actions should resolve Direct methods on first call
+ EXTJSIV-9295 Direct PollProvider does not handle erroneous input properly

Documentation (7)

+ EXTJSIV-7521 Lockable mixin is not listed for Grid in the docs
+ EXTJSIV-8004 Documentation on #SenchaCmd for #ExtJS doesn't mention to use latest version of #SenchaSDK tools. Can easily get caught
+ EXTJSIV-8487 Ext.Component.afterRender marked as private
+ EXTJSIV-8488 Ext.dd.DragZone.destroy should be marked public
+ EXTJSIV-9294 Ext.ComponentQuery needs more documentation
+ EXTJSIV-9636 Ext.app.Application name should be documented as mandatory
+ EXTJSIV-9659 The Building Themes for ExtJS guide is empty

Draw (2)

+ EXTJSIV-9786 Drawing: Re sizable Sencha Logo: Displaying JS Error on Loading the example on IE9 Browser.
+ EXTJSIV-9795 Drawing : Browser Logos : Displaying JS error upon  closing the Draw component panel.

Events (1)

+ EXTJSIV-9261 Observable.observe does not capture events properly

Examples (2)

+ EXTJSIV-9654 Basic Templating example has incorrect XTemplate statement
+ EXTJSIV-9757 Combination Examples:  Web Desktop : Displaying JS error while selecting options from the menu.

Forms (17)

+ EXTJSIV-7355 numberfield's autoStripChars does not work on numbers with exponents such as "1e42"
+ EXTJSIV-7792 Forms scrolls in window in Chrome
+ EXTJSIV-8006 Combobox field value not correct on select event when leaving field using mouse click
+ EXTJSIV-8067 HtmlEditor - tabbing into editor field in Internet Explorer 9 throws error
+ EXTJSIV-8158 Triggerfield height can not be adjusted with setHeight()
+ EXTJSIV-8278 Background color does not follow growing text
+ EXTJSIV-8542 htmleditor places a "br" tag in the editor field after pressing the source edit button in firefox
+ EXTJSIV-9303 HtmlEditor throws JS error when selecting certain toolbar items with selected text on IE
+ EXTJSIV-9439 Loading large amount of data in the HtmlEditor locks up FF19 / FF20
+ EXTJSIV-9487 Default 'x-form-file-wrap' class not applied to filefield when form contains a fieldBodyCls in fieldDefaults
+ EXTJSIV-9501 HTMLEditor - setValue does not work when component is not rendered
+ EXTJSIV-9527 HtmlEditor causes form isDirty() to be true
+ EXTJSIV-9555 combineLabels does not work
+ EXTJSIV-9558 In tabbed panel, data doesn't load in HtmlEditor
+ EXTJSIV-9603 Combo is too slow when loading a large amount of items
+ EXTJSIV-9641 FieldSet fieldvaliditychange and fielderrorchange don't fire
+ EXTJSIV-9766 Double clicking on editor causes: NS_ERROR_INVALID_POINTER

Grid (44)

+ EXTJSIV-5245 Grid column lines are shown for hidden columns if RowExpander is used
+ EXTJSIV-5543 focus is lost on an active cell editor in an editable grid
+ EXTJSIV-6294 When tabbing quickly through cell editing, the cell editor drops out of edit mode (intermittent)
+ EXTJSIV-6734 Hidden grid column's height is not properly measured when wordwrap is used
+ EXTJSIV-7331 HeaderContainer defaults doesn't work if there is a column with locked: true
+ EXTJSIV-7437 GridFilters feature doesn't work for unlocked columns
+ EXTJSIV-7855 Setting a value in a grid removes focus from textfield
+ EXTJSIV-8795 Grids lose horizontal scroll position on row focus in IE
+ EXTJSIV-8910 Grid filters aren't taking a lockingPartner into account when filtering
+ EXTJSIV-9001 VERY slow tree grid on second load with bufferedrenderer plugin
+ EXTJSIV-9095 blur() not firing when pressing tab to leave datefield grid cell editor
+ EXTJSIV-9130 Bufferedrenderer can lose track of scroll position if user scrolls grid rapidly
+ EXTJSIV-9139 Buffered renderer crashes when modifying store before rendered
+ EXTJSIV-9262 drag/drop plugins cause grid focus and scrollbar reset with prevent focus
+ EXTJSIV-9367 Cell beforeedit event is fired twice when clicking on an editable cell
+ EXTJSIV-9376 Grid RowExpander does not work with locking enabled
+ EXTJSIV-9379 Grid performance with many columns and editing
+ EXTJSIV-9380 Grid column lines not synced with header in locked+grouped sample
+ EXTJSIV-9382 Load mask disappears too soon when buffered store loads pages.
+ EXTJSIV-9385 Tab key not working on grid cell edit with group feature, but ungrouped store
+ EXTJSIV-9390 GridPanel reconfigure does not refresh the data on reconfigure if there's a buffered renderer plugin.
+ EXTJSIV-9397 Grids: Infinite Grid: Vertical scroll bar size increases after sorting any columns
+ EXTJSIV-9402 forceFit calculations being applied too late upon reconfigure.
+ EXTJSIV-9406 Grid not displaying emptyText when container layout 'auto'
+ EXTJSIV-9411 Meta config example throws errors on mouseover after reloading metadata
+ EXTJSIV-9426 Ellipsis no longer appear in grid column header when column title is long
+ EXTJSIV-9438 Nested column headers do not get the correct height when using white-space:normal
+ EXTJSIV-9453 Resizing last column of grid throws error
+ EXTJSIV-9454 Hiding a wide column in a crowded forceFit grid can shrink the column upon show.
+ EXTJSIV-9457 Auto align feature on column divider incorrect in IE in some cases
+ EXTJSIV-9475 Kitchen Sink: Grids: Big Data: Emptying cell data under 'Name' column and then clicking on 'Update' button under row editor displays JS  error
+ EXTJSIV-9476 Kitchen Sink: Grids: Big Data: Drag and drop 'Notice Period' column into locked area displays JS error
+ EXTJSIV-9532 Column widths go wrong with hidden column and forcefit true
+ EXTJSIV-9562 Grid summary columns not resizing/behaving same as regular grid columns
+ EXTJSIV-9595 Kitchen Sink: Big Data: Locking the 'Absences' group displays JS error
+ EXTJSIV-9637 Row Grouping Grid with locked column presents incorrect row alignment with large datasets
+ EXTJSIV-9662 Combination Examples: Kitchen Sink: Grouped Grid: Expanding a group for second time displays JS error
+ EXTJSIV-9691 RowEditor should flip its buttons to the top when there is not room to scroll them into view.
+ EXTJSIV-9756 Combination Examples: Kitchen sink: Drag and Drop: Grid to form: The swapping and the Drag and Drop Functionality is not working on IE10 Browser.
+ EXTJSIV-9804 Grid doesn't check hidden state in hide/show
+ EXTJSIV-9805 Column events not fired correctly
+ EXTJSIV-9819 collapseAll() and expandAll() create circular logic that locks up the browser when a grid is grouped and locked
+ EXTJSIV-9851 Grouping doubles up on expand / collapse when buffer rendered and data fits within view height.
+ EXTJSIV-9860 Kitchen sink: Big Data: Collapsing a group displays JS error

Layouts (6)

+ EXTJSIV-7407 Adding a collapsed region to a border layout throws an error
+ EXTJSIV-8000 Borders problem with collapsible and 'mini' collapseMode within border layout
+ EXTJSIV-9272 Anchor and Column layouts have unnecessary gap for scrolling
+ EXTJSIV-9305 Anchor layout does not exclude scrollbar width when the autoScroll=true and anchor=100%
+ EXTJSIV-9401 In some cases constraints like minHeight can cause layout failures
+ EXTJSIV-9714 Layout Managers: Complex Layout: The field is void in editable mode when switched using "Tab" key in keyboard.

Locale (3)

+ EXTJSIV-7179 Missing translation for TextField blankText config in cs locale
+ EXTJSIV-7426 Locale override remains in German Locale file and comments state they should be removed for 4.1.x
+ EXTJSIV-9580 Polish translation targets msg property of AbstractView for localized text but should be loadingText

MVC (1)

+ EXTJSIV-9486 Application inheritance does not work properly

Menu (1)

+ EXTJSIV-9296 Menu with floating false is not positioned properly in right aligned HTML

Misc (3)

+ EXTJSIV-8419 MessageBox does not respect construction-time configs vs those passed to each show call
+ EXTJSIV-9391 LTR scrolling is not handled correctly when RTL overrides are included
+ EXTJSIV-9877 RowNumberer column header shows ellipsis in IE8

Panel (1)

+ EXTJSIV-9823 the *-{ui} class is not being added to the header of a panel

Selection Model (3)

+ EXTJSIV-9003 Grid selection range doesn't select correctly
+ EXTJSIV-9288 Row selection model does not handle vetoed mousedown events
+ EXTJSIV-9357 No way to restrict method of deselection in single selection model to ctrl+click as it was in previous versions

Tabs (2)

+ EXTJSIV-7337 Nested tab panels don't maintain constraint or masking with windows
+ EXTJSIV-9625 Side tabs throw exception if tabs are hidden initially.

Theme (4)

+ EXTJSIV-8453 Tree lines have 1px gaps in Neptune theme
+ EXTJSIV-8749 Neptune - Create color variables for Global Error (red) and Confirmation (green)
+ EXTJSIV-9423 Accessibility theme needs tool icons for window move and resize
+ EXTJSIV-9824 There is no variable to control the base path of resources used in the CSS output

ToolTips (2)

+ EXTJSIV-8824 Tooltip cuts off content on Chrome
+ EXTJSIV-8935 Tooltips aligning using left origin when in RTL mode

Tree (8)

+ EXTJSIV-8327 Ext.tree.Panel ignores value of Ext.enableFx
+ EXTJSIV-9229 remote tree node expand not take proxy.extraParams set at beforeexpand
+ EXTJSIV-9414 Dropping to tree from grid causes JavaScript error due to nodeHighlightOnDrop
+ EXTJSIV-9462 Tree node arrow in IE10 do not show expand state properly
+ EXTJSIV-9511 beforeitemsexpand should fire before beforeload
+ EXTJSIV-9515 expandAll's callback is called for the last node in every descendant non-leaf
+ EXTJSIV-9798 Trees : Locking Tree Grid: Unable to check or uncheck the check boxes under "Done" column when any of the columns are hidden
+ EXTJSIV-9832 Combination exampes: Kitchen Sink: Trees: Two Trees: Unable to expand/collapse & move on the folder in the tree panel in a specific scenario.

Total: 133

#Release Notes for Ext JS 4.2.1 Beta 1

Release Date: April 10, 2013

Version Number: 4.2.1.744

##New Features

Core (2)

+ EXTJSIV-7969 There should be an easy way to reset a color picker
+ EXTJSIV-9019 constrainTo needs an option to restrict keep constrained item away from outer edges of the area

Examples (1)

+ EXTJSIV-9276 Add usage of RowExpander to KS BigData grid example.

Forms (1)

+ EXTJSIV-8947 ComboBox should have anyMatch and caseSensitive options

MVC (1)

+ EXTJSIV-9070 Controllers loaded from other controllers should be supported

Total: 5

##Bugs Fixed

Core (7)

+ EXTJSIV-8568 getPlugin fails if plugins is not declared as an array
+ EXTJSIV-9049 Date parse using "m/Y" format wraps "end of month" into "next month" depending on current date
+ EXTJSIV-9101 Box layout's menu overflow handler puts overflow menu at right in RTL mode. Should go on left.
+ EXTJSIV-9122 Capturing listeners aren't removed from DOM element in Ext.EventManager.removeListener()
+ EXTJSIV-9151 Ext.util.MixedCollection.sortByKey does not work
+ EXTJSIV-9240 Container insert and move methods do not respect component instances vs indexes
+ EXTJSIV-9342 Container does not recurse into floatingItems in getRefItems breaking ComponentQuery for floating descendants

Data (4)

+ EXTJSIV-9074 Combo does not respect autoLoad:false with remote filter
+ EXTJSIV-9176 Updating a record in grouped store, trigger remove action on the store's proxy
+ EXTJSIV-9184 Configuring a Store with groupField and getGroupString doesn't work.
+ EXTJSIV-9201 TreeStore setProxy method doesn't return the proxy object

Direct (1)

+ EXTJSIV-9333 Direct call doesn't work with buffering disabled in 4.2.0

Examples (2)

+ EXTJSIV-9226 Closing theme changer dialog breaks window resizing
+ EXTJSIV-9232 MVC:Feed Viewer: Adding new feed displays JS error

Forms (22)

+ EXTJSIV-7436 Fileupload button doesn't expand height to cover button in tall file field component
+ EXTJSIV-7764 Ext.form.Panel does not relay updateRecord from BasicForm
+ EXTJSIV-7836 Display field does not report proper height when text wraps and gets clipped or overlapped
+ EXTJSIV-7877 Calling setValue on textarea with a numeric value throws JS error
+ EXTJSIV-8250 Ext.slider.Multi setMinValue and setMaxValue don't fire change event
+ EXTJSIV-8784 FieldContainer invalidCls causes double error indicators
+ EXTJSIV-8950 Buttons blur themselves on invocation of their handlers making them and their ancestor hierarchy keyboard-inaccessible
+ EXTJSIV-8960 File field can overlap things if buttonOnly is true
+ EXTJSIV-9075 Destroying a combobox does not clean up the KeyNav
+ EXTJSIV-9100 RTL - form fields on a toolbar are misaligned in IE quirks
+ EXTJSIV-9168 Items are not always removed from form when destroyed
+ EXTJSIV-9169 Overflow menu trigger button is placed at right side of editor in RTL mode
+ EXTJSIV-9182 form.submit() with fileuploadfield does not trigger failure handler for HTTP errors
+ EXTJSIV-9185 Combobox with large fieldLabel can cause misplacement of picker
+ EXTJSIV-9237 Slider with increment configured adjusts the maxValue
+ EXTJSIV-9260 hiddenfield occupies the visile place in the form
+ EXTJSIV-9266 Combo trackOver:false does not disable overItemCls tracking
+ EXTJSIV-9274 File input element covers text field and steals clicks displaying file browser
+ EXTJSIV-9287 Basicform keeps reference of destroyed items
+ EXTJSIV-9335 Button of file field component does not render correctly in RTL mode
+ EXTJSIV-9344 Bug with FieldSet and grid cell editing plugin
+ EXTJSIV-9421 DateField doesn't show the picker inside collapsed region

Grid (11)

+ EXTJSIV-5922 Locking, grouping and buffered rendering do not work together.
+ EXTJSIV-6806 Grid locking and row editing do not work together
+ EXTJSIV-9077 Grid headers do not have proper gradient stretching when sliced for IE
+ EXTJSIV-9102 Mouseover row highlighting not working in wrapped rows.
+ EXTJSIV-9141 After ending cell editing with the Enter key, keyboard navigation no longer works.
+ EXTJSIV-9195 grid reconfigure without store throws JS error
+ EXTJSIV-9214 Grid cell edit with group feature not updating values
+ EXTJSIV-9224 RowExpander doesn't fire events on the proper grid view when locking
+ EXTJSIV-9251 on grid's record destroy, the selectionchange event is not fired
+ EXTJSIV-9253 Changing the group field value of a record in a grouped grid throws an error.
+ EXTJSIV-9268 Ext.grid.Panel allowDeselect config has no effect

Layouts (3)

+ EXTJSIV-8553 Text wraps/clips in IE10 (in tooltips for example) because Direct2D rounding bug is not properly detected
+ EXTJSIV-9116 Hightlight focus doesn't completely cover under overflow menu options
+ EXTJSIV-9234 Border layout does not apply child margins on reversed sides in RTL

Locale (1)

+ EXTJSIV-9340 Datepicker is not picking up localized text properly

MVC (1)

+ EXTJSIV-9105 In controller using views: 'Microsoft.view.MyView' generate many requests

Menu (2)

+ EXTJSIV-9099 Grouped menu check items display checkbox
+ EXTJSIV-9104 MenuManager's mousedown clickhandler doesn't always work on IE

Misc (1)

+ EXTJSIV-9143 Ext.isIterable returns true for MixedCollection

Panel (2)

+ EXTJSIV-8589 Panel ghost is not assigned the proper z-index in some cases
+ EXTJSIV-9330 Collapsed panels that need an additional Header do not propagate margins to that header

Selection Model (1)

+ EXTJSIV-8279 Error when trying to select a record while using CellModel

Theme (3)

+ EXTJSIV-3570 Ext JS 4 Themes - hardcoded variable colors
+ EXTJSIV-9103 ext-theme-neptune-all-rtl.css exceeds IE's maximum number of rules for a single stylesheet.
+ EXTJSIV-9160 Toggle buttons in toolbar have incorrect gradients in Gray theme

Window (2)

+ EXTJSIV-7262 Window constrain:true inside another window, restoring position problem
+ EXTJSIV-8291 Ext.Component: show() results in two layout runs if autoRender true

Total: 63

#Release Notes for Ext JS 4.2.0

Release Date: March 11, 2013

Version Number: 4.2.0.663

##New Features

Charts (1)

+ EXTJSIV-6723 Chart series label renderer should allow label style to be modified

Forms (1)

+ EXTJSIV-8674 Checkbox and RadioButton should have setBoxLabel method

Grid (1)

+ EXTJSIV-8904 RowEditorButtons goes to 100% width on IEQuirks

Locale (1)

+ EXTJSIV-8670 Locales should be Sencha Cmd packages of type = locale

Misc (1)

+ EXTJSIV-8701 Floating RTL Switcher In Examples

Total: 5

##Bugs Fixed

Button (2)

+ EXTJSIV-9026 Neptune disabled buttons do not have proper opacity in IE8 and older
+ EXTJSIV-9058 NEPTUNE: Miscellaneous: Buttons: The contents on the buttons are missing when they are disabled on IE

Charts (2)

+ EXTJSIV-8798 Setting up legend for chart throws JavaScript error
+ EXTJSIV-9009 Pie chart Labels do not display the correct values once slices are hidden

Core (2)

+ EXTJSIV-8659 Add ms prefix to Ext.supports.CSS3LinearGradient
+ EXTJSIV-8671 Kitchen sink demo doesn't show in FF

Data (1)

+ EXTJSIV-3547 Ext.data.TreeStore fires "update" event twice due to error in Model.

DataView (3)

+ EXTJSIV-8476 Animated dataview plugin failing to position correctly in RTL mode
+ EXTJSIV-8719 Mouseover buffer delay too large by default. Causes perceived lag.
+ EXTJSIV-8923 Intermittent errors when clicking/mouseovering views/grids which dynamically update.

Documentation (2)

+ EXTJSIV-8672 Using persistenceProperty breaks Grid
+ EXTJSIV-8746 Cell selection model does not support "multi" mode

Examples (9)

+ EXTJSIV-8690 Portal example header text color looks bad in neptune theme
+ EXTJSIV-8698 Desktop toolbar is too tall in RTL mode
+ EXTJSIV-8711 Feed Viewer: Adding the 'Sci/Tech' or 'Yahoo' feed displays the each news content in HTML format
+ EXTJSIV-8754 Cannot apply a template in neptune using example templates
+ EXTJSIV-8782 Drag and Drop: Field to Grid DnD: Default page displaying JS error
+ EXTJSIV-8833 Combination Examples: Kitchen sink: Grid to Grid: Drag and drop records from first grid to second displays js error and not able to drag from second time
+ EXTJSIV-8915 Web fonts are not loading properly in IE - they are being returned as text/plain and being truncated
+ EXTJSIV-8925 Grid: Grid Grouping with Summary: Incorrect summary is displaying after swapping the columns
+ EXTJSIV-8990 Grids :  Editable Grid with JSONP writable store :  Fields under "User" form are overlapped by the bottom toolbar.

Forms (7)

+ EXTJSIV-7921 Forms: inputEl is not properly destroyed and will leak memory
+ EXTJSIV-8386 BasicForm doesn't get dynamically added items
+ EXTJSIV-8528 Tooltip layout is wrong in IE10
+ EXTJSIV-8643 Form fields in docked items don't fire form's dirty event
+ EXTJSIV-8724 Simple combobox filtering fails
+ EXTJSIV-8841 Spinner fields trigger background is transparent, allows panel background to bleed through
+ EXTJSIV-9010 HtmlEditor border is on the wrong element.

Grid (16)

+ EXTJSIV-3994 Grid scrolls when focusing or selecting a row
+ EXTJSIV-8325 Grid sel models do not initialize correctly when configured with seltype: 'xxxxx'
+ EXTJSIV-8367 Cell editing navigation does not work when locked columns are all unlocked
+ EXTJSIV-8539 Ext.grid.column.CheckColumn arrives in the framework as a replacement for the UX Ext.ux.CheckHeader as a way of displaying mutable checkboxes in grid columns.
+ EXTJSIV-8603 Ext.grid.plugin.HeaderResizer throws error in forceFit with sibling grid
+ EXTJSIV-8619 IE scrolls when clicking on editable cell
+ EXTJSIV-8625 Neptune - Grid: top border is missing
+ EXTJSIV-8757 Grids: Grid Plugins: First grid 'Collapsible grid with lockable columns' displays empty with no data
+ EXTJSIV-8758 Grids: Grid Row Editing: Default page displaying JS error
+ EXTJSIV-8775 RTL: Grids: Sliding Pager: Clicking on slider bar displays JS error
+ EXTJSIV-8786 Grids : Buffered Grid Example :  No data is displaying after sorting the columns in a specific scenario.
+ EXTJSIV-8867 Neptune : Grids:  Grid Filtering : By default all buttons are not displaying in the grid footer.
+ EXTJSIV-8898 Multi selection functionality is not working under List View grid
+ EXTJSIV-8905 Grids:Locking Row Editing: JS Error on double clicking on any of the editable fields in RTL Mode.
+ EXTJSIV-8906 Using the RowEditor on a locked grid produces errors
+ EXTJSIV-8945 Grid header menu hides upon check of visibility checkbox

Layouts (5)

+ EXTJSIV-8204 ColumnLayout is broken or behaves differently as expected
+ EXTJSIV-8660 Unable to collapse border region by double clicking on splitter
+ EXTJSIV-8661 Collapsing a Panel with any user-configured baseCls breaks placeholder collapse.
+ EXTJSIV-8725 Tab scroller partially obscures the active tab
+ EXTJSIV-8736 Layout Managers: Border Layout: The Expand/Collapse button (Center aligned on the vertical bar) is getting separated from the bar when the right panel is expanded 

MVC (1)

+ EXTJSIV-8217 Ext.application() breaks when config object contains requires

Menu (1)

+ EXTJSIV-8730 Neptune: Toolbars and Menus: Basic Toolbar: Menu scrollers are not displayed under 'Scrolling Menu' button

Misc (20)

+ EXTJSIV-8396 Miscellaneous: Bubbled Panel: Both panel header and toggle button's UI got disturbed
+ EXTJSIV-8438 Neptune - Panel header icon is cropped 
+ EXTJSIV-8702 Grid data rows need to be vertical-align:top
+ EXTJSIV-8708 Layout Managers: Complex Layout: The "Collapse/Expand" Button's Position is changing from top to bottom when tried to collapse and expand.
+ EXTJSIV-8731 Combination Examples : Right -to-Left (RTL)  :By default "RTL" example displaying in "LTR" mode.
+ EXTJSIV-8755 Rows in a locking TreeGrid can become misaligned
+ EXTJSIV-8818 Bug with password field as a grid editor
+ EXTJSIV-8820 Windows with no header throw a JS error when maximized
+ EXTJSIV-8823 Ext.view.Table does not refresh columns on commit after store.sync
+ EXTJSIV-8859 Kitchen Sink: Field to Grid : Drag and drop the fields on to grid for second time and then immediately clicking on records displays js error
+ EXTJSIV-8869 KitchenSink-all.css contains rtl rules
+ EXTJSIV-8875 Neptune - Double click action on button creates visual defect 
+ EXTJSIV-8880 Neptune - Green placement indicator should be used everywhere
+ EXTJSIV-8951 TreePanel doesn't fire itemmove event on Drag'n'Drop
+ EXTJSIV-8966 After calling record.reject() GridView doesn't clear dirty mark
+ EXTJSIV-9005 Ext.view.NodeCache must confirm element exists before trying to use it
+ EXTJSIV-9020 Nested loading example fails to load
+ EXTJSIV-9038 Expanding a tree node causes multiple layouts
+ EXTJSIV-9050 Grouping feature breaks BufferedRenderer scrollTo function
+ EXTJSIV-9052 Window modal mask too bright, and uses wait cursor.

Panel (2)

+ EXTJSIV-8304 Panel titleAlign: center - render issue?
+ EXTJSIV-8800 Panels inside tables crash IE in quirks mode

Selection Model (1)

+ EXTJSIV-9064 Selecting a grid's row with a buffered store causes a JavaScript error

Tabs (1)

+ EXTJSIV-9015 Disabled Closable Tabs  - close icon should be "greyed" out

Theme (2)

+ EXTJSIV-6394 Gray Theme Disabled Tab Background is Pink!
+ EXTJSIV-8704 Grid Filter plugin Neptune Theme (boolean filter don't show radio images)

Tree (4)

+ EXTJSIV-8759 Combination Examples: Simple Tasks: Displaying JS error while trying to add new folder when 'List' panel is collapsed
+ EXTJSIV-8805 Ext.data.Nodeinterface - collapseChildren not working as specified
+ EXTJSIV-8832 Combination Examples: Kitchen sink: Tree Reorder: Tree panel displayed empty without nodes and js error is displayed in console
+ EXTJSIV-8874 Tree Grid - Expand Collapse action shrinks column width

Window (2)

+ EXTJSIV-8741 Neptune - WIndow >> Progress Dialog: the progress bar is cropped
+ EXTJSIV-8848 Windows: Window Variations: Top two floating windows are missing header titles and displayed with white patches

Total: 83

#Release Notes for Ext JS 4.2.0 RC 1

Release Date: February 13, 2013

Version Number: 4.2.0.489

The major new arrival in this release is Neptune! In support
of Neptune there have been many internal changes. The goal was to
preserve the historical structure of the SDK zip as much as possible,
however, there are some noteworthy changes and additions.

At a glance:

Themes are now organized as "packages" using Sencha Cmd 3.1. This allows themes to exist 
as self-contained folders with all of their required SASS, JavaScript and other resources. 
Themes use theme inheritance to share code and resources between each other.

All packages exist in the "./packages" folder off the
    Ext JS root. Packages contain source for building into your
    applications using Sencha Cmd 3.1+ as well as pre-built versions
    of CSS and JS files. These are used in "dev mode" or as part of
    your application if you are not using Sencha Cmd. The pre-built
    content for each package is in its "./build" folder.

Both the Neptune theme ("ext-theme-neptune") and Classic theme ("ext-theme-classic") extend 
the Neutral theme ("ext-theme-neutral") to inherit most of their styling needs. They provide 
their own distinct, image assets.

The Gray ("ext-theme-gray"), Accessibility ("ext-theme-access") and Classic Sandbox 
("ext-theme-classic-sandbox") themes all extend Classic.

Content changes:

If you are not using Sencha Cmd to build, then the ideal locations to pull CSS and image 
assets from the SDK are the package builds.
    
For Neptune that is "./packages/ext-theme-neptune/build" and for Classic 
"./packages/ext-theme-classic/build".

The "./resources" folder is a legacy folder that contains copies of files that now reside 
in their new home in the "./packages/ext-theme-classic/build" and related folders.

New content, such as the Neptune theme, do not exist in the "./resources" folder.

Changes to theme creation process:

Compass is still required to build framework themes.

Creating themes can be accomplished in the old way by importing the "all.scss" file from the Ext JS theme.

The ideal approach for building themes is to move the theme to the new Sencha Cmd 3.1 package 
format. Following this approach you will only need to run  sencha package build to 
produce your theme (including IE image slicing). Sencha Cmd will handle making all of the 
required Compass calls for you as well as process inherited themes.

To create an empty theme:

    sencha -sdk /path/to/ext-4.2.0 generate workspace /path/to/workspace
    cd /path/to/workspace
    sencha generate package -type=theme mytheme
    cd packages/mytheme

See the Sencha Cmd guides for more details.

Given an empty theme (as produced above), you need to edit the "package.json" file to set 
the base theme by adding an "extend" property:

    {
        "name": "mytheme",
        "type": "theme",
        "version": "1.0.0",
        "compatVersion": "1.0.0",
        "extend": "ext-theme-neptune"
    }

Look for new guides describing this process shortly, but in the interim, look at how the 
provided themes are structured as a reference.

Changes to theme creation in SASS:

Themes provide many more variables to control their styling than in previous versions.

While these are being documented, please refer to the theme's variable definition files 
found the their package folder (e.g., "./packages/ext-theme-neptune/sass/var").

These files are organized to precisely match the components to which they apply. Keep in 
mind that the variables of base themes also apply. These will be in their own "./sass/var" folder.

Most of the variables are defined in the Neutral theme. That is, in the "ext-theme-neutral" package.

Most of the mixins are also defined in the Neutral theme. That is, in the "ext-theme-neutral" 
package. These are found in the "./packages/ext-theme-neutral/sass/src" folder. As with 
variables, these files match with the respective classes and are inherited as well.

Certain core styles that are more than presentation are defined in the Base theme ("ext-theme-base").

Many of the high-level mixins (such as the panel mixin) now encapsulate much more of the 
process of defining a new "ui" (a presentation mode of a component, e.g., "default" or "framed").

As such, calls to them will need to pass more parameters to fully define the intended "ui" 
and some rules that had to be manually duplicated will need to be removed from your SASS.

Some mixin positional arguments may have changed in some cases. It is highly recommended 
to use named parameters when calling mixins and not positional ones to minimize any such issues.

##New Features

Charts (1)

+ EXTJSIV-8498 Certain Chart and Legend methods should be refactored for easier overriding

Cmd (1)

+ EXTJSIV-8638 Themes need to be Cmd packages so they can provide JavaScript overrides to builds

Direct (1)

+ EXTJSIV-4350 Callbacks should be passed options used to make the call

Grid (2)

+ EXTJSIV-3940 Grouping Feature is not Stateful
+ EXTJSIV-8368 RowEditor should support lockable grids

Theme (6)

+ EXTJSIV-8383 Themes should not use resetCSS and related scopeResetCSS and styleHtmlContent
+ EXTJSIV-8632 Deliver Neptune theme (for all browsers IE7+)
+ EXTJSIV-8633 Themes should be able to inherit easily and cleanly from other themes
+ EXTJSIV-8639 Buttons and tabs should use simpler markup and be easier to theme
+ EXTJSIV-8641 SASS Mixins should contain more of the generated styles for their components
+ EXTJSIV-8642 Date pickers should use simpler markup and be easier to theme

Total: 11

##Bugs Fixed

Charts (2)

+ EXTJSIV-4757 Setting a chart time axis to have a grid can cause errors with certain step/start val
+ EXTJSIV-7720 Minimum and maximum should be ignored in stacked charts

Core (5)

+ EXTJSIV-8280 Ext.dom.Helper.insertHtml fails in native Windows 8 app
+ EXTJSIV-8349 Component resizer handles not visible.
+ EXTJSIV-8418 IE9 navigator.geolocation memory leak (standards mode)
+ EXTJSIV-8503 MVC removes Ext.app namespace produced by Cmd optimizer
+ EXTJSIV-8536 Focus management. Window's mousedown delayed focus timer "wins" over the focus caused by click handler.

Data (9)

+ EXTJSIV-6327 Proxies must not be shared between Model super/sub classes. Fix requires user code to call Model.getProxy() to ensure access to a Model&#39;s proxy as it is now lazily instantiated when requested (so the proxy *property* may not be a Proxy).
+ EXTJSIV-6444 Store.isLoading() is wrong from inside Ext.view.View.collectData
+ EXTJSIV-6981 belongsTo & hasOne association's setters cannot accept record instances.
+ EXTJSIV-8149 Store removeAll() doesn't work for localstorage
+ EXTJSIV-8213 loadRawData should not fire load event
+ EXTJSIV-8227 Ext.data.Model.setFields() does not set all fields if extended
+ EXTJSIV-8272 NodeInterface subclass event firing causes stackoverflow
+ EXTJSIV-8281 TreeStore cannot remove nodes that were created and saved to server
+ EXTJSIV-8563 Tree Duplicate Nodes during load if node has expanded:true

DataView (2)

+ EXTJSIV-8505 Data View :  Displaying JS error  while accessing "Data view" and "animated Data view" examples.
+ EXTJSIV-8506 Data View :  Advanced Data view :  Insert Image button is displaying in expand mode.

Documentation (3)

+ EXTJSIV-7811 Problem in 4.1.x with MS dates in JSON POST to .NET WCF web service
+ EXTJSIV-8262 DnD: Ext.grid.plugin.DragDrop:beforedrop docs incorrect
+ EXTJSIV-8459 Docs don't clearly state that svg.sencha.io service only creates PNG images for exported chart data

Examples (3)

+ EXTJSIV-8337 Progress Bar left text align doesn't seem to work?
+ EXTJSIV-8400 Accessibility: 'Binding a Grid to a Form' - Displaying JS error while accessing the example.
+ EXTJSIV-8440 Unable to add a new feed in feed viewer example

Forms (10)

+ EXTJSIV-7388 Slider needs to be inverted in rtl mode
+ EXTJSIV-7462 Change to use tables for fields causes autoScroll to fail on FieldContainers
+ EXTJSIV-7890 File Field Button is invisible when in an initially hidden tab
+ EXTJSIV-8221 Form with standardSubmit isn't working
+ EXTJSIV-8229 TimeField's keystroke filtering overrides the TimePicker's min/max filtering.
+ EXTJSIV-8352 Fieldset titles misaligned
+ EXTJSIV-8463 FieldSet in RTL has incorrect margin
+ EXTJSIV-8467 Classic Theme in RTL : Forms : Slider Field : Unable to handle sliders in the slider filed example.
+ EXTJSIV-8545 Double assignment of value in form/Basic.js
+ EXTJSIV-8581 Combo events broken after combo.getStore().load()

Grid (16)

+ EXTJSIV-5482 Locking grid does not support stateful mode
+ EXTJSIV-7413 A grouped and sortable grid does not save state
+ EXTJSIV-7653 While editing a cell in a grid, clicking on another grid doesn't change focus
+ EXTJSIV-8084 BufferedRenderer Grid plugin does not work properly when editing store.
+ EXTJSIV-8159 GroupField displays instead of ColumnName in a group header of a locked grid
+ EXTJSIV-8163 Grids: Infinite Grid with Remote filter: Selection focus is not responding with down arrow key in a particular scenario
+ EXTJSIV-8166 Grid raises an error if there is second grid with summary feature
+ EXTJSIV-8174 Moving a grid column causes it to disappear
+ EXTJSIV-8180 Locking Grid: adding column using reconfigure doesn't work
+ EXTJSIV-8200 Grid with CellEditing and CheckboxModel, checker width incorrect
+ EXTJSIV-8206 GroupStore.js onUpdate function throws a JS error
+ EXTJSIV-8210 Grid store listeners not cleaned up
+ EXTJSIV-8293 Lockable plugins should not be cloned unless required
+ EXTJSIV-8336 Rowbody features don't handle store record removal.
+ EXTJSIV-8416 Grouping grid icon stays on the left in RTL mode
+ EXTJSIV-8606 delayed task: delayScroll is not canceled before destroying of the Panel

Layouts (6)

+ EXTJSIV-6867 vbox layout: containers aren't auto-heighting properly
+ EXTJSIV-7667 Table layout causes child containers using auto layout to be sized wrongly
+ EXTJSIV-8253 Ext.layout.container.Auto.calculateOverflow() can fail when scrolling
+ EXTJSIV-8323 Window header and button layout is wrong in MessageBox
+ EXTJSIV-8373 Buttongroup lays out wrong
+ EXTJSIV-8564 Click on a field in an accordion header causes the panel to collapse/expand

Locale (2)

+ EXTJSIV-8190 Slovak locale inconsistency and errors
+ EXTJSIV-8246 Turkish locale errors

MVC (1)

+ EXTJSIV-6672 Ext.app.Controller.addRef should accept arrays

Misc (1)

+ EXTJSIV-5130 Neptune theme missing resources

Selection Model (1)

+ EXTJSIV-8602 selectionchange is not fired when removing selected record

Tabs (3)

+ EXTJSIV-7709 RTL - Themes Example - tabs do not show text in IE7 strict
+ EXTJSIV-8481 Classic Theme in RTL :  Tabs : Advanced Tabs  :  Tab title is overlapped by close and tab image .
+ EXTJSIV-8609 Tab strip is missing bottom border in IE6,7,8 and IE quirks

ToolTips (3)

+ EXTJSIV-8345 Tooltip background wrong colour in classic theme. It's white
+ EXTJSIV-8346 Tooltips body should be position:relative, layout is broken
+ EXTJSIV-8362 Tooltip layout not shrinkwrapping content height

Tree (5)

+ EXTJSIV-6824 TreePanel multiselect is working incorrectly
+ EXTJSIV-8150 Dropping nodes onto folders which are currently loading throws JS error.
+ EXTJSIV-8224 Cannot deselect rows when selmodel is MULTI and treeviewdragdrop is enabled
+ EXTJSIV-8232 Event signature changed: Ext.data.TreeStore.beforeappend on root node
+ EXTJSIV-8260 Locking TreePanel autoLoads its store when regular TreePanel does not.

Total: 72

#Release Notes for Ext JS 4.2.0 Beta 2

Release Date: January 8, 2013

Version Number: 4.2.0.265

##Bugs Fixed

Core (5)

+ EXTJSIV-8042 Ext.utils.CSS.getRule - always throws error
+ EXTJSIV-8064 Modal mask doesn't appear in Chrome and IE9
+ EXTJSIV-8079 Grid grouping labels not translated (at least for German)
+ EXTJSIV-8117 Portuguese locales: wrong day and month names
+ EXTJSIV-8136 Ext.String.repeat with negative count infinite loop

Direct (1)

+ EXTJSIV-8021 Ext.Direct API methods should not be resolved at construction time

Documentation (2)

+ EXTJSIV-7881 Explain interaction of reference types and configs
+ EXTJSIV-7992 Grid guide is not updated with 4.2 improvements

Examples (2)

+ EXTJSIV-8009 Typo in desktop example
+ EXTJSIV-8029 Combination Examples: Web Desktop: 'More Items' sub menu is displayed on top left corner of the page when mouse hovered

Forms (3)

+ EXTJSIV-6999 fileuploadfield on a form is clearing selected file path after submit button is pressed
+ EXTJSIV-7918 Checkboxgroup allowBlank:false and validitychange event not firing on first click
+ EXTJSIV-7945 Error handling issue while submitting forms with file uploads in IE9

Grid (21)

+ EXTJSIV-7582 minHeight on table header causes layout faults if there is a scrollbar
+ EXTJSIV-7775 The hmenu-asc.gif icon for "Sort ascending" has the arrow pointing down. It's identical to the "sort descending" icon.
+ EXTJSIV-7895 Grouping Feature not able to show/hide columns when enableGroupingMenu: false
+ EXTJSIV-7949 Canceling new rows in RESTful store grid panel leaves behind a blank row
+ EXTJSIV-7952 Locked grid row heights fail to sync when OSX scroll bars turned off.
+ EXTJSIV-7961 Menus are constrained incorrectly. They should not have ownerCt configured.
+ EXTJSIV-7968 GroupGrid can hide all columns in certain scenario
+ EXTJSIV-7982 Summary feature causes errors if data is modified and view is not rendered
+ EXTJSIV-7983 Grouping grid headers do not always fill the horizontal space
+ EXTJSIV-7987 Grouping grid crash on record update
+ EXTJSIV-8003 Grouping grid allows grouping by last visible column
+ EXTJSIV-8005 Grid selection model events do not fire after reconfigure
+ EXTJSIV-8014 Double clicking to auto-size an unresizable column causes JS error
+ EXTJSIV-8038 Grid: view isn't removed from Scroll Manager when grid is destroyed
+ EXTJSIV-8043 Grid columns with no explicit renderer definition are not shown
+ EXTJSIV-8046 RowSelectionModel Keyboard navigation does not work.
+ EXTJSIV-8083 buffered grid checkbox selection model does not support select all 
+ EXTJSIV-8115 hidden: true of grid column with inner columns causes error
+ EXTJSIV-8144 Grids : Grouping : Displaying Js error upon navigating the records in the grid in a specific scenario.
+ EXTJSIV-8145 Grid view refresh and toggleSummaryRow not working as expected
+ EXTJSIV-8161 Buffered Grids No Longer Work In Tab Panels

Layouts (1)

+ EXTJSIV-7973 Layout failure in PropertyGrid

MVC (1)

+ EXTJSIV-6032 Controller shouldn't require selector when ref has autoCreate flag

Menu (1)

+ EXTJSIV-8167 Ext.menu.CheckItem: checked not a boolean until rendered

Misc (4)

+ EXTJSIV-5226 Focus on OK button in MessageBox
+ EXTJSIV-6014 Incomplete Localisation for LoadMask and AbstractView
+ EXTJSIV-8052 4.2.0 beta and ent-beta builds fail sencha generate app with YUI disabled
+ EXTJSIV-8087 Delegate Ext.Object.chain to Object.create

Panel (1)

+ EXTJSIV-7981 Crash when expanding collapsed/hidden panel

Toolbars (1)

+ EXTJSIV-8041 more.gif in x-toolbar-more-icon class is not RTL

Tree (1)

+ EXTJSIV-7916 Tree node removeAll(true) throws exception when there's a child node.

Total: 44

##New Features

Charts (1)

+ EXTJSIV-5604 With multiple Column series, columns can completely obscure each other.  

Core (1)

+ EXTJSIV-7564 Add Ext.Object.isEmpty method

Data (1)

+ EXTJSIV-7400 Added CORS support for IE (XDR)

Forms (1)

+ EXTJSIV-8073 HtmlEditor should be a FieldContainer and use standard container layouts

Layouts (1)

+ EXTJSIV-8072 Panel shrinkWrap should be able to include docked items in its calculation

MVC (1)

+ EXTJSIV-7429 Controllers should be able to listen to non-Component events

Performance (1)

+ EXTJSIV-8092 Data and Tree performance optimizations

Tree (1)

+ EXTJSIV-7955 Trees should be able to use buffered rendering

Total: 8

#Release Notes for Ext JS 4.2.0 Beta

Release Date: December 11, 2012

Version Number: 4.2.0.179

##Bugs Fixed

Charts (6)

+ EXTJSIV-3394 Charts - Area charts - December Month Name is missing when resize and also minimizing the chart
+ EXTJSIV-6011 Area chart numeric x-axis display bug
+ EXTJSIV-7300 Charts : Pie chart : Displaying JS error upon mouse hovering on chart legends.
+ EXTJSIV-7759 Chart ColumnSeries yField fails if not an array
+ EXTJSIV-7771 Grouped Column Chart With One Group Has Incorrect Label
+ EXTJSIV-7876 Charts: Line and Radar series: markers can't be styled with the renderer function

Core (3)

+ EXTJSIV-4453 Method `Ext.Element.setStyle()` with `-ms-transform` does not work.
+ EXTJSIV-7534 Panel border: false option breaks rendering of content
+ EXTJSIV-7717 Internal usage of Ext.fly() overwrites user's Ext.fly singleton.

Data (2)

+ EXTJSIV-3455 Model constructor does not set the idProperty when the id is specified as an argument to the constructor.
+ EXTJSIV-7287 A grouped store should automatically resort when data modified

Documentation (1)

+ EXTJSIV-7805 Ext.define function form does not support overrides

Examples (10)

+ EXTJSIV-2288 Failed test: Verify the menu display  when user right  click on the Desktop
+ EXTJSIV-4842 Combination Examples - Web Desktop : Left, Center & Right alignments are not properly working for "Notepad"
+ EXTJSIV-5464 Combination Examples - Kitchen sink - Displaying JS error upon clicking on â€šÃ„ÃºTitled Tab panelsâ€šÃ„Ã¹
+ EXTJSIV-6154 Combination Examples: Web Desktop: Notepad: Alignment is applying for whole text in text area and not just for selected line of text.
+ EXTJSIV-6352 Combination Examples : Feed Viewer: Tab size is not adjusting accordingly once after selecting the â€šÃ„ÃºYahoo Software Newsâ€šÃ„Ã¹ under Feeds panel
+ EXTJSIV-7294 Combination Examples :  Calendar : Displaying JS error while saving the event.
+ EXTJSIV-7617 Combination Examples : Web desktop :  Displaying Js error upon double clicking on "maximize" button in the "About ExtJS" window.
+ EXTJSIV-7658 Combination Example: Web desktop: Note pad is not displaying upon moving in a specific scenario.
+ EXTJSIV-7700 Grid filter menu icon missing
+ EXTJSIV-7882 Combination Examples  : Right-to-Left (RTL) (New) : East panel getting expand and collapse when we expand the "West" panel.

Forms (9)

+ EXTJSIV-4477 Ext.form.field.File: no tooltip on the upload button
+ EXTJSIV-5288 Forms : Shopping Cart Checkout:  Unable to delete the data from the phone number and postal code fields
+ EXTJSIV-5672 Forms: MultiSelect and ItemSelector: Down arrow and up arrow are not functional when multiple items are selected in ItemSelector List
+ EXTJSIV-5856 Combination Examples : Web Desktop:  Text in the notepad getting erased by clicking the "Tab" key.
+ EXTJSIV-6023 Ext.ux.form.ItemSelector with delimited cannot read delimited values
+ EXTJSIV-7085 HtmlEditor: clicking on down arrow on forecolor or backcolor button deselects text in IE
+ EXTJSIV-7711 Selecting same highlighted item in combo does not close listbox
+ EXTJSIV-7803 Down arrow on picker fields does not move focus to popup
+ EXTJSIV-7921 Forms: inputEl is not properly destroyed and will leak memory

Grid (13)

+ EXTJSIV-5794 Grouping grid with a summary for each group and the entire grid
+ EXTJSIV-5817 Grids - Grouping Grid - Grouping grid displaying blank in a specific scenario 
+ EXTJSIV-5898 Grids- Infinite scroll grid- No data is displaying upon clicking Author column header multiple times.
+ EXTJSIV-6144 Grouping Grid column menu items are not showing the proper checked/enabled state in all cases
+ EXTJSIV-6508 Grids: RESTful Store with GridPanel and RowEditor: Value under â€šÃ„ÃºIDâ€šÃ„Ã¹ column is slightly moved down on row editor in a particular scenario
+ EXTJSIV-6734 Hidden grid column's height is not properly measured when wordwrap is used
+ EXTJSIV-7449 CellEditor does not scroll with grid
+ EXTJSIV-7472 Grid  â€šÃ„Ã¬  Grouped Header  â€šÃ„Ã¬ Able to hide all columns in a specific scenario 
+ EXTJSIV-7630 Grid : Infinite Scrolling: Getting Js error when click on Expand / Collapse icons after selecting â€šÃ„ÃºGroup by this fieldâ€šÃ„Ã¹  option in the drop down menu
+ EXTJSIV-7827 Grid TableView's trackOver config does not honour false setting.
+ EXTJSIV-7853 Grids : Infinite Grid with remote filter. Load never completes if filter returned no results.
+ EXTJSIV-7932 CellEditing+ Nav error when grid is empty
+ EXTJSIV-7953 Paging Grid Example: The text preview spans 2 columns instead of 3 

Layouts (8)

+ EXTJSIV-4345 Layout does not properly handle min/maxWidth/Height if in autoWidth/Height mode
+ EXTJSIV-6030 Ext.Msg.alert fails is called while layouts are globally suspended.
+ EXTJSIV-7591 Expand border collapsed region from floated disables further collapsing.
+ EXTJSIV-7593 Border layout shuffles DOM order upon layout. This causes removed items to lose layout.
+ EXTJSIV-7687 First panel in accordion multi layout is always expanded
+ EXTJSIV-7688 Unable to specify non-collapsible panels in accordion layout
+ EXTJSIV-7744 Switching to a shrinkwrap dimension should clear that dimension in the DOM on layout
+ EXTJSIV-7858 Closing a recently collapsed region in a border layout results in a removal error

Menu (2)

+ EXTJSIV-7304 Button Menu width does not resize when word length changes
+ EXTJSIV-7823 Menu IE7 CSS issue: too wide and too white separators

Misc (19)

+ EXTJSIV-4015 Charts Die at 2147483648 - Max Integer
+ EXTJSIV-5483 Accessibility : Binding a Grid to a Form : Active state is missing on rating radio buttons through keyboard tab.
+ EXTJSIV-5533 Combination Examples : Ext JS Calender  - The event drag and drop is not functioning as desired
+ EXTJSIV-5591 JS Calendar - Unable to scroll up/down using arrow keys to select time field.
+ EXTJSIV-5678 [4.1 RC1] Scoped CSS Incorrect in IE7/8
+ EXTJSIV-5881 Tab:TabsOverflowMenu: Tabs are not seen in the drop-down in the mentioned scenario
+ EXTJSIV-6017 Miscellaneous : Panels : â€šÃ„ÃºMasked Panel with a really long titleâ€šÃ„Ã¹ is not displaying title when panel is collapsed in Opera 11.61
+ EXTJSIV-6130 Drag and Drop : Grid to Grid DnD : Displaying JS error while moving records from first grid to second grid with "Ctrl" key.
+ EXTJSIV-7015 Padding causes box layout overflow scroller to never disable scroll right button
+ EXTJSIV-7081 Offset start and limit calculated incorrectly for infinite grid
+ EXTJSIV-7095 Not triggered and unefficient summary update.
+ EXTJSIV-7207 Constrained floaters: Should maintain position but then constrain upon floatParent resize and move.
+ EXTJSIV-7374 RTL - Themes Example - Message Box does not show any content, just an empty frame.
+ EXTJSIV-7390 RTL - animation of width in rtl mode uses an incorrect anchor point
+ EXTJSIV-7447 Miscellaneous: Slider: 'Vertical Slider with multiple thumbs' tool tips are misplaced in a scenario
+ EXTJSIV-7470 Border layout: expanding collapsed region caused iframe reloading
+ EXTJSIV-7509 Grid column header trigger gets cut off if header text is too wide in IE6 & IE quirks
+ EXTJSIV-7603 Windows -> Window Variations: Constrained windows position is changing or going outside the window, when Constraining window is moved.
+ EXTJSIV-7776 ComponentQuery doesn't consider numeric zero as a value

Panel (3)

+ EXTJSIV-5381 Panel does not open after rapid fire expand/close
+ EXTJSIV-7411 RTL - Themes Example - collapsed east placeholder has incorrect padding on tool.
+ EXTJSIV-7740 BorderLayout: 'hidden: true' is ignored if 'collapsed: true'

Selection Model (2)

+ EXTJSIV-7848 SelectionModel selectionchange event triggered when not needed
+ EXTJSIV-7903 RowModel.onEditorTab doesn't handle cancelled beforeedit

Toolbars (2)

+ EXTJSIV-5067 Toolbars and Menus: Basic Toolbar: Space between 'Choose a color' and 'Dynamically added item' menu items is more in IE compared to other browsers
+ EXTJSIV-7609 Toolbar overflow button has no padding-right

Tree (2)

+ EXTJSIV-6399 TreeViewDragDrop plugin now has a sortOnDrop config to maintain sort state of target node.
+ EXTJSIV-7762 Trees: Drag and Drop Reordering: Expand/ Collapse for couple of times display JS error

Window (1)

+ EXTJSIV-6341 Windows: Window Variations: Two floating windows â€šÃ„ÃºConstrained Windowâ€šÃ„Ã¹ and â€šÃ„ÃºHeader-Constrained Windowâ€šÃ„Ã¹ are disappearing in a particular scenario

Total: 83

#Release Notes for Ext JS 4.1.3

Release Date: October 25, 2012

Version Number: 4.1.3.548

##Highlights

The biggest change beyond bug fixes is the new build script based on
Sencha Cmd. Goto the SDK folder and run the following: 

    sencha ant build

##Bugs Fixed

Charts (9)

+ EXTJSIV-5500 Style for chart line series not applied
+ EXTJSIV-6593 Bars in bar chart are not aligned with labels using time axes
+ EXTJSIV-6611 Column chart with date axis does not render properly
+ EXTJSIV-6931 Labels on Time axis do not respect "step" config
+ EXTJSIV-6974 Custom chart theme - colors incorrectly applied with stacked columns
+ EXTJSIV-6992 Area chart  x-axis does not handle ticks with different increments than the data points
+ EXTJSIV-7180 Grid update. Updating selected row refocuses that row stealing focus from any previously focused element.
+ EXTJSIV-7210 Chart losing label contrast after highlight
+ EXTJSIV-7220 Some series charts that do not have a Category Axis defined do not render

Core (5)

+ EXTJSIV-6803 Element content updating fails to update IMG src on IE.
+ EXTJSIV-7091 Accessibility: Keyboard Feed Viewer: Unhiding "Author"column displays JS error
+ EXTJSIV-7309 Missing key:value in Ext.Date.monthNumbers of the ext-lang-fr.js file
+ EXTJSIV-7484 Splitter doesn't work with one hidden panel next to it
+ EXTJSIV-7486 Date: UTC time zone offsets are no longer calculated

Data (4)

+ EXTJSIV-7215 DomQuery does not support an attribute selector with a "." in it
+ EXTJSIV-7226 Presence validation does not take boolean values into account
+ EXTJSIV-7269 Ext.data.NodeInterface remove doesn't call destroy if parent is null
+ EXTJSIV-7422 Field mapping should only honor 0 as a valid falsey value and ignore others

Documentation (2)

+ EXTJSIV-7102 Missing itemclick in docs for Ext.chart.series.Series
+ EXTJSIV-7463 Update docs for propertygrid.nameColumnWidth

Draw (1)

+ EXTJSIV-7243 Drawing "Logos - Couple of Browser logos are displaying in Black & white color in FF

Examples (5)

+ EXTJSIV-7123 Chart examples use xtype on constructed objects
+ EXTJSIV-7196 Statusbar Advanced example problem hiding error popup
+ EXTJSIV-7268 Charts   "Filled Radar Chart - Getting JS error when click on Animate Button
+ EXTJSIV-7351 Combination Examples -  Web Desktop "Video is not playing and error "X"icon is displaying when  select "About Ext JS"option  in IE9
+ EXTJSIV-7434 Typo in text for maxSelections on both MultiSelect and ItemSelector

Forms (11)

+ EXTJSIV-6069 ComboBox reports incorrect value when non-unique display fields are used
+ EXTJSIV-6405 Default ComboBox shrinkWrap width should match TextField
+ EXTJSIV-6959 Focus lost when error tooltip displayed on modal window/form
+ EXTJSIV-6964 HtmlEditor text highlight color is not working under html editor under Form-3 in FF browsers
+ EXTJSIV-7062 Focus on combobox and datepicker removes the ability to close the row editor with "esc" key
+ EXTJSIV-7117 ComboBox forceSelection doesn't fire select event
+ EXTJSIV-7204 Ext.form.field.File could not be fully enabled after being disabled
+ EXTJSIV-7206 A filefield initially hidden does not render the browse button correctly when shown
+ EXTJSIV-7314 Forms "Checkout form - Validation tool tip message is displaying even after entering required data in the text fields
+ EXTJSIV-7348 NumberField ignores spinDownEnabled and spinUpEnabled configs
+ EXTJSIV-7396 HtmlEditor: Editor is still focused after Source Edit is toggled off

Grid (19)

+ EXTJSIV-6431 Grouping grid allows grouping by last visible column
+ EXTJSIV-7010 Remote grid filtering doesn't work with locked column
+ EXTJSIV-7051 Infinite grid: can't scroll to last row when cell height is changed
+ EXTJSIV-7127 Deleting row above selected cell of a grid causes multiple cells to appear selected
+ EXTJSIV-7140 Cannot call method 'getXY' of null error when scrolling buffered grid after creating new store with grid.reconfigure
+ EXTJSIV-7166 Buffered Grid scrollTo does not always reach specified scrollTop on IE
+ EXTJSIV-7167 Grid : Grid plugins : Unable to expand the gird rows when we lock all the columns in the grid.
+ EXTJSIV-7177 Grids : Cell editing with grouping Feature. Navigation allowed into collapsed groups.
+ EXTJSIV-7211 CellSelectionModel, grid editing plugin failed when used for TreePanel editing
+ EXTJSIV-7214 Locking grid gets in infinite loop when column locked config is set to false
+ EXTJSIV-7225 Grid: when using forceFit config, headers and columns are out of sync when resized
+ EXTJSIV-7238 Able to hide all columns when the one remaining column is menuDisabled
+ EXTJSIV-7335 Grid reconfigure without new store unbinds old store
+ EXTJSIV-7336 Grid column with locked false causes stack overflow
+ EXTJSIV-7361 Scroll delta difference when hovering locked and unlocked columns in FF15
+ EXTJSIV-7451 propertygrid: enableColumnResize and enableColumnMove configs don't work
+ EXTJSIV-7495 Grids:Grid Plugins: Double clicking on grid rows displays row expanded body with dotted line border
+ EXTJSIV-7519 Girds :  Gird Plugins Examples : Displaying Js error while scrolling down in the grid with keyboard key.
+ EXTJSIV-7569 Table Views itemupdate event's node param is not a node associated with the view.

Layouts (3)

+ EXTJSIV-7231 Showing/Hiding panel in borderLayout shows/hides all spliter on the same level
+ EXTJSIV-7358 JavaScript error when grid toolbars switched (IE error only)

+ EXTJSIV-7403 Overflow Tool bar : ">>"(Menu extend /Menu trigger) button is not working

MVC (3)

+ EXTJSIV-7308 Controller classes not in a 'controller' namespace fail during class creation
+ EXTJSIV-7420 Ext.application causes synchronous loading and mail fail on some models
+ EXTJSIV-7547 Incorrect MVC namespace determined for some classes

Menu (2)

+ EXTJSIV-7265 A checkbox is rendered on a checkmenuitem when the item is part of a radio group
+ EXTJSIV-7442 A button with a menu crashes if all menu items are disabled and you tab from field

Misc (11)

+ EXTJSIV-4070 Modal containers allow tab out.
+ EXTJSIV-5450 Focus lost when error tooltip displayed on modal window/form
+ EXTJSIV-6845 Locking Grouping Grid: It is possible to hide all columns, resulting in a zero width grid.
+ EXTJSIV-7157 RowBody of a selected row doesn't look selected
+ EXTJSIV-7170 Ext.data.Model destroy always sends delete request to server
+ EXTJSIV-7195 HtmlEditor text area loses background color when using the highlight feature
+ EXTJSIV-7216 Page analyzer gets stack overflow in IE8
+ EXTJSIV-7234 BUGS: ExtJS API doc view -- error in IE8
+ EXTJSIV-7435 Ext.selection.DataViewModel missing view render check
+ EXTJSIV-7460 LoadMask always in front when owner has a parent container
+ EXTJSIV-7475 Tabs -> Group Tabs: JS error is displayed while navigating between the various tabs in IE6 and IE7 browsers only

Panel (1)

+ EXTJSIV-7561 'body' missing in the docs of Panel

Tabs (1)

+ EXTJSIV-7320 Tab Scroller Menu Plugin- Selected Tab is not activated 

ToolTips (2)

+ EXTJSIV-7139 Tooltips with header have no padding around tools
+ EXTJSIV-7221 Error tooltip shown when no error

Tree (5)

+ EXTJSIV-7248 Unable to sort tree node in an un-rendered tree
+ EXTJSIV-7321 Tree view dragdrop does not copy a subtree
+ EXTJSIV-7341 Tree node's expand icon disappears on select when loading is required to show children
+ EXTJSIV-7466 TreeViewDragDrop plugin:   configuration allowParentInserts is not working
+ EXTJSIV-7476 When reloading a tree node, view throws TypeError from updateIndexes

Window (2)

+ EXTJSIV-7185 Initially maximized window can still drag/resize
+ EXTJSIV-7229 Stateful window shown with animation save position incorrectly

Total: 86

#Release Notes for Ext JS 4.1.2

Release Date: September 7, 2012

Version Number: 4.1.2.381

##Bugs Fixed

Animation (2)

+ EXTJSIV-5214 Ext.fx.Amin only animates last element in target list
+ EXTJSIV-5675 animateTarget id can cause animations to fail in some cases

Charts (12)

+ EXTJSIV-4699 Gauge Chart Label Click issue
+ EXTJSIV-6236 Columns are not bound to the x-axis
+ EXTJSIV-6249 Multiple issues with Time axis, Masks and Zoom
+ EXTJSIV-6629 chart.Chart.afterRender contains dead code
+ EXTJSIV-6708 Tooltip doesn't display the value on first mouseover
+ EXTJSIV-6789 Line carts lose style after resize
+ EXTJSIV-6861 Line series is not shown after disabling and enabling the legend item
+ EXTJSIV-6896 Bar Graph Axis become corrupted when refreshing
+ EXTJSIV-6901 Chart "Line Chart:   All nodes are relocated at end point, when legend items are unchecked and checked 
+ EXTJSIV-6977 Charts should restrict user from repeating category axis values
+ EXTJSIV-7065 Charts: Reload Chart: "Reload Data" button is not functioning
+ EXTJSIV-7111 Pie Charts: One  of the segment does not animate when shadow is set to false.

Core (17)

+ EXTJSIV-6520 scrollIntoView causes menu items to disappear in IE
+ EXTJSIV-6552 Instantiating local storage provider in old IE causes hard error
+ EXTJSIV-6571 Grid Selection Model fires mouseup event when using direction keys
+ EXTJSIV-6626 Ext.syncRequire() doesn't add to Ext.Loader.history the same as Ext.require()
+ EXTJSIV-6690 Calling Element.selectable() on labels doesn't make it selectable
+ EXTJSIV-6713 Ext.Element.purgeAllListeners doesn't work
+ EXTJSIV-6714 Ext.Function.createInterceptor can't return false value for intercepted method
+ EXTJSIV-6716 ExtJs 4.1.0 - XTemplate and nestled tpl for loops does not set parent values properly
+ EXTJSIV-6817 Dataview overItemCls only applied in dev mode
+ EXTJSIV-6829 Observable hasListener returns true after clearListeners
+ EXTJSIV-6852 Ext.dom.Helper fails to update innerHTML of THEAD in IE
+ EXTJSIV-6859 DomHelper.insertAfter with multiple rows always inserts the 2nd row in IE
+ EXTJSIV-6863 constrainTo property has no effect when window is being shown
+ EXTJSIV-6905 Ext.Date doesn't support 'o' and 'W' ISO-8601 formats
+ EXTJSIV-6928 Danish locale NumberField decimal separator incorrect
+ EXTJSIV-7108 setDisabled on panel during render adds class to wrong element
+ EXTJSIV-7175 Loader garbage collection causes IE to request script with null src.

Data (28)

+ EXTJSIV-4601 Tree cannot accept a root node that is currently the root of another Tree.
+ EXTJSIV-5612 File uploads may fail in Opera
+ EXTJSIV-5677 metaData is not read in wrapped JSON (ASP.NET)
+ EXTJSIV-6305 Model instance shared if proxy subclass specifies a reader config object
+ EXTJSIV-6441 Ext.data.proxy.JsonP autoAppendParams ignored in buildUrl method
+ EXTJSIV-6483 Store's remove event is fired for each record passed - need bulkremove event
+ EXTJSIV-6550 store.reload() has hard error when called on empty buffered store
+ EXTJSIV-6614 Need spec to make sure AMF Packet can decode XMLDocument data type in AMF3
+ EXTJSIV-6615 Need spec to verify AMF Packet can decode headers
+ EXTJSIV-6616 AMF Packet has problems with floating point numbers.
+ EXTJSIV-6617 AMF Packet does not decode dates correctly
+ EXTJSIV-6622 AMF Packet needs spec for "Typed Object" data type
+ EXTJSIV-6623 AMF Grid Example throws "attempted to get unknown AMF3 type" error.
+ EXTJSIV-6663 JsonP destroy method confuses entity life cycle with object cleanup
+ EXTJSIV-6666 Model.idChanged Event not fired when saving phantom records
+ EXTJSIV-6733 Ext.view.AbstractView pollutes record's data object with associated data
+ EXTJSIV-6743 TreeStore does not require specified model class as does Store
+ EXTJSIV-6746 TreeStore nodeParam should replace "id" in requests
+ EXTJSIV-6753 DomQuery does not handle xml elements with namespace prefixes
+ EXTJSIV-6755 TreeStore CRUD read request appends "id" parameter when TreeStore's "nodeParam" parameter is already present.
+ EXTJSIV-6788 Datetime-fields not sent as null by Writer when not having a value
+ EXTJSIV-6826 Ext.data.Writer does not recognize 'timestamp' field type
+ EXTJSIV-6831 TreeStore sometimes modifies the specified root node config
+ EXTJSIV-6848 Forms: MultiSelect and ItemSelector: Items are duplicated, when drag and drop the selected items under "MultiSelect Test"form
+ EXTJSIV-6882 AMF Ajax specs have been disabled because of relative paths.
+ EXTJSIV-6933 metachange event fire multiple times
+ EXTJSIV-6935 Typo in extjs-4.1.1/src/data/Store.js line 1768
+ EXTJSIV-6988 Buffered store w/ grid locks up in loading

DataView (3)

+ EXTJSIV-5722 Data view : Advanced Data view  :  Vertical scroll bar is neither moving up/down  even user selection reached end of the list.
+ EXTJSIV-6437 DataView: DataView: Images alignment is disturbed when only spaces are given in the image name
+ EXTJSIV-6858 Ext.view.View fire itemadd when adding to empty view

Documentation (7)

+ EXTJSIV-5409 Ext.String.trim method is not parsing @example tag correctly
+ EXTJSIV-6180 Grid guide refers to old verticalScrollerType, link to Infinite Scrolling Example broken
+ EXTJSIV-6625 Rewrite AMF guide
+ EXTJSIV-6742 Window ghost config not documented
+ EXTJSIV-6822 Ext.util.Renderable.initRenderData should be marked as protected
+ EXTJSIV-6835 Several components attempt to limit the access on their inherited API
+ EXTJSIV-6936 Remove call to getBubbleTarget in Ext.util.Observable:enableBubble example in docs because it recurses on itself

Draw (2)

+ EXTJSIV-7186 Wrong calculation of step in Ext.draw.Draw
+ EXTJSIV-831 Gradients not working when I extend Ext.draw.Component

Events (1)

+ EXTJSIV-6047 Ext.EventManager.contains should accept raw browser event instance

Examples (18)

+ EXTJSIV-6446 Combination Examples: Ext Js Calendar :First created event is getting dragged and dropped  instead of second event
+ EXTJSIV-6447 Direct: Direct Named Arguments: When long text is entered in name fields, server response alert is shown out of the response box.
+ EXTJSIV-6555 Calendar incorrectly renders when date is set from midnight one day to midnight of the following day. 
+ EXTJSIV-6601 Combination Examples : Ext JS Calendar :No horizontal gap between the fields of "When" and "Calendar"
+ EXTJSIV-6602 Toolbars and Menus : Overflow toolbar : User getting "Action date"  alerts when user delete or enters invalid date in the action field.
+ EXTJSIV-6635 Forms "Shopping cart Checkout" All items in the state combo box  are not displaying in a specific scenario
+ EXTJSIV-6638 Combination Examples - Portal Demo - Graph is disappearing upon on click on "sp500" legend items when  it is in enable state
+ EXTJSIV-6649 Combination Examples - Feed viewer: Unable to select Column Header drop down menu after selecting "Right" option in the preview drop down menu.
+ EXTJSIV-6677 Embedded ItemSelector in MultiSelects are configured to persist
+ EXTJSIV-6703 MessageBox's initial layout to auto size itself is visible in Opera
+ EXTJSIV-6770 Ext.ux.TreePicker in form return RawValue after form.getValues() is called
+ EXTJSIV-6809 Trailing comma issue in Ext.ux.grid.filter.DateFilter
+ EXTJSIV-6812 MultiSelect issue with same label
+ EXTJSIV-6908 Ext.ux.form.MultiSelect value should be empty array if store is empty not null
+ EXTJSIV-6922 AMF and SOAP examples throw an error in qa environment
+ EXTJSIV-6929 MultiSelect.getValue with single mode selection returns array of 2 items
+ EXTJSIV-7012 GMapPanel creating global variable
+ EXTJSIV-7053 Broken link to sqlite installation page in grid filtering example

Forms (40)

+ EXTJSIV-4412 URL validation do not accept localhost
+ EXTJSIV-5389 Form gets dirty if a textarea field contains a leading line break
+ EXTJSIV-5763 Disabled displayfield doesn't appear greyed out
+ EXTJSIV-5855 HtmlEditor: various issues related to linebreaks and font selection
+ EXTJSIV-5966 Clarify the documentation regarding checkboxfield checkedCls
+ EXTJSIV-5980 Ext.form.field.File button text french translation is missing
+ EXTJSIV-6128 Ext.form.field.HtmlEditor: Can not select text outside visible text part
+ EXTJSIV-6152 HTMLEditor Font Combo Missing and Anchor margin-bottom not applied
+ EXTJSIV-6219 Modal mask causes body scroll on IE7/Quirks/IFrame
+ EXTJSIV-6241 Field validation is not always triggered when deleting all content in IE8/9
+ EXTJSIV-6280 Too much top and bottom padding of form fieldset
+ EXTJSIV-6424 FieldContainer's absolute layout misplaced in firefox
+ EXTJSIV-6514 Element.getAlignToXY inaccuracy when close to right edge of viewport
+ EXTJSIV-6521 Focus (including selectText) on input fields not functioning correctly
+ EXTJSIV-6556 Focus on htmlEditor doesn't work
+ EXTJSIV-6595 BasicForm  reset should remove reference to _record
+ EXTJSIV-6609 Disabled fields should not display validation errors
+ EXTJSIV-6652 Ext.form.field.File enable is not enabling the button
+ EXTJSIV-6669 Right Click Pasting does not trigger the combobox picker
+ EXTJSIV-6706 Timefield text input disappears on first keystroke
+ EXTJSIV-6711 Ext.form.field.Number change min/max Value doesn't reset maskRe
+ EXTJSIV-6745 Form submit modal wait message. Modal mask not hidden on return.
+ EXTJSIV-6771 LabelAlign top doesn't work
+ EXTJSIV-6772 NumberField enforceMaxLength doesn't deal  with spin up/down
+ EXTJSIV-6777 ComboBox readOnlyCls is never applied
+ EXTJSIV-6793 MultiSelect/ItemSelector do not display error icon properly
+ EXTJSIV-6796 Text field size changes on focus / blur in IE8
+ EXTJSIV-6798 Picker drop downs not closed by tab key blur
+ EXTJSIV-6836 Japanese locale invalidates timefield when AM/PM is enabled
+ EXTJSIV-6874 reader and errorReader of Basic Form does not support creating by type
+ EXTJSIV-6890 Disabled HTML Editor Masks Entire Form in Firefox
+ EXTJSIV-6934 msgTarget qtip/title trigger layouts when not needed
+ EXTJSIV-6939 Combobox flickers before it appears for first time
+ EXTJSIV-6944 Fieldsets with a minHeight and collapsible collapse incorrect elements
+ EXTJSIV-6950 Proper css class not added when labelAlign: 'top'
+ EXTJSIV-6990 triggerNoEditCls is not applied to non-editable or readonly Ext.form.field.ComboBox
+ EXTJSIV-7000 CheckboxManager incorrectly returns checkboxes from other forms
+ EXTJSIV-7017 Email vtype doesn't allow single quote and other special chars within local part of email address
+ EXTJSIV-7020 Multi-thumb slider cannot set all values at once using setValue
+ EXTJSIV-7058 Forms "Shopping cart Checkout" - Text fields are overlapping with respective section borders 

Grid (42)

+ EXTJSIV-4164 RowWrap feature CSS overrides the grid cell dirty CSS
+ EXTJSIV-5595 Last selected row maintains selection after unchecked on column sort
+ EXTJSIV-5676 rowLines : false config has no effect for locked grid
+ EXTJSIV-6404 [4.1] scrollByDeltaX and scrollByDeltaY methods not working on a locking grid panel.
+ EXTJSIV-6592 Column header CSS classes related to sort contain "undefined"
+ EXTJSIV-6598 Group Column hidden: true doesn't hide its child columns
+ EXTJSIV-6634 RowNumberer columns should default to being in the locked side of a lockable grid.
+ EXTJSIV-6665 Locked side of locked grid is 1px too wide, may scroll horizontally upon focus.
+ EXTJSIV-6691 Ext.grid.feature.GroupingView does not respect enableGroupingMenu
+ EXTJSIV-6695 When CheckboxSelectionModel is used in locking grid, check column is duplicated, one on each side.
+ EXTJSIV-6702 Grouping Feature's menu CheckItem "Show in groups" should be disabled if Store is not grouped.
+ EXTJSIV-6724 Wrong getEditor() call in RowModel.
+ EXTJSIV-6727 Columns in locked grid should be able to be not lockable.
+ EXTJSIV-6730 Error when editable column edited then dragged to other side of locked grid, edited again, the dragged back and edited again
+ EXTJSIV-6731 Grid "Locking, Group Summary Grid Example with grouped headers - Getting JS Error when tab key is pressed and  hold for a while when all columns  are locked state
+ EXTJSIV-6736 Features and plugins are always cloned to both sides of a lockable grid.
+ EXTJSIV-6747 Grid check box selection bug
+ EXTJSIV-6759 Ext.grid.header.Container:getHeaderIndex has typo in query string
+ EXTJSIV-6768 Grid cell editing does not update rendered elements properly in all cases
+ EXTJSIV-6800 Columns grid header menu needs hideOnClick set
+ EXTJSIV-6808 Grid sortchange fires two times on header click(sort)
+ EXTJSIV-6811 Position is NaN in slider when number of records < = pageSize 
+ EXTJSIV-6820 In all header menu drop-downs,Sort Descending icon is not displaying 
+ EXTJSIV-6839 CheckboxModel sometimes accesses element before rendering
+ EXTJSIV-6842 Cell Editing Grid:   Displaying JS error when Delete Plant button is clicked after selecting any cell in the grid
+ EXTJSIV-6860 Destroying a grid during grid editing results in JS error
+ EXTJSIV-6875 [4.1.1 GA] RowEditing Update button initially looks enabled for invalid editor
+ EXTJSIV-6876 Grid with rowExpander is non-functional if a column is locked.
+ EXTJSIV-6914 Wrong horz scrollbar on Grid within Accordion Layout
+ EXTJSIV-6930 Ext.grid.plugin.RowEditingView conflicting with grouped headers in grid
+ EXTJSIV-6932 RowNumberer rowSpan is not applied
+ EXTJSIV-6985 Calling setWidth on grid header with hideHeaders:true does not resize column
+ EXTJSIV-6986 Cell editing restores wrong value when value is updated during edit
+ EXTJSIV-6989 Row updating after field edit does not update all attributes of the TDs
+ EXTJSIV-7014 Load options.callback called multiple times when Store is buffered
+ EXTJSIV-7018 Row update loses altRowCls for row striping
+ EXTJSIV-7046 Grid "Locking, Group Summary Grid Example with grouped headers" Displaying Blank when  Schedule column is locked  
+ EXTJSIV-7087 PropertyGrid without source throws a JavaScript error
+ EXTJSIV-7088 Checkbox disappears after reconfigure call on locked grid with checkbox selection mod
+ EXTJSIV-7092 Grid : Locking Grouping Grid with Summary and Grouped headers: "Schedule" grouped column header is still displaying even there are no columns exist in the group.
+ EXTJSIV-7104 With CheckboxModel selection model Header Checkbox is checked on empty store
+ EXTJSIV-7115 Locked grid header menu trigger disappears after a reconfigure

Layouts (6)

+ EXTJSIV-5999 Overflow items do not sync with dynamic state change of toolbar. Toggle buttons represented wrongly.
+ EXTJSIV-6539 Collapsed regions are changing layout after floating out in a border layout
+ EXTJSIV-6854 Table layout - clearEl defined but not used
+ EXTJSIV-6925 Panel with flex 'height' less than minHeight not working correctly
+ EXTJSIV-6979 collapseFirst: false does not work for the accordion layout
+ EXTJSIV-6996 Splitters in vbox layout incorrectly read width instead of height

MVC (3)

+ EXTJSIV-6662 Ext.app.Controller.hasRef - use Ext.Array.indexOf to find reference
+ EXTJSIV-6725 Controller dependencies are broken if you don't have controller in the class name
+ EXTJSIV-6726 views set on Ext.application will not load files

Misc (27)

+ EXTJSIV-4583 Singleton is created when singleton (false) is listed
+ EXTJSIV-4853 Drag and Drop : Grid To Grid DnD - Tool tip is stretched while dragging the row second time.
+ EXTJSIV-6170 Ext.DomHelper's 'confRe' matches substrings while it shouldn't
+ EXTJSIV-6248 Ext.chart.Mask is broken
+ EXTJSIV-6356 locale update for ext-lang-it.js
+ EXTJSIV-6376 [4.1.0] TreePanel selectPath callback is called twice
+ EXTJSIV-6400 Floating components do not get destroyed when an ancestor is destroyed
+ EXTJSIV-6409 Field to grid example. Enable dragging fields via their label.
+ EXTJSIV-6537 Date picker shows a selection when picking a new month from the month picker, even though the value has not changed.
+ EXTJSIV-6640 If a container is draggable, Ext.resizer.Resizer does not resize the container in IE8
+ EXTJSIV-6728 Border Layout: collapsing or expanding a region while another region's float animation is taking place puts the layout in a weird state.
+ EXTJSIV-6757 New Jira Test!
+ EXTJSIV-6761 en_GB Locale does not localize dates in DateColumns
+ EXTJSIV-6819 TaskRunner quietly catches errors
+ EXTJSIV-6833 Ext.util.KeyNav.setConfig() assigns undefined defaultEventAction property
+ EXTJSIV-6834 XTemplate renders null data value as "null" but should be blank like undefined
+ EXTJSIV-6844 AMF Grid Example does not load in Firefox 3.6
+ EXTJSIV-6846 When scrolling down an infinite and locked column grid the row synchronization breaks
+ EXTJSIV-6851 AbstractComponent addes isContained to item configs
+ EXTJSIV-6864 AbstractComponent methods preFocus, beforeBlur and postBlur should be protected not private
+ EXTJSIV-6873 Ext.grid.plugin.DragDrop dragText is not localized
+ EXTJSIV-6942 negativeText is not overridden in locale files for Ext.locale.ru.form.field.Number
+ EXTJSIV-6984 ext-lang-pt_BR.js accent is not properly encoded
+ EXTJSIV-7001 AbstractComponent - duplicate Ext.ComponentQuery dependency
+ EXTJSIV-7013 Selection disappears when scrolling in an infinite grid
+ EXTJSIV-7047 Grids -> Locking Grouping Grid with Summary and grouped headers: Columns are not properly aligned when initially example is loaded.
+ EXTJSIV-7143 Accidental global vars in Date parser and VType

Panel (7)

+ EXTJSIV-6543 Collapsing a panel causes its header to appear even if "header:false"
+ EXTJSIV-6720 Panel header tools - "close" not set to instance of Ext.panel.Tool
+ EXTJSIV-6774 Adding a floating component does not trigger the add event
+ EXTJSIV-6779 Panel.addTool can add tool twice
+ EXTJSIV-6915 Placeholder does not honor titleCollapse over floating
+ EXTJSIV-6927 Panel placeholder collapse event fires at construction time
+ EXTJSIV-6997 Calling Panel.setTitle when not rendered fails to set the title

Selection Model (1)

+ EXTJSIV-6937 CellSelectionModel gets JS error when Tab button is pressed after deleting last row in the grid 

Tabs (1)

+ EXTJSIV-6633 TabPanel's tabBar config should accept a layout config to modify the layout of the tabBar

Theme (1)

+ EXTJSIV-6643 _loadmask.scss - typo in a variable name

ToolTips (1)

+ EXTJSIV-6693 Using tooltips on various components throws errors when QuickTips are not enabled

Toolbars (3)

+ EXTJSIV-5970 Overflowchange is not fired when a toolbar is resized and the overflow is changed
+ EXTJSIV-6814 Repeated button hiding causes non-responsiveness
+ EXTJSIV-6982 Toolbar item setText does not update text property

Tree (14)

+ EXTJSIV-3758 Tree API is missing "getOwnerTree" method
+ EXTJSIV-3764 TreeView does not provide nodedragover event
+ EXTJSIV-6474 Tree node quick tip needs to be HTML encoded when rendered
+ EXTJSIV-6667 Tree node drag drop reordering does not invoke tree panel scroller
+ EXTJSIV-6681 [4.1] Poor performance of TreeStore sort
+ EXTJSIV-6738 Global leak in NodeInterface decorate method
+ EXTJSIV-6797 TablePanels with hideHeaders:true missing top border
+ EXTJSIV-6813 TreeGrid keyboard navigation stops working in IE9 after you expand a node using the keyboard
+ EXTJSIV-6856 TreeView does not always update height after expand/collapse of items
+ EXTJSIV-6857 Tree does not auto size using after expand/collapse with animate: false
+ EXTJSIV-6865 Tree add and remove methods have poor performance
+ EXTJSIV-6866 Dragging elements past the overflow point in a tree grid does not allow scrolling
+ EXTJSIV-7048 Consecutive animated expand/collapse calls on a tree node causes unpredictable corruption and JS errors.
+ EXTJSIV-7135 Trees"Drag and Drop reordering "Getting script error in FF browsers when "Expand All"and "Collapse All"buttons are clicked 

Window (7)

+ EXTJSIV-6426 CellEditors in a modal Window cause the window to be masked below its own mask.
+ EXTJSIV-6540 Maximized window rendered into a DIV positioned incorrectly.
+ EXTJSIV-6689 Align center in a window doesn't wrap text
+ EXTJSIV-6756 Esc will not close window with a editable grid If Esc was used to stop inline editing
+ EXTJSIV-6782 Modal mask for Window can cause scrollbars on the body in IE
+ EXTJSIV-6872 Ext.Msg.show maxWidth doesn't cause any effect
+ EXTJSIV-6941 IconCls param ignored in Ext.MessageBox.show

Total: 243

#Release Notes for Ext JS 4.1.1

Release Date: July 4, 2012

Version Number: 4.1.1

##Bugs Fixed

Charts (6)

+ EXTJSIV-6275 Line chart messed up after disabling and enabling lines though legend
+ EXTJSIV-6323 Charts don't render with either constrain, or both maximum and minimum
+ EXTJSIV-6324 Problem using minimum, maximum and majorTicksSteps together
+ EXTJSIV-6359 Chart should display integers on axis
+ EXTJSIV-6583 Chart redraw on store update fails in inactive card
+ EXTJSIV-6585 Rapid clicks on pie chart causes slices to shrink or disappear

Core (10)

+ EXTJSIV-3932 dom.style.setExpression not implemented in IE8
+ EXTJSIV-5956 Ext.extend does not handle constructor properly using 3-argument form
+ EXTJSIV-6087 Ext.data.TreeStore CRUD regression
+ EXTJSIV-6452 Container's private floatingItems collection should be floatingDescendants
+ EXTJSIV-6453 Container-owned floating items appear at wrong level in the ComponentQuery hierarchy
+ EXTJSIV-6456 ComponentQuery :last selector fails with a single item
+ EXTJSIV-6484 Ext.AbstractManager.onAvailable listener isn't removed properly
+ EXTJSIV-6499 Reusing id's for elements recently removed from the DOM would incorrectly reference old element
+ EXTJSIV-6570 Ext.Element getStyle can throw in IE6/7 reading font styles
+ EXTJSIV-6612 Observable.resumeEvents should tolerate being called when suspendCount is zero

Data (6)

+ EXTJSIV-5253 Ext.data.writer.Json no longer respects dateFormat
+ EXTJSIV-5995 Model field disappear when using idProperty
+ EXTJSIV-6480 loadData reading an Array uses the wrong field order to read the data items.
+ EXTJSIV-6523 data.Reader will not read data where a model is included
+ EXTJSIV-6545 Can't reload buffered store after filtering
+ EXTJSIV-6627 Model.copy passes its data into the new constructor as raw which gets converted.

DataView (1)

+ EXTJSIV-6524 AbstractView should not cancel SPACE key event if target is an input element.

Documentation (3)

+ EXTJSIV-5148 Ext.selection.Model documentation bug
+ EXTJSIV-6187 Grouping and locking features do not work together
+ EXTJSIV-6573 AbstractComponent.render missing in the API docs

Examples (4)

+ EXTJSIV-6449 Simple Tasks reminder window does not lay out when resized.
+ EXTJSIV-6450 Themes example's layout expands vertical slider's element to 100% width
+ EXTJSIV-6462 Chart rendering is broken by moving its ancestors in the DOM in IE
+ EXTJSIV-6717 Combination Examples - Feed Viewer:  Getting error upon clicking on any feed in the preview panel when "Hide" option is selected in the preview drop down menu.

Forms (15)

+ EXTJSIV-6071 The title of the MultiSelect is not displayed
+ EXTJSIV-6085 "Custom Layout " Alert message borderline is missing under "Radio Groups " in IE6 
+ EXTJSIV-6086 labelWidth is ignored with labelAlign top
+ EXTJSIV-6127 TextField emptyText cannot be entered as the value
+ EXTJSIV-6160 Ext.form.field.Time does not initialize value correctly
+ EXTJSIV-6227 Adding a new field to a form layout fails on IE
+ EXTJSIV-6311 Time field clears value on blur.
+ EXTJSIV-6371 Fields with labelAlign top need to not make label its own row - causes too many problems
+ EXTJSIV-6402 DisplayField doesn't update size after a value change
+ EXTJSIV-6416 Calling setText on unrendered TextField does not work
+ EXTJSIV-6445 standardSubmit: true is broken for forms with params
+ EXTJSIV-6478 Ext.form.BasicForm fails to correctly read the response of a file upload
+ EXTJSIV-6568 HtmlEditor leaks memory on window unload in IE6/7
+ EXTJSIV-6579 HtmlEditor contents are cleared by initial Ext.example.msg
+ EXTJSIV-6594 enforceMaxLength with no maxLength in textfield allows only one char

Grid (18)

+ EXTJSIV-5343 Lockable views do not handle drag between two sides well or dragging of or between group headers.
+ EXTJSIV-6075 Checkbox selection model's header checkbox not in sync if records are added/removed
+ EXTJSIV-6242 Grid row editor does not close when record being edited is removed
+ EXTJSIV-6264 Grid filter range menu iconCls conflicts with Panel iconCls - rename to itemIconCls
+ EXTJSIV-6419 Grid Filters JS error when click on any column header after filtering Date and swap columns 
+ EXTJSIV-6420 Grid row heights aren't synced in locked grid on IE9 standards.
+ EXTJSIV-6421 Locking grid headers misplaced after column hide
+ EXTJSIV-6440 BorderLayout: collapsed GridPanel on south looks inconsistent after expand
+ EXTJSIV-6463 Infinite grid alignment is skewed by presence of group headers
+ EXTJSIV-6477 Arrow keys become unresponsive when arrowing through records in a buffered grid
+ EXTJSIV-6481 Firefox 13 new default smooth scrolling leads to very slow grid scrolling
+ EXTJSIV-6482 Grid RowExpander is not reinserted after reconfigure
+ EXTJSIV-6509 Using getEditor on a grid column creates an orphaned component resulting in a memory leak
+ EXTJSIV-6531 Grid reconfigure fails with hideHeaders
+ EXTJSIV-6546 PagingScroller onCacheClear assumes view is rendered
+ EXTJSIV-6584 Cell editing in locked grid causes JS error
+ EXTJSIV-6644 CellSelectionModel selects the wrong cell in a locked grid
+ EXTJSIV-6718 Tab key causes error when cell editing with row selection model

Layouts (5)

+ EXTJSIV-5131 ShrinkWrap layouts can fail with constrained widths / heights
+ EXTJSIV-6041 In IE8/9 "strict" mode, Box layout's perpendicular overflow does not work
+ EXTJSIV-6049 Auto-width grid in vbox stretches to 10,000px
+ EXTJSIV-6369 Closing floated/collapsed panel in border layout causes JS error
+ EXTJSIV-6528 Ext.layout.container.BoxOverflow.Menu.destroy throws Exception

Menu (1)

+ EXTJSIV-6386 Picking a date doesn't work when Date field inside Menu

Misc (2)

+ EXTJSIV-6348 Drag-drop on invalid dropzone leaves no focus
+ EXTJSIV-6510 IE 6 nonsecure items warning when using Ext.History

Panel (4)

+ EXTJSIV-5149 "mini" collapseMode in border layout doesn't seem to work
+ EXTJSIV-6372 Multiple issues with Panel.setBodyStyle
+ EXTJSIV-6373 Specifying Panel header config and closable: true causes error
+ EXTJSIV-6448 Left and right aligned headers in panel drag are not layed out properly

Theme (2)

+ EXTJSIV-6163 SplitButton with arrowAlign bottom and Gray theme - CSS issue on mouse over
+ EXTJSIV-6425 Sass function theme-background-image throws exception without a return value and css doesn't compile

Toolbars (2)

+ EXTJSIV-6251 Toolbar defaults override single item settings
+ EXTJSIV-6451 Form fields clone in overflow menu of toolbar do not sync the original field value

Tree (9)

+ EXTJSIV-5248 Ext.data.TreeStore setting the root property in the proxy doesn't work
+ EXTJSIV-6005 Ext.data.TreeStore with Ext.data.proxy.Rest does not pass ids correctly
+ EXTJSIV-6302 NodeInterface qtip and qtitle not updated
+ EXTJSIV-6417 tree.selectPath(tree.getRootNode().getPath()) doesn't select
+ EXTJSIV-6418 Folder keeps displaying collapse button after all leaves are dragged away
+ EXTJSIV-6443 expandable: false has no effect in tree grid
+ EXTJSIV-6473 Spacebar not toggling checkbox state in TreePanel
+ EXTJSIV-6554 Tree view refresh event is fired before the render event
+ EXTJSIV-6580 Tree node parentId doesn&#39;t respect useNull

Window (6)

+ EXTJSIV-5889 Dragging a header-constrained window below Viewport bottom scrolls the Viewport
+ EXTJSIV-6033 Ext.window.Window fire incorrect events when maximized/restored
+ EXTJSIV-6234 Constrained window in a border layout is displaying at wrong location.
+ EXTJSIV-6297 Constraining a window to a panel using the "constrain" config does not work when "autoShow" is true
+ EXTJSIV-6397 Form submit with waitMsg:'string' called from Window focuses the Window which hides any MessageBox
+ EXTJSIV-6547 Window is not closed on Esc

Total: 94

#Release Notes for Ext JS 4.1.1 RC 2

Release Date: June 13, 2012

Version Number: 4.1.1 RC 2

##Bugs Fixed

Button (2)

+ EXTJSIV-6139 Button retains the focused state after disabling and enabling
+ EXTJSIV-6329 Config html of Button not working

Charts (2)

+ EXTJSIV-6077 Layouts cause Charts to (re)animate
+ EXTJSIV-6224 Chart export hard codes sencha.io

Core (11)

+ EXTJSIV-5767 return false from beforerender throws exception
+ EXTJSIV-5944 Ext.onReady with delay option hangs up a browser
+ EXTJSIV-6055 onReady does not work in an iframe in IE8 when parent is a different domain
+ EXTJSIV-6056 Problems with Component previousNode
+ EXTJSIV-6124 Loader calls Ext globalEval with code that breaks when IE cc_on
+ EXTJSIV-6137 Element slideIn tr anchor doesn't work as expected.
+ EXTJSIV-6185 getPosition on floating Components with parent Container always returns container-relative position
+ EXTJSIV-6196 calling showAt on a component does not fire the 'show' event.
+ EXTJSIV-6199 DomQuery fails with dots in the element id
+ EXTJSIV-6273 EventManager does not return listener response
+ EXTJSIV-6319 Ext.onReady sometimes fails in an iframe in IE when parent is in a different domain

Data (3)

+ EXTJSIV-6298 Ext.data.Tree.flatten duplicates Ext.Object.getValues
+ EXTJSIV-6305 Model instance shared if proxy subclass specifies a reader config object
+ EXTJSIV-6306 Model's Id field not defined after sync in TreeStore

DataView (1)

+ EXTJSIV-6019 When deferInitialRefresh is false, the arrival of the data still causes a second layout run

Documentation (2)

+ EXTJSIV-5558 refs config not in API documentation
+ EXTJSIV-6179 pruneRemoved on Ext.selection.Model should not be private

Events (1)

+ EXTJSIV-6320 Listener tracking is broken when removing non-existent listener

Examples (1)

+ EXTJSIV-6413 Tabs : Basic Tabs: Clicking on "Event Tab"for first time, displaying the tab's content with border line

Forms (17)

+ EXTJSIV-5298 Ext.form.Panel does not respect inherited properties when creating the BasicForm
+ EXTJSIV-5962 Dragging mouse off the right over a form scrolls content out of view in WebKit
+ EXTJSIV-6121 TimeField submit format not using 24 hour format
+ EXTJSIV-6142 Form field with incorrect width on validation, if msgTarget: 'side'
+ EXTJSIV-6143 Ext.form.field.Number: Spinner field sometimes fires 2 spin events
+ EXTJSIV-6173 Field not destroyed after form is closed
+ EXTJSIV-6176 Forms : File uploads : "File upload" window is not opening upon clicking on "photo" text field.
+ EXTJSIV-6184 Labelable: getFieldLabel should implement same logic as the setter as regards label separator
+ EXTJSIV-6198 Fields within Field Container don't resize properly
+ EXTJSIV-6255 TextAarea ignores "cols" attribute
+ EXTJSIV-6258 Combobox forceSelection clears the value if there is no match
+ EXTJSIV-6277 MsgBox header components are not placed properly in IE
+ EXTJSIV-6278 Trigger button does not look disabled on a disabled ComboBox
+ EXTJSIV-6281 Store filter from combobox remains after combo is destroyed and store is reused
+ EXTJSIV-6303 HtmlEditor destroy generates errors
+ EXTJSIV-6340 Measurement of triggerWidth does not work correctly with scopedResetCSS
+ EXTJSIV-6361 File upload field browse button does not properly re-enable after the field has been disabled in Internet Explorer

Grid (29)

+ EXTJSIV-5934 Infinite Grid does not clear page cache when grouping changes
+ EXTJSIV-6001 Error in Ext.grid.plugin.Editing if no cell is active
+ EXTJSIV-6025 CellEditing plugin does not refocus edited cell when completing an edit
+ EXTJSIV-6037 When groups are rendered initially collapsed using startCollapsed, they cannot be expanded.
+ EXTJSIV-6050 Grid Group's groupHeaderTpl does not have parent param
+ EXTJSIV-6070 Row positions issue on vertical scroll and sorting
+ EXTJSIV-6107 Grid Column Sort Indicator Problem
+ EXTJSIV-6115 RowEditing uses wrong record if startEdit is called while already editing a record
+ EXTJSIV-6117 Locked column in infinite grid causes rows to disappear on page refresh
+ EXTJSIV-6122 Editing a Grid and then reloading its Data causes error
+ EXTJSIV-6123 Wrong grid panel height on layout change
+ EXTJSIV-6135 Scrolling and Rendering Bug in Grid Grouping with Summary example
+ EXTJSIV-6157 Grid Row Editor's Update button is not always enabled/disabled properly
+ EXTJSIV-6164 ProgressBar Pager fails when clicking on left edge of the progress bar.
+ EXTJSIV-6171 RowEditor in tab panel does not show editors properly when tab is hidden
+ EXTJSIV-6186 ActionColumn icon not updating in Grid or TreeGrid
+ EXTJSIV-6194 removeAll on buffered grid causes error in cancelAllPrefetches
+ EXTJSIV-6197 ActionColumn appearance does not change when disabled
+ EXTJSIV-6228 Column Group uses wrong config "restrictColumnReorder" - should be "sealedColumns"
+ EXTJSIV-6232 Grid column resizers are not aligned correctly
+ EXTJSIV-6259 Infinite Grid with Grouping. Groups should not be collapsible.
+ EXTJSIV-6313 Large jumps in infinite grid sometimes prune a required page from the buffered store
+ EXTJSIV-6337 Gridview fails to render properly if initial refresh occurs before view is rendered
+ EXTJSIV-6347 Grid Column Tooltip not supported as it was in v3
+ EXTJSIV-6364 Cell editing with RowSelection model causes JS error on endEdit
+ EXTJSIV-6414 Grid / Infinite Scrolling with remote filtering / Load masking is displaying and not able to search for the second time 
+ EXTJSIV-6422 Row Editor throws an error when the grid has a checkbox selection model
+ EXTJSIV-6436 RowEditor does not sync when grid columns dragged to reorder.
+ EXTJSIV-6461 Sort is broken on Remote Summary Grid

Layouts (9)

+ EXTJSIV-5167 Box layout (toolbar) overflow button does not work twice
+ EXTJSIV-5562 Horizontal scrollbar not visible when set to overflow in hbox layout
+ EXTJSIV-5806 Box layout fails to respect width and height percentages
+ EXTJSIV-5935 Error removing item afterRender: ownerContext.target.ownerLayout not defined
+ EXTJSIV-5939 Adding a new Checkbox to a CheckboxGroup fails on IE
+ EXTJSIV-5990 Layout failure with fieldset in vbox
+ EXTJSIV-6129 Collapsed fieldset does not resize parent when opened
+ EXTJSIV-6158 Percentage size does not work for floating components like Window
+ EXTJSIV-6428 Accordion with single item throws JS error in onComponentCollapse

MVC (1)

+ EXTJSIV-6162 Ext.application.init() is never invoked

Menu (2)

+ EXTJSIV-6254 Can't edit textfields properly when placed in a Menu
+ EXTJSIV-6321 Menu subclass doesn't inherit scrolling functionality

Misc (11)

+ EXTJSIV-6100 .sass-cache included in extjs pachage
+ EXTJSIV-6170 Ext.DomHelper's 'confRe' matches substrings while it shouldn't
+ EXTJSIV-6193 DragDropManager.fireEvents - wrong parameters calling onInvalidDrop
+ EXTJSIV-6208 Traditional Chinese localization does not display properly for days of the week in IE
+ EXTJSIV-6226 Draw component does not auto-size correctly with no content
+ EXTJSIV-6253 Scoped css doesn't work well for filtering and date picker
+ EXTJSIV-6287 Flash Component disregards WMODE transparent
+ EXTJSIV-6304 Ext.menu.DatePicker select triggered twice
+ EXTJSIV-6335 DatePicker's native tip occludes "Today" button's QuickTip
+ EXTJSIV-6407 AbstractContainer overrides enable/disable without returning this
+ EXTJSIV-6412 Grids :Grouping Grid:The "Name"column check box is not displaying 

Panel (6)

+ EXTJSIV-4144 Collapsible FormPanel collapsible direction [right] issue
+ EXTJSIV-4268 Panel does not respect animCollapse: false in placeholder collapseMode (border layout)
+ EXTJSIV-5351 Inconsistency on closing tabpanel items
+ EXTJSIV-5456 Layout changes inside a collapsed panel in a border layout creates extra panel header
+ EXTJSIV-6148 Calling removeDocked on a panel with no border throws exception
+ EXTJSIV-6178 Expanding a panel restores wrong size if size changed while collapsed

Tabs (2)

+ EXTJSIV-6237 When labelAlign='top' and errorAlign='side', invalidation causes incorrect field width
+ EXTJSIV-6272 Tab text centering stops working in IE8 after dynamically adding tab
Theme (2)

+ EXTJSIV-6188 Toolbar margin variables don't have !default flags
+ EXTJSIV-6282 Sass bug in _frame.scss when $radius === 10

ToolTips (1)

+ EXTJSIV-6221 Canceling tooltip in beforeshow causes subsequent problems

Toolbars (4)

+ EXTJSIV-5933 Toolbar reorderer stops during drag on IE
+ EXTJSIV-6251 Toolbar defaults override single item settings
+ EXTJSIV-6271 Programmatically set label in bbar is not visible until browser is resized
+ EXTJSIV-6279 tbseparator incorrectly inherits border from toolbar

Tree (9)

+ EXTJSIV-3571 Two TreePanel behave wrongly when sharing a store
+ EXTJSIV-4918 Tree expand all / collapse all buggy behavior
+ EXTJSIV-5992 Tree expandAll/collapseAll does not always descend fully
+ EXTJSIV-6136 TreePanel loadMask cannot be rebound to a different mask
+ EXTJSIV-6286 Ext.ux.CheckColum does not work with a Tree
+ EXTJSIV-6302 NodeInterface qtip and qtitle not updated
+ EXTJSIV-6330 TreeStore root node does not always have an id
+ EXTJSIV-6344 Uncaught TypeError: Cannot read property 'dom' of null
+ EXTJSIV-6357 TreeStore listeners are not cleaned up

Window (2)

+ EXTJSIV-3779 Message Box Dialog - Page is grayed out and not allowed to update the page when quickly double-clicking on Icon Show button. 
+ EXTJSIV-5905 JS error when creating LoadMask bound to a Window

Total: 118

#Release Notes for Ext JS 4.1.1 RC 1

Release Date: May 15, 2012

Version Number: 4.1.1 RC 1

##Bugs Fixed

Button (3)

+ EXTJSIV-5964 Buttons do not show 'pressing' animation when clickEvent is 'mousedown'
+ EXTJSIV-5989 Changing text in some buttons does not layout properly in Chrome 16+
+ EXTJSIV-6109 Button contents are cut off when using scoped CSS

Charts (3)

+ EXTJSIV-5981 Bound of Area Series incorrectly calculated.
+ EXTJSIV-6074 Column chart with all zero data renders poorly and throws css warnings
+ EXTJSIV-6088 Pie chart is broken after resize

Core (1)

+ EXTJSIV-6052 DragZone determines wrong target el causing subsequent JS error

Data (4)

+ EXTJSIV-5988 Falsy Ext.data.Operation id property lost during Ext.data.Request creation.
+ EXTJSIV-5993 Ext 4.1 RC3  HasOne Assocation Bug
+ EXTJSIV-6024 Problem in extending from a model with associations
+ EXTJSIV-6063 Ext.data.Store.add() behave inconsistently when groupField is used

DataView (2)

+ EXTJSIV-6082 Hidden data view breaks when updating
+ EXTJSIV-6110 Ext.view.AbstractView indexOf throws error if argument is invalid or null

Documentation (1)

+ EXTJSIV-6112 Errors and omissions in the MVC Application Architecture guide

Events (1)

+ EXTJSIV-5983 beforerender event not fired for Viewport (or component with configured 'el')

Examples (1)

+ EXTJSIV-6045 GroupTabPanel ux bug - Missing lower rounded corner

Forms (10)

+ EXTJSIV-5389 TextArea marks form as dirty
+ EXTJSIV-5458 Delete key does not work for textfield (email vtype) in Opera 11
+ EXTJSIV-5965 TextField placeholder text shifts up by 1 pixel on focus
+ EXTJSIV-5994 FieldSet label component is not available before render
+ EXTJSIV-6016 MultiSelect / ItemSelector : "Clear" and "Reset" Buttons are not working when all items are dragged to right panel in Item Selector Table.
+ EXTJSIV-6054 Spinner setReadOnly does not hide triggers
+ EXTJSIV-6065 TextArea special keys stop working at maxLength with enfornceMaxLength on
+ EXTJSIV-6081 A HiddenField occupies visible space in the form
+ EXTJSIV-6104 Slider readOnly has no effect
+ EXTJSIV-6134 Labelable insertion templates do not have access to component id

Grid (5)

+ EXTJSIV-5984 [4.1 RC3] Grouping expand() not working
+ EXTJSIV-6057 Calling Ext.grid.Panel.reconfigure before rendering causes error
+ EXTJSIV-6066 Grid does not always show its loadmask properly
+ EXTJSIV-6083 scope has no effect on actioncolumn
+ EXTJSIV-6092 Grid header Container getVisibleHeaderClosestToIndex does not check previous only next

Layouts (5)

+ EXTJSIV-5797 Autosized tooltips are not layed out correctly
+ EXTJSIV-5806 Box layout fails to respect width and height percentages
+ EXTJSIV-5861 Fit layout does not adjust sizes based on autoScroll triggered by minHeight
+ EXTJSIV-6026 Splitters in HBox layouts have no height
+ EXTJSIV-6042 getPosition method doesn't return page coordinate

Menu (1)

+ EXTJSIV-6035 Menu destroy method can cause JS error on keyNav

Misc (1)

+ EXTJSIV-5982 Stacked bar/column chart leave a ghost shadow when all items are hidden

Panel (2)

+ EXTJSIV-5716 Panels with min/max constraints misbehave in a box layout with stretchmax
+ EXTJSIV-5916 Problem with Panel.setTitle without header

Tree (3)

+ EXTJSIV-6051 4.1 Grid to Tree DnD not working any more
+ EXTJSIV-6076 Changing TreeStore's defaultRootProperty breaks the tree
+ EXTJSIV-6113 TreeGrid is not repainted after the vertical scroll bar disappears

Window (1)

+ EXTJSIV-6048 Frame: true should not cause a window to display badly

Total: 44

#Release Notes for Ext JS 4.1.0

Release Date: April 20, 2012

Version Number: 4.1.0

##Bugs Fixed

Charts (2)

+ EXTJSIV-5657 Charts : Grouped Bar :Displaying Js error upon clicking on "Legends" in the "grouped bar" chart on IE9
+ EXTJSIV-5954 Simple Area Chart Not Working in 4.1RCx

Core (4)

+ EXTJSIV-5811 Elements can't fadeIn() after fadeOut()

+ EXTJSIV-5846 Component id's starting with non-word characters cause JS errors
+ EXTJSIV-5902 Draggable and resizable images leave resize handlers at start point when moved
+ EXTJSIV-5958 Ext.Error toString not including the method name

Data (5)

+ EXTJSIV-4957 Inconsistent signature for the Store &#39;datachanged&#39; event
+ EXTJSIV-5809 Model fields are set to undefined or defaultValue when they should not be updated
+ EXTJSIV-5862 Dependency on Writer from Proxy causes JS error
+ EXTJSIV-5877 Store modifies the value of inline data config option
+ EXTJSIV-5945 Ext.data.Model getFields returns undefined

DataView (1)

+ EXTJSIV-5831 Floatable TreePanel in West Border of Viewport has two left hand borders

Draw (1)

+ EXTJSIV-5904 Surface.removeAll - fails to remove items from groups

Events (3)

+ EXTJSIV-5193  Resize event is not fired for custom form field
+ EXTJSIV-5815 Error using a mixin that itself has Ext.util.Observable as a mixin
+ EXTJSIV-5844 Events: option.target has been removed from 4.x

Examples (2)

+ EXTJSIV-5948 Ext.ux.form.ItemSelector does not work with asynchronous loading (proxy) in ItemSelector example 
+ EXTJSIV-5949 RC3: Ext.ux.form.ItemSelector.bindStore() method non-functioning

Forms (8)

+ EXTJSIV-4978 Forms - Dynamic Forms : Unable to access Form 1, Form 2 & Form 5 when clicked on expand/collapse  button and and pressed the tab key
+ EXTJSIV-5242 DisplayField does not respect fieldStyle
+ EXTJSIV-5826 Validation of timefield is not correct in Chinese.
+ EXTJSIV-5827 Work day is corrupt in Spanish date input
+ EXTJSIV-5832 Recreating an HtmlEditor makes it unable to be focused until ENTER is pressed
+ EXTJSIV-5906 Can't create trigger field outside of onReady
+ EXTJSIV-5937 CheckboxGroup has incorrect column loop
+ EXTJSIV-5955 Ext.form.Labelable uses a CSS class without baseCSSPrefix

Grid (4)

+ EXTJSIV-5457 Grid infinite scroll: no last elements, no return to first elements
+ EXTJSIV-5847 Ext.ux.grid.FiltersFeature removes dynamically added filters
+ EXTJSIV-5894 GroupingSummary returns '\u00a0' when sum is equal 0
+ EXTJSIV-5953 TemplateColumn not updated dynamically

Layouts (2)

+ EXTJSIV-5562 Horizontal scrollbar not visible when set to overflow in hbox layout
+ EXTJSIV-5941 Resizable Components in Absolute layouts get misplaced.

MVC (1)

+ EXTJSIV-4202 Problem with building when MVC app has a custom directory structure
Menu (1)

+ EXTJSIV-5804 Menu onClick does not fire in all cases

Misc (4)

+ EXTJSIV-5134 Miscellaneous - Panels : "Masked Panel with a really long title" panel's UI is disturbed when clicked more than twice on expand/ collapse button
+ EXTJSIV-5501 Ext.Date.format breaks on wrong input
+ EXTJSIV-5899 Combination Examples:Ext JS Calendar:Displaying js error while creating the new event  with empty date field.
+ EXTJSIV-5967 ElementLoader - inconsistent API (?)

Panel (1)

+ EXTJSIV-5959 Panel with collapseFirst: false and closable does not display collapse tool button

Tabs (2)

+ EXTJSIV-5099 Tabs - Advanced Tabs : Tabs are added without close button when clicked on "Add Closable Tab" button
+ EXTJSIV-5857 TabPanel children don't fire the close event

Theme (1)

+ EXTJSIV-3712 TabBar background is blue in the gray theme

Tree (2)

+ EXTJSIV-5908 Fast clicks in Tree can lead to duplication of entries
+ EXTJSIV-5952 Allow NodeInterface.decorate to expect a record instance for backward compatibility

Window (1)

+ EXTJSIV-5897 Window's title will not  display in IE6/7/8 when it was dragging

Total: 45
