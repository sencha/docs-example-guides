# Differences Between Ext JS 6.5.0 Modern and Ext JS 6.2.1 Modern

While we believe these guides are extremely helpful to developers planning to upgrade their applications,
please be aware that the content is generated from documentation and may not always perfectly describe
the actual code changes in the release. Incorrect changes may be indicated due to comment updates, formatting
omissions, etc..

If you see anything suspicious or inaccurate in this report, please report the problem on the
[Forums](https://www.sencha.com/forum/forumdisplay.php?132-Ext-JS-Community-Forums-6-x) or to
[Sencha Support](https://support.sencha.com/).

## Added
 - Ext.chart.Caption
 - Ext.chart.modifier.Callout
 - Ext.chart.navigator.*
 - Ext.chart.series.BoxPlot
 - Ext.chart.series.sprite.BoxPlot
 - Ext.chart.sprite.Bar3D
 - Ext.chart.sprite.BoxPlot
 - Ext.chart.theme.*
 - Ext.d3.svg.Export
 - Ext.data.Group
 - Ext.data.Range
 - Ext.data.summary.*
 - Ext.data.validator.*
 - Ext.data.virtual.*
 - Ext.dataview.Component
 - Ext.dataview.listswiper.*
 - Ext.dataview.Location
 - Ext.dataview.NavigationModel
 - Ext.dataview.pullrefresh.*
 - Ext.dataview.selection.*
 - Ext.Dialog
 - Ext.Editor
 - Ext.exporter.excel.PivotXlsx
 - Ext.exporter.file.ooxml.excel.*
 - Ext.field.ComboBox
 - Ext.field.Container
 - Ext.field.Date
 - Ext.field.FileButton
 - Ext.field.InputMask
 - Ext.grid.Location
 - Ext.grid.menu.*
 - Ext.grid.NavigationModel
 - Ext.grid.plugin.CellEditing
 - Ext.grid.plugin.Summary
 - Ext.grid.selection.*
 - Ext.Indicator
 - Ext.layout.Center
 - Ext.layout.Form
 - Ext.menu.*
 - Ext.panel.Collapser
 - Ext.panel.Date
 - Ext.panel.Resizer
 - Ext.route.*
 - Ext.util.Cookies
 - Ext.util.KeyMap
 - Ext.util.KeyNav
 - Ext.ux.google.map.Marker
 - Ext.ux.rating.Picker

## Renamed
 - `Ext.layout.Default` -> `Ext.layout.Auto`
 - `Ext.plugin.ListPaging` -> `Ext.dataview.plugin.ListPaging`
 - `Ext.plugin.SortableList` -> `Ext.dataview.plugin.SortableList`
 - `Ext.plugin.PullRefresh` -> `Ext.dataview.plugin.PullRefresh`
 - `Ext.field.DatePicker` -> `Ext.field.Date`
 - `Ext.util.TapRepeater` -> `Ext.util.ClickRepeater`
 - `Ext.panel.Tool` -> `Ext.Tool`
 - `Ext.grid.plugin.MultiSelection` -> `Ext.grid.plugin.RowOperations` (Added extra functionality)

## Removed
 - Ext.grid.HeaderGroup (Use `Ext.grid.column.Column`, which can also act as a group of headers).
 - Ext.plugin.field.PlaceHolderLabel (Was deprecated in 6.2.0, placeholder label support is native to the field)
 - Ext.ux.google.Feeds

## Modified
### Ext
- Added Methods
   - `getApplication`
   - `getViewportHeight`
   - `getViewportWidth`

### Ext.app.Application
- Added Configs
   - `viewport`

### Ext.app.bind.Binding
- Added Methods
   - `isAvailable`

### Ext.app.ViewController
- Added Methods
   - `setBind`

### Ext.app.ViewModel
- Added Methods
   - `setData`

### Ext.Base
- Added Methods
   - `destroyMembers`
- Modified Methods
   - `getConfig`
      - Added _ifInitialized_ param

### Ext.Button
- Added Configs
   - `arrow`
   - `arrowAlign`
   - `buttonType`
   - `destroyMenu`
   - `menu`
   - `menuAlign`
   - `toggleHandler`
- Added Vars
   - `$button-arrow-horizontal-spacing`
   - `$button-arrow-horizontal-spacing-big`
   - `$button-arrow-icon`
   - `$button-arrow-icon-color`
   - `$button-arrow-icon-font-size`
   - `$button-arrow-icon-font-size-big`
   - `$button-arrow-icon-size`
   - `$button-arrow-icon-size-big`
   - `$button-arrow-vertical-spacing`
   - `$button-arrow-vertical-spacing-big`
   - `$button-badge-font-size-big`
   - `$button-badge-line-height-big`
   - `$button-badge-padding-big`
   - `$button-box-shadow`
   - `$button-box-shadow-transition`
   - `$button-disabled-arrow-icon-color`
   - `$button-disabled-background-color`
   - `$button-disabled-background-gradient`
   - `$button-disabled-border-color`
   - `$button-disabled-box-shadow`
   - `$button-focused-arrow-icon-color`
   - `$button-focused-background-color`
   - `$button-focused-background-gradient`
   - `$button-focused-border-color`
   - `$button-focused-box-shadow`
   - `$button-focused-color`
   - `$button-focused-icon-color`
   - `$button-focused-outline-color`
   - `$button-focused-outline-offset`
   - `$button-focused-outline-style`
   - `$button-focused-outline-width`
   - `$button-hovered-arrow-icon-color`
   - `$button-hovered-background-color`
   - `$button-hovered-background-gradient`
   - `$button-hovered-border-color`
   - `$button-hovered-box-shadow`
   - `$button-hovered-color`
   - `$button-hovered-icon-color`
   - `$button-icon-only-padding`
   - `$button-icon-only-padding-big`
   - `$button-pressed-arrow-icon-color`
   - `$button-pressed-box-shadow`
   - `$button-raised-ui`
   - `$button-square-ui`
   - `$button-text-transform`
   - `$button-text-transform-big`
   - `$enable-inverted-alt-button`
- Modified Vars
   - `$button-action-ui`
      - **type** is map (was boolean)
   - `$button-alt-ui`
      - **type** is map (was boolean)
   - `$button-confirm-ui`
      - **type** is map (was boolean)
   - `$button-decline-ui`
      - **type** is map (was boolean)
   - `$button-flat-ui`
      - **type** is map (was boolean)
   - `$button-plain-ui`
      - **type** is map (was boolean)
   - `$button-round-ui`
      - **type** is map (was boolean)
   - `$button-segmented-ui`
      - **type** is map (was boolean)
- Removed Configs
   - `badgeCls`
   - `baseCls`
   - `labelCls`
   - `pressedCls`
   - `pressingCls`
- Removed Vars
   - `$button-pressed-shadow`
   - `$button-shadow`
   - `$button-small-ui`
   - `$include-button-uis`

### Ext.carousel.Carousel
- Modified Configs
   - `indicator`
      - **type** is Boolean/Ext.carousel.Indicator (was Boolean)

### Ext.chart.AbstractChart
- Added Configs
   - `captions`

### Ext.chart.axis.Time
- Removed Configs
   - `calculateByLabelSize`

### Ext.chart.axis.Time3D
- Removed Configs
   - `calculateByLabelSize`

### Ext.chart.interactions.PanZoom
- Added Configs
   - `doubleTapReset`

### Ext.chart.legend.SpriteLegend
- Added Configs
   - `hidden`

### Ext.chart.series.Line
- Added Configs
   - `curve`

### Ext.chart.series.Pie3D
- Removed Configs
   - `angleField`

### Ext.chart.series.sprite.Cartesian
- Modified Methods
   - `renderClipped`
      - Modified _ctx_ param
         - **type** is CanvasRenderingContext2D (was Ext.draw.engine.Canvas/Ext.draw.engine.SvgContext)
      - Added _dataClipRect_ param
      - Added _surfaceClipRect_ param
      - Removed _clip_ param
      - Removed _rect_ param

### Ext.chart.series.sprite.Line
- Added Configs
   - `curve`
- Removed Configs
   - `smooth`
   - `step`

### Ext.chart.series.sprite.Series
- Added Configs
   - `labelOverflowPadding`
   - `labels`

### Ext.chart.sprite.Label
- Added Configs
   - `field`
   - `hideLessThan`

### Ext.Component
- Added Configs
   - `displayed`
   - `modelValidation`
   - `tabIndex`
   - `weight`
- Added Methods
   - `initDragConstraints`
   - `initInheritedState`
   - `onResize`
   - `showAt`
- Added Static-methods
   - `from`
- Modified Configs
   - `draggable`
      - **type** is now for a drag source
- Modified Properties
   - `rendered`
      - **access** is public (was private)
- Modified Methods
   - `show`
- Removed Configs
   - `styleHtmlCls`
   - `styleHtmlContent`

### Ext.Container
- Added Configs
   - `autoSize`
   - `defaultFocus`
   - `innerCls`
   - `weighted`
- Added Methods
   - `findDefaultFocus`
   - `getFocusEl`

### Ext.d3.axis.Axis
- Modified Configs
   - `scale`
      - **type** is Object (was Object/Function)

### Ext.d3.Component
- Added Configs
   - `transitions`
- Added Methods
   - `createTransition`
- Modified Properties
   - `panZoom`
      - **access** is public (was protected)

### Ext.d3.hierarchy.Hierarchy
- Added Configs
   - `linkKey`
   - `noParentValue`
- Added Properties
   - `layoutTransition`
- Added Methods
  - `addLinks`
   - `addNodes`
   - `nodeFromRecord`
   - `removeLinks`
   - `removeNodes`
   - `selectionFromRecord`
   - `updateLinks`
   - `updateNodes`
- Modified Methods
   - `onNodeDeselect`
      - Added _record_ param
      - Added _selection_ param
      - Removed _node_ param
      - Removed _element_ param
   - `onNodeSelect`
      - Added _record_ param
      - Added _selection_ param
      - Removed _node_ param
      - Removed _element_ param
- Removed Methods
   - `selectNode`

### Ext.d3.hierarchy.partition.Sunburst
- Removed Configs
   - `nodeSelectTransition`
   - `nodeZoomTransition`

### Ext.d3.hierarchy.tree.Tree
- Removed Configs
   - `diagonal`

### Ext.d3.hierarchy.TreeMap
- Added Configs
   - `scaleLabels`
- Removed Configs
   - `sticky`

### Ext.d3.svg.Svg
- Added Methods
   - `alignContent`

### Ext.data.AbstractStore
- Added Methods
   - `createActiveRange`

### Ext.data.field.Field
- Added Configs
   - `summary`
- Added Methods
   - `getSummary`
- Modified Methods
   - `validate`
      - Modified _errors_ param
         - **type** is Ext.data.ErrorCollection/Ext.util.Collection/Array (was Ext.data.ErrorCollection)

### Ext.data.LocalStore
- Added Methods
   - `getSummaryRecord`

### Ext.data.Model
- Added Configs
   - `summary`
- Added Methods
   - `calculateSummary`
   - `mergeData`
- Added Static-methods
   - `getSummaryModel`
   - `loadData`
- Modified Methods
   - `getData`
      - Modified _options_ param
         - Modified _associated_ property
            - **type** is Boolean/Object (was Boolean)

### Ext.data.proxy.Memory
- Added Configs
   - `clearOnRead`

### Ext.data.reader.Reader
- Added Configs
   - `groupRootProperty`
   - `summaryRootProperty`

### Ext.dataview.DataView
- Added Configs
   - `selected`
- Added Events
   - `childdoubletap`
   - `childlongpress`
   - `childmouseenter`
   - `childmouseleave`
   - `childsingletap`
   - `childtap`
   - `childtaphold`
   - `childtouchcancel`
   - `childtouchend`
   - `childtouchmove`
   - `childtouchstart`
   - `rowselection`
   - `selectionchange`
- Removed Configs
   - `itemConfig`
   - `maxItemCache`

### Ext.dataview.IndexBar
- Added Configs
   - `animation`
   - `autoHide`
   - `dynamic`
   - `indicator`
- Added Vars
   - `$indexbar-indicator-background-color`
   - `$indexbar-indicator-border-radius`
   - `$indexbar-indicator-color`
   - `$indexbar-indicator-enable-arrow`
   - `$indexbar-indicator-font-size`
   - `$indexbar-indicator-font-size-big`
   - `$indexbar-indicator-font-weight`
   - `$indexbar-indicator-font-weight-big`
   - `$indexbar-indicator-height`
   - `$indexbar-indicator-height-big`
   - `$indexbar-indicator-line-height`
   - `$indexbar-indicator-line-height-big`
   - `$indexbar-indicator-margin`
   - `$indexbar-indicator-spacing`
   - `$indexbar-indicator-width`
   - `$indexbar-indicator-width-big`
   - `$indexbar-justify-items`
- Removed Vars
   - `$indexbar-height`
   - `$indexbar-height-big`
   - `$indexbar-horizontal-height`
   - `$indexbar-horizontal-height-big`

### Ext.dataview.ItemHeader
- Added Configs
   - `group`
   - `tpl`
- Added Vars
   - `$itemheader-box-shadow`
   - `$itemheader-focused-outline-color`
   - `$itemheader-focused-outline-offset`
   - `$itemheader-focused-outline-style`
   - `$itemheader-focused-outline-width`
   - `$itemheader-pinned-border-color`
   - `$itemheader-pinned-bottom-box-shadow`
   - `$itemheader-pinned-box-shadow`

### Ext.dataview.List
- Added Configs
   - `groupFooter`
   - `groupHeader`
   - `minimumBufferDistance`
   - `pinFooters`
   - `pinnedFooter`
   - `preventSelectionOnTool`
   - `variableHeights`
- Added Events
   - `childdoubletap`
   - `childlongpress`
   - `childmouseenter`
   - `childmouseleave`
   - `childsingletap`
   - `childtap`
   - `childtaphold`
   - `childtouchcancel`
   - `childtouchend`
   - `childtouchmove`
   - `childtouchstart`
   - `itemaction`
- Modified Methods
   - `scrollToRecord`
      - Removed _overscroll_ param
- Removed Configs
   - `itemHeight`
   - `refreshHeightOnUpdate`
   - `scrollDock`
   - `striped`
   - `useComponents`

### Ext.dataview.ListItem
- Added Vars
   - `$listitem-focused-background-color`
   - `$listitem-focused-border-color`
   - `$listitem-focused-color`
   - `$listitem-focused-outline-color`
   - `$listitem-focused-outline-offset`
   - `$listitem-focused-outline-style`
   - `$listitem-focused-outline-width`
   - `$listitem-pinned-background-color`
   - `$listitem-pinned-border-color`
   - `$listitem-pinned-bottom-box-shadow`
   - `$listitem-pinned-box-shadow`
   - `$listitem-pinned-color`
- Removed Vars
   Disclosure is now a tool.

   - `$listitem-disclosure-background-color`
   - `$listitem-disclosure-border-radius`
   - `$listitem-disclosure-border-radius-big`
   - `$listitem-disclosure-icon`
   - `$listitem-disclosure-icon-color`
   - `$listitem-disclosure-icon-font-size`
   - `$listitem-disclosure-icon-font-size-big`
   - `$listitem-disclosure-icon-size`
   - `$listitem-disclosure-icon-size-big`
   - `$listitem-disclosure-margin`
   - `$listitem-disclosure-margin-big`
   - `$listitem-disclosure-pressed-background-color`
   - `$listitem-disclosure-pressed-icon-color`
   - `$listitem-pressed-disclosure-background-color`
   - `$listitem-pressed-disclosure-icon-color`

### Ext.dataview.SimpleListItem
- Added Vars
   - `$listitem-focused-outline-color`
   - `$listitem-focused-outline-offset`
   - `$listitem-focused-outline-style`
   - `$listitem-focused-outline-width`
   - `$listitem-pinned-background-color`
   - `$listitem-pinned-border-color`
   - `$listitem-pinned-bottom-box-shadow`
   - `$listitem-pinned-box-shadow`
   - `$listitem-pinned-color`
- Removed Vars
   Disclosure is now a tool.

### Ext.Date
- Added Properties
   - `defaultTimeFormat`

### Ext.Deferred
- Added Static-methods
   - `race`

### Ext.dom.Element
- Added Methods
   - `getClassMap`
   - `getTextSelection`
   - `hover`
   - `indexOf`
   - `isFocusable`
   - `isInputField`
   - `isTabbable`
   - `ripple`
   - `selectable`
   - `selectText`
   - `setClassMap`
   - `swallowEvent`
   - `unselectable`
   - `visit`
- Added Static-methods
   - `isRelativeUnit`
- Modified Methods
   - `isVisible`
      - Added _mode_ param

### Ext.drag.proxy.Placeholder
- Modified Methods
   - `getElement`
      - Added _info_ param
      - Removed _source_ param

### Ext.draw.Container
- Added Configs
   - `downloadServerUrl`
- Modified Methods
   - `download`
      - Modified _config_ param
         - Modified _url_ property
            - **optional** is undefined (was true)

### Ext.draw.Draw
- Added Methods
   - `naturalSpline`

### Ext.draw.modifier.Highlight
- Added Configs
   - `style`
- Removed Configs
   - `highlightStyle`

### Ext.draw.sprite.Composite
- Added Methods
   - `addSprite`
- Modified Methods
   - `add`
      - Modified _sprite_ param
         - **type** is undefined (was Ext.draw.sprite.Sprite/Object)

### Ext.event.Event
- Added Methods
   - `key`

### Ext.Factory
- Added Configs
   - `creator`
   - `typeProperty`
- Added Methods
   - `update`

### Ext.field.Checkbox
- Added Methods
   - `getChecked`
- Added Vars
   - `$checkboxfield-box-label-color`
   - `$checkboxfield-box-label-font-family`
   - `$checkboxfield-box-label-font-size`
   - `$checkboxfield-box-label-font-size-big`
   - `$checkboxfield-box-label-font-weight`
   - `$checkboxfield-box-label-line-height`
   - `$checkboxfield-box-label-line-height-big`
   - `$checkboxfield-box-label-padding`
   - `$checkboxfield-box-label-padding-big`
   - `$checkboxfield-focused-checkbox-color`

### Ext.field.Field
- Added Configs
   - `autoFitErrors`
   - `error`
   - `errorMessage`
   - `errorTarget`
   - `errorTip`
   - `errorTpl`
   - `inline`
   - `labelMinWidth`
   - `requiredMessage`
   - `validateDisabled`
   - `validationMessage`
   - `validators`
- Added Properties
   - `validateOnInit`
- Added Methods
   - `completeEdit`
   - `formatErrors`
   - `isEqual`
   - `isValid`
   - `validate`
- Added Vars
   - `$field-error-icon-side`
   - `$field-error-icon-side-color`
   - `$field-error-icon-side-font-size`
   - `$field-error-icon-side-font-size-big`
   - `$field-error-icon-side-margin`
   - `$field-error-icon-side-margin-big`
   - `$field-error-icon-side-size`
   - `$field-error-icon-side-size-big`
   - `$field-error-icon-under`
   - `$field-error-icon-under-color`
   - `$field-error-icon-under-font-size`
   - `$field-error-icon-under-font-size-big`
   - `$field-error-icon-under-margin`
   - `$field-error-icon-under-margin-big`
   - `$field-error-icon-under-size`
   - `$field-error-icon-under-size-big`
   - `$field-error-message-color`
   - `$field-error-message-font-family`
   - `$field-error-message-font-size`
   - `$field-error-message-font-size-big`
   - `$field-error-message-font-weight`
   - `$field-error-message-line-height`
   - `$field-error-message-line-height-big`
   - `$field-error-under-margin`
   - `$field-error-under-margin-big`
   - `$field-label-min-width`
   - `$field-label-min-width-big`
   - `$field-label-width`
   - `$field-label-width-big`
- Removed Configs
   - `clearIcon` -> Moved to `Ext.field.Text`
   - `inputCls` -> Moved to `Ext.field.Input`
- Removed Vars
   - `$form-field-bg-color`
   - `$form-field-bg-color`
   - `$form-field-height`
   - `$form-field-height`

### Ext.field.File
- Added Methods
   - `getFiles`

### Ext.field.Input
This class has been repurposed to act as a base field class for any field with an input

### Ext.field.Number
- Added Configs
   - `decimals`

### Ext.field.Picker
- Added Configs
   - `edgePicker`
   - `floatedPicker`
   - `picker`

### Ext.field.Radio
- Added Vars
   - `$radiofield-box-label-color`
   - `$radiofield-box-label-font-family`
   - `$radiofield-box-label-font-size`
   - `$radiofield-box-label-font-size-big`
   - `$radiofield-box-label-font-weight`
   - `$radiofield-box-label-line-height`
   - `$radiofield-box-label-line-height-big`
   - `$radiofield-box-label-padding`
   - `$radiofield-box-label-padding-big`
   - `$radiofield-focused-checkbox-color`

### Ext.field.Select
- Added Configs
   - `autoLoadOnValue`
   - `collapseOnSelect`
   - `displayTpl`
   - `hideTrigger`
   - `itemTpl`
   - `multiSelect`
   - `selectOnTab`
   - `valueNotFoundText`
- Added Methods
   - `findRecordByDisplay`
   - `findRecordByValue`
   - `getRecordDisplayData`
- Added Events
   - `select`

### Ext.field.Slider
- Added Vars
   - `$sliderfield-body-width`
   - `$sliderfield-body-width-big`
   - `$sliderfield-box-label-color`
   - `$sliderfield-box-label-font-family`
   - `$sliderfield-box-label-font-size`
   - `$sliderfield-box-label-font-size-big`
   - `$sliderfield-box-label-font-weight`
   - `$sliderfield-box-label-line-height`
   - `$sliderfield-box-label-line-height-big`
   - `$sliderfield-box-label-padding`
   - `$sliderfield-box-label-padding-big`
   - `$sliderfield-padding`
   - `$sliderfield-padding-big`
- Removed Vars
   - `$form-slider-size`
   - `$form-slider-size`
   - `$form-thumb-size`
   - `$form-thumb-size`

### Ext.field.Spinner
- Removed Configs
   - `defaultValue`

### Ext.field.Text
- Added Configs
   - `animateUnderline`
   - `autoHideInputMask`
   - `bodyAlign`
   - `clearable`
   - `editable`
   - `inputMask`
   - `pattern`
   - `placeholder`
- Added Methods
   - `clearValue`
   - `getTextSelection`
- Added Vars
   - `$textfield-alt-ui`
   - `$textfield-animate-underline-duration`
   - `$textfield-body-width`
   - `$textfield-body-width-big`
   - `$textfield-celleditor-ui`
   - `$textfield-faded-ui`
   - `$textfield-focused-input-underline-color`
   - `$textfield-focused-input-underline-width`
   - `$textfield-input-underline-color`
   - `$textfield-input-underline-width`
   - `$textfield-invalid-input-underline-color`
   - `$textfield-invalid-input-underline-width`
   - `$textfield-solo-ui`
- Modified Methods
   - `select`
      - Added _start_ param
      - Added _end_ param
      - Added _direction_ param
- Removed Vars
   - `$textfield-focused-input-border-width`
   - `$textfield-invalid-input-border-width`

### Ext.field.Toggle
- Added Vars
   - `$togglefield-body-width`
   - `$togglefield-body-width-big`
   - `$togglefield-box-label-color`
   - `$togglefield-box-label-font-family`
   - `$togglefield-box-label-font-size`
   - `$togglefield-box-label-font-size-big`
   - `$togglefield-box-label-font-weight`
   - `$togglefield-box-label-line-height`
   - `$togglefield-box-label-line-height-big`
   - `$togglefield-box-label-padding`
   - `$togglefield-box-label-padding-big`
   - `$togglefield-padding`
   - `$togglefield-padding-big`
- Removed Vars
   - `$form-toggle-size`
   - `$form-toggle-size`

### Ext.field.trigger.Trigger
- Added Vars
   - `$trigger-alt-ui`
   - `$trigger-faded-ui`
   - `$trigger-solo-ui`

### Ext.form.FieldSet
- Removed Vars
   - `$form-fieldset-radius`
   - `$form-fieldset-radius`

### Ext.form.Panel
- Removed Vars
   - `$form-bg-color`
   - `$form-bg-color`
   - `$form-dark`
   - `$form-dark`
   - `$form-label-background-color`
   - `$form-label-background-color`
   - `$form-label-width`
   - `$form-label-width`
   - `$form-light`
   - `$form-light`
   - `$form-spacing`
   - `$form-spacing`

### Ext.GlobalEvents
- Added Events
   - `beforeroute`
   - `beforeroutes`
   - `mouseup`

### Ext.grid.cell.Base
- Added Configs
   - `bodyCls`
   - `bodyStyle`
   - `selectable`
- Added Vars
   - `$gridcell-background-color`
   - `$gridcell-color`
   - `$gridcell-column-border-color`
   - `$gridcell-column-border-style`
   - `$gridcell-column-border-width`
   - `$gridcell-focused-outline-color`
   - `$gridcell-focused-outline-offset`
   - `$gridcell-focused-outline-style`
   - `$gridcell-focused-outline-width`
   - `$gridcell-hovered-background-color`
   - `$gridcell-hovered-color`
   - `$gridcell-pressed-background-color`
   - `$gridcell-pressed-color`
   - `$gridcell-selected-background-color`
   - `$gridcell-selected-color`
   - `$gridcell-summary-ui`
- Removed Configs
   - `innerCls`
   - `innerStyle`

### Ext.grid.cell.Check
- Added Vars
   - `$checkcell-focused-checkbox-color`

### Ext.grid.cell.Expander
- Removed Vars
   - `$padding`

### Ext.grid.column.Check
- Added Configs
   - `headerCheckboxAlign`
- Added Vars
   - `$checkcolumn-checkbox-horizontal-spacing`
   - `$checkcolumn-checkbox-horizontal-spacing-big`
   - `$checkcolumn-checkbox-vertical-spacing`
   - `$checkcolumn-checkbox-vertical-spacing-big`
   - `$checkcolumn-focused-checkbox-color`
   - `$checkcolumn-hovered-background-color`
   - `$checkcolumn-resizer-background-color`
   - `$checkcolumn-resizer-width`
   - `$checkcolumn-trigger-background-color`
   - `$checkcolumn-trigger-border-color`
   - `$checkcolumn-trigger-border-style`
   - `$checkcolumn-trigger-border-width`
   - `$checkcolumn-trigger-icon`
   - `$checkcolumn-trigger-icon-color`
   - `$checkcolumn-trigger-icon-font-size`
   - `$checkcolumn-trigger-icon-font-size-big`
   - `$checkcolumn-trigger-width`
   - `$checkcolumn-trigger-width-big`

### Ext.grid.column.Column
- Added Configs
   - `exportRenderer`
   - `exportSummaryRenderer`
   - `groupHeaderTpl`
   - `hideable`
   - `menu`
   - `menuDisabled`
   - `sorter`
   - `summary`
   - `summaryCell`
   - `summaryDataIndex`
- Added Methods
   - `getSortParam`
   - `getVisibleIndex`
- Added Vars
   - `$gridcolumn-hovered-background-color`
   - `$gridcolumn-menu-columns-icon`
   - `$gridcolumn-menu-sort-asc-icon`
   - `$gridcolumn-menu-sort-desc-icon`
   - `$gridcolumn-resizer-width`
   - `$grid-column-resizer-width-big`
   - `$gridcolumn-trigger-background-color`
   - `$gridcolumn-trigger-border-color`
   - `$gridcolumn-trigger-border-style`
   - `$gridcolumn-trigger-border-width`
   - `$gridcolumn-trigger-icon`
   - `$gridcolumn-trigger-icon-color`
   - `$gridcolumn-trigger-icon-font-size`
   - `$gridcolumn-trigger-icon-font-size-big`
   - `$gridcolumn-trigger-width`
   - `$gridcolumn-trigger-width-big`
- Removed Vars
   - `$resizer-background-color`

### Ext.grid.Grid
- Added Configs
   - `columnLines`
   - `columnMenu`
   - `columnResize`
   - `columnsMenuItem`
   - `multiColumnSort`
   - `rowNumbers`
   - `selectable`
   - `sortable`
- Added Events
   - `beforeselectionextend`
   - `cellselection`
   - `columnmenucreated`
   - `columnselection`
   - `selectionextenderdrag`

### Ext.grid.HeaderContainer
- Added Vars
   - `$headercontainer-background-color`

### Ext.grid.Row
- Added Methods
   - `getCells`
- Added Vars
   - `$gridrow-pinned-background-color`
   - `$gridrow-pinned-border-color`
   - `$gridrow-pinned-bottom-box-shadow`
   - `$gridrow-pinned-box-shadow`
   - `$gridrow-pinned-color`

### Ext.grid.RowHeader
- Added Vars
   - `$rowheader-box-shadow`
   - `$rowheader-focused-outline-color`
   - `$rowheader-focused-outline-offset`
   - `$rowheader-focused-outline-style`
   - `$rowheader-focused-outline-width`
   - `$rowheader-pinned-border-color`
   - `$rowheader-pinned-bottom-box-shadow`
   - `$rowheader-pinned-box-shadow`

### Ext.layout.Card
- Added Methods
   - `next`
   - `previous`

### Ext.list.AbstractTreeItem
- Modified Methods
   - `onClick`
      - **access** is protected (was private)

### Ext.list.Tree
- Added Configs
   - `expanderFirst`
- Modified Events
   - `selectionchange`
      - Added _treelist_ param
      - Removed _this_ param

### Ext.list.TreeItem
- Added Vars
   - `$treelist-nav-ui`

### Ext.Media
- Added Configs
   - `controls`

### Ext.mixin.Bindable
- Added Configs
   - `nameable`
   - `shareableName`
- Added Methods
   - `isBound`

### Ext.mixin.Container
- Added Configs
   - `nameHolder`
- Added Methods
   - `getNamedItems`
   - `lookupName`

### Ext.mixin.Inheritable
- Added Methods
   - `isAncestor`
   - `isDescendantOf`

### Ext.mixin.Traversable
- Added Methods
   - `is`
   - `nextNode`
   - `nextSibling`
   - `previousNode`
   - `previousSibling`

### Ext.Panel
- Added Configs
   - `bbar`
   - `bodyStyle`
   - `buttonAlign`
   - `buttons`
   - `buttonToolbar`
   - `collapsed`
   - `collapsible`
   - `headerPosition`
   - `iconAlign`
   - `lbar`
   - `minButtonWidth`
   - `rbar`
   - `resizable`
   - `tbar`
   - `titleAlign`
- Added Methods
   - `close`
   - `collapse`
   - `expand`
   - `toggleCollapsed`
- Added Vars
   - `$panel-anchor-background-color`
   - `$panel-anchor-border-color`
   - `$panel-anchor-margin`
   - `$panel-border-radius-big`
   - `$panel-header-icon-color`
   - `$panel-header-min-height`
   - `$panel-header-min-height-big`
   - `$panel-header-title-padding`
   - `$panel-header-title-padding-big`
   - `$panel-tool-background-color`
   - `$panel-tool-border-radius`
   - `$panel-tool-border-radius-big`
   - `$panel-tool-color`
   - `$panel-tool-cursor`
   - `$panel-tool-disabled-background-color`
   - `$panel-tool-disabled-color`
   - `$panel-tool-disabled-cursor`
   - `$panel-tool-disabled-opacity`
   - `$panel-tool-focused-outline-color`
   - `$panel-tool-focused-outline-offset`
   - `$panel-tool-focused-outline-style`
   - `$panel-tool-focused-outline-width`
   - `$panel-tool-font-size`
   - `$panel-tool-font-size-big`
   - `$panel-tool-hovered-background-color`
   - `$panel-tool-hovered-color`
   - `$panel-tool-hovered-opacity`
   - `$panel-tool-opacity`
   - `$panel-tool-pressed-background-color`
   - `$panel-tool-pressed-color`
   - `$panel-tool-pressed-opacity`
   - `$panel-tool-size`
   - `$panel-tool-size-big`
   - `$panel-tool-spacing`
   - `$panel-tool-spacing-big`
- Modified Vars
   - `$panel-light-ui`
      - **type** is map (was boolean)
- Removed Vars
   - `$include-floating-panels`

### Ext.panel.Header
- Added Configs
   - `titleRotation`

### Ext.panel.Title
- Added Configs
   - `rotateIcon`
   - `rotation`

### Ext.picker.Picker
- Added Configs
   - `side`
- Removed Vars
   - `$picker-active-border-color`
   - `$picker-active-border-color`
   - `$picker-row-height`
   - `$picker-row-height`
   - `$picker-row-height`
   - `$picker-sheet-radius`
   - `$picker-sheet-radius`
   - `$picker-title-bg-color`
   - `$picker-title-bg-color`
   - `$picker-title-color`
   - `$picker-title-color`

### Ext.pivot.dimension.Item
- Added Configs
   - `column`

### Ext.pivot.matrix.Base
- Added Configs
   - `collapsibleColumns`
   - `collapsibleRows`
   - `useNaturalSorting`

### Ext.pivot.plugin.Configurator
- Added Events
   - `applypivotsettings`
   - `beforeapplypivotsettings`
   - `beforeshowpivotsettings`
   - `showpivotsettings`
- Removed Configs
   - `panelWrap`
   - `panelWrapper`

### Ext.pivot.plugin.configurator.Panel
- Added Methods
   - `getAggregateHeader`
   - `getAllFieldsHeader`
   - `getLeftAxisHeader`
   - `getTopAxisHeader`
   - `setAggregateContainerVisible`
   - `setAllFieldsContainerVisible`
   - `setLeftAxisContainerVisible`
   - `setTopAxisContainerVisible`

### Ext.pivot.plugin.DrillDown
- Added Configs
   - `panel`

### Ext.pivot.plugin.RangeEditor
- Removed Configs
   - `panelWrap`
   - `panelWrapper`

### Ext.Promise
- Added Static-methods
   - `race`

### Ext.promise.Promise
- Added Methods
   - `catch`

### Ext.scroll.Scroller
- Modified Methods
   - `scrollBy`
      - Modified _undefined_ return
         - **type** is Ext.Promise (was Ext.scroll.Scroller)
   - `scrollIntoView`
      - Modified _undefined_ return
         - **type** is Ext.Promise (was Ext.scroll.Scroller)
   - `scrollTo`
      - Modified _undefined_ return
         - **type** is Ext.Promise (was Ext.scroll.Scroller)
- Modified Events
   - `scroll`
      - Added _deltaX_ param
      - Added _deltaY_ param
   - `scrollend`
      - Added _deltaX_ param
      - Added _deltaY_ param

### Ext.Sheet
- Added Configs
   - `cover`
   - `reveal`
   - `side`
- Added Vars
   - `$sheet-border-style`
   - `$sheet-border-width`
- Removed Vars
   - `$sheet-bg-color`

### Ext.slider.Thumb
- Added Vars
   - `$thumb-toggle-off-ui`
   - `$thumb-toggle-on-ui`

### Ext.supports
- Added Properties
   - `CannotScrollExactHeight`
   - `XmlQuerySelector`

### Ext.tab.Tab
- Added Configs
   - `closable`
- Added Vars
   - `$tab-active-arrow-icon-color`
   - `$tab-active-close-icon-background-color`
   - `$tab-active-close-icon-color`
   - `$tab-active-close-icon-hovered-background-color`
   - `$tab-active-close-icon-hovered-color`
   - `$tab-active-close-icon-pressed-background-color`
   - `$tab-active-close-icon-pressed-color`
   - `$tab-active-focused-outline-color`
   - `$tab-active-indicator-background-color`
   - `$tab-active-indicator-height`
   - `$tab-arrow-horizontal-spacing`
   - `$tab-arrow-horizontal-spacing-big`
   - `$tab-arrow-icon`
   - `$tab-arrow-icon-color`
   - `$tab-arrow-icon-font-size`
   - `$tab-arrow-icon-font-size-big`
   - `$tab-arrow-icon-size`
   - `$tab-arrow-icon-size-big`
   - `$tab-arrow-vertical-spacing`
   - `$tab-arrow-vertical-spacing-big`
   - `$tab-box-shadow`
   - `$tab-close-icon`
   - `$tab-close-icon-background-color`
   - `$tab-close-icon-border-radius`
   - `$tab-close-icon-border-radius-big`
   - `$tab-close-icon-color`
   - `$tab-close-icon-font-size`
   - `$tab-close-icon-font-size-big`
   - `$tab-close-icon-hovered-background-color`
   - `$tab-close-icon-hovered-color`
   - `$tab-close-icon-margin`
   - `$tab-close-icon-margin-big`
   - `$tab-close-icon-pressed-background-color`
   - `$tab-close-icon-pressed-color`
   - `$tab-close-icon-size`
   - `$tab-close-icon-size-big`
   - `$tab-close-icon-spacing`
   - `$tab-close-icon-spacing-big`
   - `$tab-disabled-arrow-icon-color`
   - `$tab-disabled-background-color`
   - `$tab-disabled-background-gradient`
   - `$tab-disabled-border-color`
   - `$tab-disabled-box-shadow`
   - `$tab-disabled-color`
   - `$tab-disabled-icon-color`
   - `$tab-focused-arrow-icon-color`
   - `$tab-focused-background-color`
   - `$tab-focused-background-gradient`
   - `$tab-focused-border-color`
   - `$tab-focused-box-shadow`
   - `$tab-focused-color`
   - `$tab-focused-icon-color`
   - `$tab-focused-outline-color`
   - `$tab-focused-outline-offset`
   - `$tab-focused-outline-style`
   - `$tab-focused-outline-width`
   - `$tab-hovered-arrow-icon-color`
   - `$tab-hovered-background-color`
   - `$tab-hovered-background-gradient`
   - `$tab-hovered-border-color`
   - `$tab-hovered-box-shadow`
   - `$tab-hovered-color`
   - `$tab-hovered-icon-color`
   - `$tab-icon-only-padding`
   - `$tab-icon-only-padding-big`
   - `$tab-pressed-arrow-icon-color`
   - `$tab-pressed-background-color`
   - `$tab-pressed-background-gradient`
   - `$tab-pressed-border-color`
   - `$tab-pressed-box-shadow`
   - `$tab-pressed-color`
   - `$tab-pressed-icon-color`
   - `$tab-text-transform`
   - `$tab-text-transform-big`
- Removed Vars
   - `$active-icon-color`

### Ext.tip.ToolTip
- Added Vars
   - `$tooltip-anchor-background-color`
   - `$tooltip-anchor-border-color`
   - `$tooltip-anchor-height`
   - `$tooltip-anchor-margin`
   - `$tooltip-anchor-width`
   - `$tooltip-body-background-color`
   - `$tooltip-body-border-color`
   - `$tooltip-body-border-style`
   - `$tooltip-body-border-width`
   - `$tooltip-body-color`
   - `$tooltip-body-font-family`
   - `$tooltip-body-font-size`
   - `$tooltip-body-font-size-big`
   - `$tooltip-body-font-weight`
   - `$tooltip-body-line-height`
   - `$tooltip-body-line-height-big`
   - `$tooltip-body-padding`
   - `$tooltip-body-padding-big`
   - `$tooltip-border-color`
   - `$tooltip-border-radius`
   - `$tooltip-border-radius-big`
   - `$tooltip-border-style`
   - `$tooltip-border-width`
   - `$tooltip-header-background-color`
   - `$tooltip-header-background-gradient`
   - `$tooltip-header-border-color`
   - `$tooltip-header-border-style`
   - `$tooltip-header-border-width`
   - `$tooltip-header-color`
   - `$tooltip-header-font-family`
   - `$tooltip-header-font-size`
   - `$tooltip-header-font-size-big`
   - `$tooltip-header-font-weight`
   - `$tooltip-header-icon-color`
   - `$tooltip-header-icon-font-size`
   - `$tooltip-header-icon-font-size-big`
   - `$tooltip-header-icon-horizontal-spacing`
   - `$tooltip-header-icon-horizontal-spacing-big`
   - `$tooltip-header-icon-opacity`
   - `$tooltip-header-icon-size`
   - `$tooltip-header-icon-size-big`
   - `$tooltip-header-icon-vertical-spacing`
   - `$tooltip-header-icon-vertical-spacing-big`
   - `$tooltip-header-line-height`
   - `$tooltip-header-line-height-big`
   - `$tooltip-header-min-height`
   - `$tooltip-header-min-height-big`
   - `$tooltip-header-padding`
   - `$tooltip-header-padding-big`
   - `$tooltip-header-shadow`
   - `$tooltip-header-title-padding`
   - `$tooltip-header-title-padding-big`
   - `$tooltip-header-z-index`
   - `$tooltip-manage-borders`
   - `$tooltip-tool-background-color`
   - `$tooltip-tool-border-radius`
   - `$tooltip-tool-border-radius-big`
   - `$tooltip-tool-color`
   - `$tooltip-tool-cursor`
   - `$tooltip-tool-disabled-background-color`
   - `$tooltip-tool-disabled-color`
   - `$tooltip-tool-disabled-cursor`
   - `$tooltip-tool-disabled-opacity`
   - `$tooltip-tool-focused-outline-color`
   - `$tooltip-tool-focused-outline-offset`
   - `$tooltip-tool-focused-outline-style`
   - `$tooltip-tool-focused-outline-width`
   - `$tooltip-tool-font-size`
   - `$tooltip-tool-font-size-big`
   - `$tooltip-tool-hovered-background-color`
   - `$tooltip-tool-hovered-color`
   - `$tooltip-tool-hovered-opacity`
   - `$tooltip-tool-opacity`
   - `$tooltip-tool-pressed-background-color`
   - `$tooltip-tool-pressed-color`
   - `$tooltip-tool-pressed-opacity`
   - `$tooltip-tool-size`
   - `$tooltip-tool-size-big`
   - `$tooltip-tool-spacing`
   - `$tooltip-tool-spacing-big`
- Removed Vars
   - `$tip-anchor-height`
   - `$tip-anchor-width`
   - `$tip-background-color`
   - `$tip-body-color`
   - `$tip-body-font-size`
   - `$tip-body-font-weight`
   - `$tip-body-padding`
   - `$tip-border-color`
   - `$tip-border-width`
   - `$tip-header-color`
   - `$tip-header-font-size`
   - `$tip-header-font-weight`
   - `$tip-header-padding`
   - `$tip-tool-color`
   - `$tip-tool-spacing`

### Ext.Toolbar
- Added Vars
   - `$toolbar-footer-ui`
- Removed Vars
   - `$toolbar-spacing`

### Ext.util.FilterCollection
- Added Methods
   - `getFilterCount`

### Ext.util.Format
- Added Methods
   - `resource`

### Ext.util.History
- Added Properties
   - `hashbang`
- Added Methods
   - `replace`

### Ext.util.Positionable
- Modified Methods
   - `getRegion`
      - Added _local_ param

### Ext.ux.google.Map
- Added Configs
   - `markers`
   - `markerTemplate`
- Added Methods
   - `fitMarkersInView`
- Added Events
   - `markerclick`
   - `markerdblclick`
   - `markerdrag`
   - `markerdragend`
   - `markerdragstart`
   - `markermousedown`
   - `markermouseout`
   - `markermouseover`
   - `markermouseup`
   - `markerrightclick`
- Modified Methods
   - `setMapCenter`
      - Modified _coordinates_ param
         - **type** is Object/Ext.data.Model/google.maps.LatLng (was Object/google.maps.LatLng)

### Ext.Video
- Added Configs
   - `showPosterOnPause`

### Ext.viewport.Default
- Modified Methods
   - `hideMenu`
      - Added _animate_ param

### Ext.Widget
- Added Configs
   - `constrainAlign`
   - `disabled`
   - `hideMode`
   - `name`
   - `renderTo`
   - `ripple`
- Added Properties
   - `baseCls`
   - `inheritUi`
   - `onRender`
- Added Methods
   - `addCls`
   - `afterRender`
   - `disable`
   - `enable`
   - `hasCls`
   - `isAncestor`
   - `isDescendantOf`
   - `isDisabled`
   - `isEnabled`
   - `removeCls`
   - `replaceCls`
- Added Events
   - `beforedisabledchange`
   - `disabledchange`
- Modified Configs
   - `flex`
      - **type** is Number/String/Object (was Number)
- Removed Configs
   - `constrainTo`

### Global_CSS
- Added Vars
   - `$accent-color-name`
   - `$base-color-name`
   - `$dark-mode`
   - `$draggable-cursor`
   - `$enable-all-icon-classes`
   - `$enable-color-classes`
   - `$image-search-path`
   - `$include-missing-images`
   - `$ripple-background-color`
   - `$ripple-confirm-background-color`
   - `$ripple-decline-background-color`
   - `$ripple-transition`
   - `$shadow`
- Modified Vars
   - `$font-size`
      - **value** is 13px (was pxToRootPct(13px))
   - `$font-size-big`
      - **value** is 15px (was pxToRootPct(15px))
- Removed Vars
   - `$enable-missing-images`
   - `$include-default-uis`
   - `$include-form-sliders`
   - `$include-html-style`
   - `$page-bg-color`

## Summary
 - 1,049 Classes
 - 2,569 Class Configs
 - 880 Class Properties
 - 54 Class Static Properties
 - 6,887 Class Methods
 - 185 Class Static Methods
 - 559 Class Events
 - 1,424 Class Vars

