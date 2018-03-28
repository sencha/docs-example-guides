# Differences Between Ext JS 6.5.0 Classic and Ext JS 6.2.1 Classic

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
 - Ext.exporter.excel.PivotXlsx
 - Ext.exporter.file.ooxml.excel.*
 - Ext.field.InputMask

## Removed
 - Ext.chart.label.Callout
 - Ext.chart.series.sprite.Box
 - Ext.ux.dashboard.GoogleRssPart
 - Ext.ux.dashboard.GoogleRssView
 - Ext.ux.google.Feeds
 - Ext.ux.GroupTabPanel
 - Ext.ux.GroupTabRenderer

## Modified
### Ext
- Added Methods
   - `getApplication`
   - `getViewportHeight`
   - `getViewportWidth`

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

### Ext.chart.series.Line
- Added Configs
   - `curve`

### Ext.chart.series.Pie3D
- Removed Configs
   - `angleField`

### Ext.chart.series.Series
- Removed Configs
   - `highlightItem`

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
   - `maskDefaults`
- Added Static-methods
   - `from`

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

### Ext.data.BufferedStore
- Added Methods
   - `contains`

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
- Modified Configs
   - `messageProperty`
      - **type** is String/Function (was String)

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
   - `indexOf`
   - `ripple`
   - `selectText`
   - `setClassMap`
- Added Static-methods
   - `isRelativeUnit`
- Modified Methods
   - `hide`
      - Removed _animate_ param
   - `isFocusable`
      - Added _skipVisibility_ param
   - `isVisible`
      - Added _mode_ param
   - `removeCls`
      - Removed _this_ return
   - `replaceCls`
      - Added _remove_ param
      - Added _add_ param
      - Modified _prefix_ param
         - **value** is undefined (was '')
      - Modified _suffix_ param
         - **value** is undefined (was '')
      - Removed _oldName_ param
      - Removed _newName_ param
   - `setHeight`
      - Removed _animate_ param
   - `setHtml`
      - Removed _loadScripts_ param
      - Removed _callback_ param
      - Removed _scope_ param
   - `setOpacity`
      - Removed _animate_ param
   - `setSize`
      - Removed _animate_ param
   - `setVisibilityMode`
      - Modified _mode_ param
         - **type** is Ext.dom.Element.VISIBILITY/Ext.dom.Element.DISPLAY/Ext.dom.Element.OFFSETS/Ext.dom.Element.CLIP/Ext.dom.Element.OPACITY (was Ext.dom.Element.VISIBILITY/Ext.dom.Element.DISPLAY/Ext.dom.Element.OFFSETS/Ext.dom.Element.CLIP)
   - `setVisible`
      - Removed _animate_ param
   - `setWidth`
      - Removed _animate_ param
   - `show`
      - Removed _animate_ param
   - `swallowEvent`
      - Modified _undefined_ return
         - **type** is Object (was Ext.dom.Element)
            - Added _destroy_ property
   - `toggle`
      - Removed _animate_ param

### Ext.drag.proxy.Placeholder
- Modified Methods
   - `getElement`
      - Added _info_ param
      - Removed _source_ param

### Ext.drag.Target
- Added Configs
   - `validCls`

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

### Ext.form.field.Text
- Added Configs
   - `autoHideInputMask`
   - `inputMask`
- Added Methods
   - `getTextSelection`
- Modified Methods
   - `selectText`
      - Added _direction_ param
      - Added _undefined_ return

### Ext.GlobalEvents
- Added Events
   - `beforeroute`
   - `beforeroutes`
   - `mouseup`

### Ext.grid.column.Action
- Added Configs
   - `isActionDisabled`

### Ext.grid.column.Column
- Added Configs
   - `exportRenderer`
   - `exportSummaryRenderer`

### Ext.grid.feature.Grouping
- Added Configs
   - `collapseTip`
   - `expandTip`

### Ext.grid.header.Container
- Added Methods
   - `isSealed`

### Ext.grid.plugin.BufferedRenderer
- Added Methods
   - `getNewFocusTarget`

### Ext.layout.container.Accordion
- Added Vars
   - `$accordion-header-focus-background-color`
   - `$accordion-header-focus-color`
   - `$accordion-header-focus-outline-color`
   - `$accordion-header-focus-outline-offset`
   - `$accordion-header-focus-outline-style`
   - `$accordion-header-focus-outline-width`
   - `$accordion-tool-focus-background-color`
   - `$accordion-tool-focus-background-image`
   - `$accordion-tool-focus-color`
   - `$accordion-tool-focus-outline-color`
   - `$accordion-tool-focus-outline-offset`
   - `$accordion-tool-focus-outline-style`
   - `$accordion-tool-focus-outline-width`
- Modified Vars
   - `$accordion-header-color`
      - **value** is $panel-header-color (was #000)
   - `$accordion-tool-glyph-color`
      - **value** is $tool-glyph-color (was $base-color)

### Ext.layout.container.boxOverflow.Scroller
- Modified Events
   - `scroll`
      - Removed _animate_ param

### Ext.list.Tree
- Added Configs
   - `expanderFirst`

### Ext.list.TreeItem
- Added Vars
   - `$treelist-nav-ui`

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

### Ext.panel.Panel
- Added Vars
   - `$panel-header-focus-background-color`
   - `$panel-header-focus-color`
   - `$panel-header-focus-outline-color`
   - `$panel-header-focus-outline-offset`
   - `$panel-header-focus-outline-style`
   - `$panel-header-focus-outline-width`
   - `$panel-tool-focus-background-color`
   - `$panel-tool-focus-background-image`
   - `$panel-tool-focus-color`

### Ext.panel.Table
- Added Methods
   - `setSelection`
- Added Events
   - `filteractivate`
   - `filterdeactivate`
- Modified Methods
   - `ensureVisible`
      - Modified _options_ param
         - Added _column_ property

### Ext.pivot.dimension.Item
- Added Configs
   - `column`
- Added Methods
   - `getConfiguration`

### Ext.pivot.Grid
- Added Vars
   - `$pivot-grid-grand-total-background-color`
   - `$pivot-grid-group-total-background-color`
- Modified Vars
   - `$pivot-grid-group-header-background-color`
      - **value** is transparent (was mix(#fff, $neutral-color, 68%))

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
- Modified Events
   - `applyconfigfieldsettings`
      - Modified _config_ param
         - Added _container_ property
         - Removed _window_ property

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

### Ext.slider.Multi
- Added Configs
   - `thumbPerValue`
- Added Methods
   - `removeThumb`
- Modified Properties
   - `defaultBindProperty`
      - **value** is 'value' (was 'values')
- Modified Events
   - `beforechange`
      - Modified _newValue_ param
         - **type** is Number/null (was Number)
      - Modified _oldValue_ param
         - **type** is Number/null (was Number)
      - Added _thumb_ param
      - Added _type_ param
   - `change`
      - Modified _newValue_ param
         - **type** is Number/null (was Number)
      - Modified _thumb_ param
         - **type** is Ext.slider.Thumb/null (was Ext.slider.Thumb)
      - Added _type_ param

### Ext.supports
- Added Properties
   - `CannotScrollExactHeight`
   - `XmlQuerySelector`

### Ext.toolbar.Toolbar
- Added Configs
   - `trackMenus`

### Ext.util.Cache
- Removed Methods
   - `each`

### Ext.util.ClickRepeater
- Added Configs
   - `handler`
   - `scope`
   - `target`
- Modified Configs
   - `el`
      - **optional** is true
- Modified Methods
   - `constructor`
      - Removed _el_ param
- Removed Methods
   - `disable`
   - `enable`
   - `setDisabled`

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
   - `alignTo`
      - Added _element_ param
      - Added _position_ param
      - Removed _anchorToEl_ param
      - Removed _alignment_ param
      - Removed _animate_ param
   - `getRegion`
      - Added _local_ param
   - `move`
      - Removed _animate_ param
   - `setBox`
      - Removed _animate_ param
   - `setX`
      - Removed _animate_ param
   - `setXY`
      - Removed _animate_ param
   - `setY`
      - Removed _animate_ param

### Ext.ux.rating.Picker
- Added Configs
   - `tip`
- Removed Configs
   - `tooltip`

### Ext.view.AbstractView
- Added Methods
   - `setSelection`

### Ext.Widget
- Added Configs
   - `disabled`
   - `hideMode`
   - `name`
   - `renderTo`
   - `ripple`
- Added Properties
   - `baseCls`
- Added Methods
   - `addCls`
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
- Modified Methods
   - `toggleCls`
      - Added _this_ return
- Removed Configs
   - `baseCls`

### Ext.window.Window
- Added Properties
   - `closeToolText`

### Global_CSS
- Added Vars
   - `$ripple-background-color`
   - `$ripple-confirm-background-color`
   - `$ripple-decline-background-color`
   - `$ripple-transition`

## Summary
 - 1,228 Classes
 - 3,590 Class Configs
 - 1,582 Class Properties
 - 67 Class Static Properties
 - 10,511 Class Methods
 - 198 Class Static Methods
 - 857 Class Events
 - 2,044 Class Vars