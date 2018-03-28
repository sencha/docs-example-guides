# Diff between Ext JS 6.5.0 and Ext JS 6.5.1 (modern)

While we believe these guides are extremely helpful to developers planning to upgrade their applications,
please be aware that the content is generated from documentation and may not always perfectly describe
the actual code changes in the release. Incorrect changes may be indicated due to comment updates, formatting
omissions, etc..

If you see anything suspicious or inaccurate in this report, please report the problem on the
[Forums](https://www.sencha.com/forum/forumdisplay.php?132-Ext-JS-Community-Forums-6-x) or to
[Sencha Support](https://support.sencha.com/).

## Modified Classes

### Ext.app.Application

- Removed Configs
  - router

### Ext.app.bind.Binding

- Removed Configs
  - twoWay

### Ext.app.bind.Template (private)

- Added Configs
  - escapes (private)

### Ext.Array

- Modified Methods
  - each
      - Modified Params
        - undefined
          - type is **Boolean/Number** (was *Boolean*)

### Ext.chart.AbstractChart

- Modified Configs
  - animation
    - value is **true** (was *!Ext.isIE8*)

### Ext.chart.series.Line

- Modified Configs
  - selectionTolerance
    - value is **20** (was *5*)

### Ext.chart.Util (private)

- Modified Methods
  - validateRange (private)
      - Modified Params
        - defaultRange
          - optional is **true** (was *undefined*)
          - value is **[0, 1]** (was *undefined*)

### Ext.dataview.Abstract (private)

- Added Configs
  - itemButtonMode

### Ext.field.ComboBox

- Removed Configs
  - autoFocus
  - autoFocusLast
  - clearFilterOnBlur
- Modified Configs
  - minChars
    - value is **null** (was *false*)

### Ext.field.Select

- Added Configs
  - autoFocus
  - autoFocusLast
- Removed Configs
  - collapseOnSelect
- Modified Configs
  - autoSelect
    - value is **false** (was *true*)
    - type is **Boolean/'initial'** (was *Boolean*)

### Ext.grid.cell.Cell

- Modified Configs
  - renderer
      - Added Properties
        - value
        - record
        - dataIndex
        - cell
        - column
        - return
      - Removed Returns
        - undefined
      - Removed Params
        - renderer

### Ext.grid.column.Column

- Modified Configs
  - renderer
      - Added Properties
        - value
        - record
        - dataIndex
        - cell
        - column
        - return
      - Removed Returns
        - undefined
      - Removed Params
        - renderer
  - summaryRenderer
      - Added Properties
        - context
      - Removed Params
        - summaryRenderer
  - summaryType
    - deprecatedMessage
      **is**
      **<pre><code>Use {@link #cfg!summary} or {@link #cfg!summaryRenderer} instead.</code></pre>**
      *was*
      *<pre><code>Use {@link #cfg!summary} or {@link #cfg!summaryRenderer}
      instead.</code></pre>*

### Ext.Mixin (protected) (protected *was public*)

### Ext.mixin.Bindable (private)

- Modified Configs
  - bind
    - optional is **true** (was *undefined*)

### Ext.scroll.Scroller

- mixins
  **is**
  **<pre><code>Ext.mixin.Factoryable,Ext.mixin.Bufferable</code></pre>**
  *was*
  *<pre><code>Ext.mixin.Factoryable</code></pre>*

### Ext.tab.Panel

- Modified Configs
  - tabBarPosition
    - type is **String** (was *'top'/'bottom'/'left'/'right'*)

### Ext.Tool

- Added Configs
  - passive

## SDK Totals

- 1,019 Classes
- 3,404 Configs
- 1,078 Properties
- 58 Static Properties
- 4,484 Methods
- 191 Static Methods
- 658 Events
- 2,332 Vars
- 91 Sass Mixins
