# Diff between Ext JS 6.5.0 and Ext JS 6.5.1 (modern)

While we believe these guides are extremely helpful to developers planning to upgrade their applications,
please be aware that the content is generated from documentation and may not always perfectly describe
the actual code changes in the release. Incorrect changes may be indicated due to comment updates, formatting
omissions, etc..

If you see anything suspicious or inaccurate in this report, please report the problem on the
[Forums](https://www.sencha.com/forum/forumdisplay.php?132-Ext-JS-Community-Forums-6-x) or to
[Sencha Support](https://support.sencha.com/).

## Added Classes

- Ext.field.Display
- Ext.grid.plugin.Clipboard
- Ext.layout.overflow.Scroller
- Ext.panel.YearPicker
- Ext.plugin.TabGuard

## Removed Classes

- Ext.chart.interactions.RotatePie3D (merged with Ext.chart.interactions.Rotate)

## Modified Classes

### Ext.Button

- Added Configs
  - stretchMenu

### Ext.calendar.form.CalendarPicker

- Added Vars
  - $calendarpicker-icon-width

### Ext.calendar.header.Days

- Added Configs
  - format

### Ext.calendar.header.Weeks

- Added Configs
  - format

### Ext.calendar.panel.Day

- Modified Configs
  - visibleDays
    - value is **4** (was *undefined*)

### Ext.calendar.panel.Panel

- Added Configs
  - switcher

### Ext.calendar.panel.Week

- Modified Configs
  - visibleDays
    - value is **7** (was *undefined*)

### Ext.calendar.view.Week

- Added Configs
  - visibleDays

### Ext.chart.axis.Axis

- Removed Configs
  - increment
  - labelInSpan

### Ext.chart.interactions.Rotate

- alias
  **is**
  **<pre><code>interaction.rotate,interaction.rotatePie3d</code></pre>**
  *was*
  *<pre><code>interaction.rotate</code></pre>*
- alternateClassNames is **Ext.chart.interactions.RotatePie3D** (was *undefined*)

### Ext.chart.legend.SpriteLegend

- Added Configs
  - marker

### Ext.chart.navigator.Navigator

- Added Configs
  - span

### Ext.chart.series.Bar3D

- Added Properties
  - reversedSpriteZOrder

### Ext.chart.series.Line

- Modified Configs
  - selectionTolerance
    - value is **5** (was *20*)

### Ext.chart.series.sprite.Cartesian

- extends is **Ext.chart.series.sprite.Series** (was *Ext.draw.sprite.Sprite*)

### Ext.chart.series.sprite.Polar

- extends is **Ext.chart.series.sprite.Series** (was *Ext.draw.sprite.Sprite*)

### Ext.chart.Util

- Modified Methods
  - validateRange
      - Modified Params
        - padding
          - value is **0.5** (was *1*)

### Ext.Component

- Added Configs
  - userSelectable

### Ext.Container

- Modified Configs
  - defaultType
    - value is **container** (was *null*)

### Ext.d3.hierarchy.TreeMap

- Modified Configs
  - leafTile
      - Modified Properties
        - label
            - Added Properties
              - offset

### Ext.data.AbstractStore

- Added Configs
  - reloadOnClearSorters

### Ext.data.field.Field

- Modified Configs
  - serialize
      - Added Params
        - value
        - record

### Ext.data.Types

- Added Properties
  - BOOLEAN
  - INTEGER
  - NUMBER

### Ext.data.validator.Range

- Added Configs
  - bothMessage
  - maxOnlyMessage
  - minOnlyMessage

### Ext.dataview.Abstract

- Added Configs
  - markDirty
  - publishes
- Modified Configs
  - enableTextSelection
    - deprecatedMessage
      <pre><code>Use {@link Ext.Component#cfg!userSelectable Ext.Component#userSelectable} instead.</code></pre>

### Ext.dataview.NavigationModel

- Modified Methods
  - setLocation
      - Modified Params
        - options
            - Added Properties
              - animation

### Ext.dataview.SimpleListItem

- Modified Sass-mixins
  - listitem-ui
      - Added Params
        - $selected-font-size
        - $selected-font-size-big
        - $pressed-font-size
        - $pressed-font-size-big

### Ext.direct.PollingProvider

- Modified Configs
  - url
    - deprecatedMessage
      <pre><code>Using Function `{@link #cfg!url url}` is deprecated, please use {@link #cfg!pollFn #pollFn} instead</code></pre>

### Ext.dom.Helper

- Modified Methods
  - createDom
      - Added Params
        - parentNode
  - createHtml
    - deprecatedMessage
      <pre><code>Please use {@link #method!markup #markup} instead.</code></pre>

### Ext.draw.Matrix

- Modified Methods
  - equals
    - deprecatedMessage
      <pre><code>This method is deprecated.</code></pre>

### Ext.event.Event

- Added Methods
  - getClipboardData

### Ext.exporter.data.Base

- Added Configs
  - autoGenerateKey

### Ext.exporter.data.Cell

- Added Configs
  - style

### Ext.exporter.data.Table

- extends is **Ext.exporter.data.Group** (was *Ext.exporter.data.Base*)

- Added Configs
  - rows
  - summaries

### Ext.field.Container

- Modified Configs
  - defaultType
    - value is **container** (was *null*)

### Ext.field.Number

- Added Configs
  - decimalsText
  - inputType
  - maxValueText
  - minValueText
  - trim

### Ext.field.Picker

- Added Configs
  - alignTarget
  - hideTrigger

### Ext.field.Spinner

- Modified Configs
  - stepValue
    - value is **1** (was *0.1*)

### Ext.field.Text

- Added Configs
  - badFormatMessage

### Ext.field.trigger.Trigger

- Added Configs
  - focusOnTap

### Ext.GlobalEvents

- Added Events
  - routereject

### Ext.grid.cell.Expander

- Added Sass-mixins
  - expandercell-ui

### Ext.grid.column.Column

- Added Configs
  - depends
- Modified Configs
  - defaultEditor
    - value
      **is**
      **<pre><code>{}</code></pre>**
      *was*
      *<pre><code>{
          xtype: 'textfield',
          required: true
      }</code></pre>*
  - sorter
    - value is **true** (was *null*)

### Ext.grid.plugin.CellEditing

- Added Configs
  - selectOnEdit

### Ext.grid.RowBody

- Modified Sass-mixins
  - rowbody-ui
      - Added Params
        - $padding

### Ext.layout.Box

- Added Configs
  - overflow
  - wrap

### Ext.layout.Card

- Added Configs
  - deferRender

### Ext.list.Tree

- Added Configs
  - floatLeafItems

### Ext.menu.CheckItem

- Added Configs
  - value

### Ext.menu.Menu

- Added Configs
  - groups

### Ext.menu.RadioItem

- Added Configs
  - name

### Ext.mixin.Inheritable

- Added Methods
  - bubble
- Modified Methods
  - onInheritedAdd
      - Added Params
        - parent

### Ext.mixin.ItemRippler

- Modified Configs
  - itemRipple
      - Added Properties
        - color

### Ext.mixin.Selectable

- Added Configs
  - publishes

### Ext.Number

- Added Methods
  - parseFloat
  - parseInt
  - roundToPrecision
  - truncateToPrecision

### Ext.panel.Date

- Added Configs
  - captionFormat
  - headerFormat
  - hideCaptions
  - hideOutside
  - navigationPosition
  - selectOnNavigate
  - specialDays
  - splitTitle
  - titleAnimation
  - yearPicker
  - yearPickerDefaults
- Removed Configs
  - monthYearFormat
  - paneCaptionFormat

### Ext.pivot.Aggregators

- Added Methods
  - countNumbers

### Ext.pivot.matrix.Base

- Added Configs
  - calculateAsExcel

### Ext.pivot.plugin.configurator.DropZone

- Added Methods
  - getCursorElement

### Ext.pivot.plugin.configurator.FieldSettings

- Modified Configs
  - aggregators

### Ext.pivot.plugin.DrillDown

- Added Configs
  - pageSize

### Ext.slider.Toggle

- Added Configs
  - value

### Ext.supports

- Added Properties
  - accessibility
- Removed Properties
  - HighContrastMode

### Ext.tab.Bar

- Added Configs
  - defaultType
  - layout

### Ext.tip.Manager

- Added Configs
  - overflowTip

### Ext.Toast

- Added Configs
  - maxQueue

### Ext.viewport.Android

- Added Properties
  - preventPullRefresh

### Ext.viewport.Default

- Added Configs
  - swipeThreshold

### Ext.Widget

- Added Configs
  - selfAlign

## SDK Totals

- 1,018 Classes
- 3,275 Configs
- 1,046 Properties
- 59 Static Properties
- 4,478 Methods
- 190 Static Methods
- 658 Events
- 2,332 Vars
- 91 Sass Mixins

