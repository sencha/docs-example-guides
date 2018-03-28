# Diff between Ext JS 6.5.0 and Ext JS 6.5.1 (classic)

While we believe these guides are extremely helpful to developers planning to upgrade their applications,
please be aware that the content is generated from documentation and may not always perfectly describe
the actual code changes in the release. Incorrect changes may be indicated due to comment updates, formatting
omissions, etc..

If you see anything suspicious or inaccurate in this report, please report the problem on the
[Forums](https://www.sencha.com/forum/forumdisplay.php?132-Ext-JS-Community-Forums-6-x) or to
[Sencha Support](https://support.sencha.com/).

## Removed Classes

- Ext.chart.interactions.RotatePie3D (merged with Ext.chart.interactions.Rotate)

## Modified Classes


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

### Ext.EventManager
- Modified Methods
  - getId
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - getPageX
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - getPageXY
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - getPageY
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - getRelatedTarget
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - getTarget
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - onWindowUnload
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - preventDefault
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - purgeElement
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - removeAll
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - removeResizeListener
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - removeUnloadListener
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - resolveTextNode
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - stopEvent
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>
  - stopPropagation
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This method is deprecated.
      </ins>      </code></pre>

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

### Ext.form.field.Base
- Modified Configs
  - formatText
    - deprecatedMessage
      <pre><code><del>undefined</del>
      <ins>This config is deprecated.
      </ins>      </code></pre>

### Ext.form.field.Text
- Modified Configs
  - size
    - deprecatedMessage
      <pre><code><del>use {@link #cfg!width #width} instead.
      </del>
      <ins>Please use {@link #cfg!width #width} instead.
      </ins>      </code></pre>

### Ext.GlobalEvents
- Added Events
  - routereject

### Ext.grid.locking.View
- Modified Methods
  - setActionableMode
    - Added Params
      - position

### Ext.grid.selection.Cells
- Modified Methods
  - setRangeStart
    - Added Params
      - endCell

### Ext.list.Tree
- Added Configs
  - floatLeafItems

### Ext.menu.Menu
- Added Configs
  - focusOnToFront

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

### Ext.Number
- Added Methods
  - parseFloat
  - parseInt
  - roundToPrecision
  - truncateToPrecision

### Ext.panel.Panel
- Added Configs
  - maintainTitlePosition
  - titlePosition

### Ext.panel.Table
- Added Configs
  - preciseHeight

### Ext.picker.Date
- Added Configs
  - defaultValue

### Ext.pivot.Aggregators
- Added Methods
  - countNumbers

### Ext.pivot.filter.Base
- Modified Configs
  - operator
    - required
      <pre><code><del>undefined</del>
      <ins>true</ins>      </code></pre>

### Ext.pivot.matrix.Base
- Added Configs
  - calculateAsExcel

### Ext.plugin.Manager
- Modified Methods
  - create
    - Added Params
      - host

### Ext.selection.RowModel
- Added Configs
  - deselectOnContainerClick

### Ext.supports
- Added Properties
  - accessibility
- Removed Properties
  - HighContrastMode

### Ext.tab.Bar
- Modified Configs
  - maxTabWidth
    - deprecatedMessage
      <pre><code><del>This config is deprecated. It is much easier to use the {@link Ext.tab.Panel#cfg!maxTabWidth maxTabWidth} config on the TabPanel.
      </del>
      <ins>This config is deprecated. Please use the
      {@link Ext.tab.Panel#cfg!maxTabWidth maxTabWidth} config on the TabPanel.
      </ins>      </code></pre>
  - minTabWidth
    - deprecatedMessage
      <pre><code><del>This config is deprecated. It is much easier to use the {@link Ext.tab.Panel#cfg!minTabWidth minTabWidth} config on the TabPanel.
      </del>
      <ins>This config is deprecated. Please use the
      {@link Ext.tab.Panel#cfg!minTabWidth minTabWidth} config on the TabPanel.
      </ins>      </code></pre>

### Ext.window.Window
- Added Configs
  - closeToolText

## SDK Totals

- 1,147 Classes
- 3,918 Configs
- 1,364 Properties
- 71 Static Properties
- 6,028 Methods
- 200 Static Methods
- 873 Events
- 2,052 Vars
- 42 Sass Mixins
