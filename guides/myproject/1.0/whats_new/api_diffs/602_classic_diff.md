<style>
.toc-page{
     display:none !important;
}
</style>

#Differences Between Ext JS 6.0.2 Classic and Ext JS 6.0.1 Classic

We believe developers can glean a lot of useful information by evaluating these diff guides when upgrading their 
applications. That said, these reports are automated and may not always accurately depict change in these early 
releases. Unwanted change may be indicated due to doc updates, formatting omissions, etc. We will review and adjust 
these guides for accuracy prior our GA release. In the meantime, please evaluate these diffs knowing that some level of 
inaccuracy may exist. If you see anything in this report that is incorrect or undesirable, please report them on the 
Ext JS 6 forums.

# Added

 - Ext.ux.grid.plugin.AutoSelector
 - Ext.chart.sprite.Label

# Removed

 - Ext.chart.label.Label
 - Ext.chart.TipSurface

# Modified

## Ext

*   Added
    *   method
        *   resolveResource
    *   property
        *   isEdge
        
## Ext.Component

*   Modified
    *   method
        *   addPlugin
            *   6.0.1
                *   private is true
                *   protected is false
            *   6.0.2
                *   private is false
                *   protected is true
*   Removed
    *   method
        *   beforeComponentLayout

## Ext.Number

*   Added
    *   method
        *   isEqual
        *   log10

## Ext.app.Application

*   Modified
    *   config
        *   mainView
            *   6.0.1
                *   type is String/Object
            *   6.0.2
                *   type is String/Object/Ext.Component

## Ext.button.Button

*   6.0.1
    *   mixins is [Ext.mixin.Queryable, Ext.util.KeyboardInteractive]
*   6.0.2
    *   mixins is [Ext.mixin.Queryable]

## Ext.dashboard.Panel

*   Modified
    *   config
        *   animCollapse
            *   6.0.1
                *   type is Boolean
            *   6.0.2
                *   type is Boolean/Number

## Ext.data.ResultSet

*   Added
    *   config
        *   metadata

## Ext.data.Store

*   Modified
    *   method
        *   onProxyLoad
            *   6.0.1
                *   private is true
                *   protected is false
            *   6.0.2
                *   private is false
                *   protected is true

## Ext.data.TreeStore

*   Added
    *   config
        *   filterer
*   Modified
    *   method
        *   onProxyLoad
            *   6.0.1
                *   private is true
                *   protected is false
            *   6.0.2
                *   private is false
                *   protected is true

## Ext.data.proxy.Direct

*   Modified
    *   method
        *   abort
            *   6.0.1
                *   private is true
            *   6.0.2
                *   private is false

## Ext.dd.DragTracker

*   Added
    *   method
        *   onCancel

## Ext.draw.gradient.Gradient

*   Modified
    *   method
        *   generateGradient
            *   6.0.1
                *   return type is Object
            *   6.0.2
                *   return type is CanvasGradient/Ext.draw.engine.SvgContext.Gradient/Ext.draw.Color.NONE

## Ext.draw.gradient.Linear

*   Modified
    *   method
        *   generateGradient
            *   6.0.1
                *   return type is Object
            *   6.0.2
                *   return type is CanvasGradient/Ext.draw.engine.SvgContext.Gradient/Ext.draw.Color.NONE

## Ext.draw.gradient.Radial

*   Modified
    *   method
        *   generateGradient
            *   6.0.1
                *   return type is Object
            *   6.0.2
                *   return type is CanvasGradient/Ext.draw.engine.SvgContext.Gradient/Ext.draw.Color.NONE

## Ext.enums.Plugin

*   Added
    *   property
        *   gridautoselector

## Ext.form.field.Base

*   Added
    *   cssVar
        *   $form-field-focus-border-style
        *   $form-field-focus-border-width

## Ext.form.field.Checkbox

*   Modified
    *   cssVar
        *   $form-checkbox-label-font-size
            *   6.0.1
                *   default value is dynamic ( $form-label-font-family )
            *   6.0.2
                *   default value is dynamic ( $form-label-font-size )

## Ext.form.field.Display

*   Added
    *   cssVar
        *   $form-display-field-focus-border-color
        *   $form-display-field-focus-border-style
        *   $form-display-field-focus-border-width
        *   $form-toolbar-display-field-focus-border-color
        *   $form-toolbar-display-field-focus-border-style
        *   $form-toolbar-display-field-focus-border-width

## Ext.form.field.Text

*   Added
    *   cssVar
        *   $form-toolbar-tag-field-item-margin
        *   $form-toolbar-tag-field-padding
        *   $grid-cell-tag-field-item-margin
        *   $grid-cell-tag-field-padding
        *   $include-tag-field-grid-ui
        *   $include-tag-field-toolbar-ui

## Ext.grid.header.Container

*   Modified
    *   method
        *   getScrollable
            *   6.0.1
                *   return type is Boolean/String/Object
            *   6.0.2
                *   return type is Object

## Ext.grid.plugin.CellEditing

*   Added
    *   method
        *   resume
        *   suspend
*   Modified
    *   method
        *   deactivate
            *   6.0.1
                *   private is true
                *   protected is false
            *   6.0.2
                *   private is false
                *   protected is true

## Ext.grid.plugin.RowEditing

*   Added
    *   method
        *   resume
        *   suspend

## Ext.layout.container.Absolute

*   Removed
    *   config
        *   ignoreOnContentChange

## Ext.list.Tree

*   Modified
    *   method
        *   getMicro
            *   6.0.1
                *   return type is Object
            *   6.0.2
                *   return type is Boolean

## Ext.panel.Panel

*   Modified
    *   config
        *   animCollapse
            *   6.0.1
                *   type is Boolean
            *   6.0.2
                *   type is Boolean/Number
        *   title
            *   6.0.1
                *   type is String
            *   6.0.2
                *   type is String/Object

## Ext.pivot.filter.Base

*   Added
    *   config
        *   type

## Ext.pivot.matrix.Base

*   Added
    *   config
        *   type

## Ext.tab.Tab

*   Modified
    *   config
        *   closeText
            *   6.0.1
                *   default value is 'Close Tab'
            *   6.0.2
                *   default value is "removable"

## Ext.tree.View

*   Added
    *   cssVar
        *   $tree-arrow-glyph-rtl

## Ext.window.MessageBox

*   Modified
    *   config
        *   title
            *   6.0.1
                *   type is String
            *   6.0.2
                *   type is String/Object

## Ext.window.Window

*   Added
    *   cssVar
        *   $window-force-header-border
*   Modified
    *   config
        *   animateTarget
            *   6.0.1
                *   type is String/Ext.dom.Element
            *   6.0.2
                *   type is String/Ext.dom.Element/Ext.Component/Boolean
    *   property
        *   focusable
            *   6.0.1
                *   default value is false
            *   6.0.2
                *   default value is true
*   Removed
    *   cssVar
        *   $ui-force-header-border
