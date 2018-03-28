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
        *   fromElement
            *   6.0.1
                *   private is true
                *   return type is void
            *   6.0.2
                *   private is false
                *   return type is Ext.Component/null
                
## Ext.Container

*   Modified
    *   config
        *   control
            *   6.0.1
                *   default value is {}
            *   6.0.2
                *   default value is null
                
## Ext.MessageBox

*   Modified
    *   method
        *   getIconCls
            *   6.0.1
                *   return type is Object
            *   6.0.2
                *   return type is String
                
## Ext.Number

*   Added
    *   method
        *   isEqual
        *   log10
        
## Ext.Panel

*   Added
    *   cssMixin
        *   panel-ui
        
*   Modified
    *   config
        *   header
            *   6.0.1
                *   private is true
                *   type is Object
            *   6.0.2
                *   private is false
                *   type is Boolean/Object
        *   icon
            *   6.0.1
                *   private is true
                *   type is Object
            *   6.0.2
                *   private is false
                *   type is String
        *   iconCls
            *   6.0.1
                *   private is true
                *   type is Object
            *   6.0.2
                *   private is false
                *   type is String
        *   title
            *   6.0.1
                *   private is true
                *   type is Object
            *   6.0.2
                *   private is false
                *   type is String/Object
        *   tools
            *   6.0.1
                *   private is true
                *   type is Object
            *   6.0.2
                *   private is false
                *   type is Object[]/Ext.panel.Tool[]                
*   Removed
    *   cssVar
        *   $header-icon-opacity
        
## Ext.SegmentedButton

*   Added
    *   config
        *   forceSelection
        *   value
    *   event
        *   change
*   Modified
    *   config
        *   pressedButtons
            *   6.0.1
                *   default value is []
            *   6.0.2
                *   default value is null
                        
## Ext.app.Application

*   Modified
    *   config
        *   mainView
            *   6.0.1
                *   type is String/Object
            *   6.0.2
                *   type is String/Object/Ext.Component
                               
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
                
## Ext.dataview.IndexBar

*   Added
    *   event
        *   directionchange
        
## Ext.dataview.List

*   Modified
    *   method
        *   getScrollDockedItems
            *   6.0.1
                *   return type is Array
            *   6.0.2
                *   return type is Ext.Component[]
                
## Ext.grid.Grid

*   Added
    *   cssVar
        *   $grid-column-resize-marker-background-color
        
## Ext.grid.cell.Base

*   Modified
    *   config
        *   align
            *   6.0.1
                *   default value is 'left'
            *   6.0.2
                *   default value is null
                
## Ext.grid.plugin.ColumnResizing

*   Added
    *   config
        *   realtime
        
## Ext.list.AbstractTreeItem

*   Added
    *   config
        *   over
    *   event
        *   itemclick
        
## Ext.list.Tree
        
*   Modified
    *   method
        *   getMicro
            *   6.0.1
                *   return type is Object
            *   6.0.2
                *   return type is Boolean
