# Diff between Ext JS 6.5.0 and Ext JS 6.5.1 (classic)

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

### Ext.event.publisher.Focus (private)

- extends is **Ext.event.publisher.Dom** (was *Ext.event.publisher.Dom,Object*)

### Ext.form.field.Text

- Added Configs
  - autoHideInputMask
  - inputMask
- Removed Configs
  - growAppend

### Ext.Mixin (protected) (protected *was public*)

### Ext.mixin.Bindable (private)

- Modified Configs
  - bind
    - optional is **true** (was *undefined*)

### Ext.panel.Panel

- Modified Configs
  - title
    - localdoc
      <pre><code>When a `title` is specified, the {@link Ext.panel.Header} will
      <del>automatically be created and displayed unless {@link #header} is set to
      `false`.</del>
      <ins>automatically be created and displayed unless {@link #header} is set to `false`.</ins>
      </code></pre>

### Ext.scroll.Scroller

- mixins
  **is**
  **<pre><code>Ext.mixin.Factoryable,Ext.mixin.Bufferable</code></pre>**
  *was*
  *<pre><code>Ext.mixin.Factoryable</code></pre>*

### Ext.ux.colorpick.ColorUtils (private)

- Modified Methods
  - parseColor
    - Param Changes
      - alphaFormat (new)

### Ext.ux.colorpick.Selection (private)

- Added Configs
  - alphaDecimalFormat
- Modified Configs
  - format
    - type
      **is**
      **<pre><code>"hex6"/"hex8"/"#hex6"/"#hex8"/"rgb"/"rgba"/"HEX6"/"HEX8"/"#HEX6"/"#HEX8"/"RGB"/"RGBA"</code></pre>**
      *was*
      *<pre><code>"hex6"/"hex8"/"#hex6"/"#hex8"/"HEX6"/"HEX8"/"#HEX6"/"#HEX8"</code></pre>*

### Ext.window.MessageBox

- Added Configs
  - cfg.maskClickAction
- Removed Configs
  - closeAction
  - cls
  - constrain
  - hideMode
  - layout
  - maxHeight
  - maxWidth
  - minHeight
  - minWidth
  - resizable
  - scrollable
  - shrinkWrapDock
  - title

### Ext.ZIndexManager

- Removed Methods
  - onCollectionSort (private)

## SDK Totals

- 1,148 Classes
- 4,115 Configs
- 1,390 Properties
- 70 Static Properties
- 6,035 Methods
- 201 Static Methods
- 873 Events
- 2,052 Vars
- 42 Sass Mixins
