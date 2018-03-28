<style>
.toc-page{
     display:none !important;
}
</style>

# Differences Between Ext JS 6.0.0 Modern and Ext JS 6.0.1 Modern

We believe developers can glean a lot of useful information by evaluating these diff guides when upgrading their applications. That said, these reports are automated and may not always accurately depict change in these early releases. Unwanted change may be indicated due to doc updates, formatting omissions, etc. We will review and adjust these guides for accuracy prior our GA release. In the meantime, please evaluate these diffs knowing that some level of inaccuracy may exist. If you see anything in this report that is incorrect or undesirable, please report them on the Ext JS 6 forums.

## Added

*    Ext.Progress
*    Ext.panel.Header
*    Ext.panel.Title
*    Ext.panel.Tool
*    Ext.plugin.Responsive

## Modified

*    Ext
    *   Added
        *   method
            *   copy
            *   copyIf
            *   first
            *   getResourcePath
            *   resolveResource
            *   ticks

*    Ext.Component
    *   Added
        *   method
            *   isVisible

*    Ext.Container
    *   Modified
        *   method
            *   factoryItem
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   removeInnerAt
                *   6.0.0
                    *   return type is void
                *   6.0.1
                    *   return type is Ext.Component

*    Ext.Img
    *   6.0.0
        *   alternateClassNames is []
    *   6.0.1
        *   alternateClassNames is [Ext.Image]

*    Ext.Panel
    *   6.0.0
        *   alternateClassNames is [Ext.lib.Panel]
    *   6.0.1
        *   alternateClassNames is [Ext.panel.Panel]
    *   Added
        *   cssVar
            *   $header-icon-opacity
            *   $panel-header-background-color
            *   $panel-header-background-gradient
            *   $panel-header-border-color
            *   $panel-header-border-style
            *   $panel-header-border-width
            *   $panel-header-color
            *   $panel-header-font-family
            *   $panel-header-font-size
            *   $panel-header-font-size-big
            *   $panel-header-font-weight
            *   $panel-header-icon-font-size
            *   $panel-header-icon-font-size-big
            *   $panel-header-icon-horizontal-spacing
            *   $panel-header-icon-horizontal-spacing-big
            *   $panel-header-icon-opacity
            *   $panel-header-icon-size
            *   $panel-header-icon-size-big
            *   $panel-header-icon-vertical-spacing
            *   $panel-header-icon-vertical-spacing-big
            *   $panel-header-line-height
            *   $panel-header-line-height-big
            *   $panel-header-padding
            *   $panel-header-padding-big
            *   $panel-light-ui
        *   method
            *   getHeader
            *   getIcon
            *   getIconCls
            *   getTitle
            *   getTools
            *   setHeader
            *   setIcon
            *   setIconCls
            *   setTitle
            *   setTools
    *   Modified
        *   property
            *   defaultBindProperty
                *   6.0.0
                    *   default value is 'html'
                *   6.0.1
                    *   default value is 'title'
    *   Removed
        *   cssMixin
            *   panel-ui ??

*    Ext.SegmentedButton
    *   6.0.0
        *   alternateClassNames is []
    *   6.0.1
        *   alternateClassNames is [Ext.button.Segmented]

*    Ext.Sheet
    *   Modified
        *   config
            *   border
                *   6.0.0
                    *   default value is false
                    *   type is Boolean
                *   6.0.1
                    *   default value is null
                    *   type is Object

*    Ext.Widget
    *   Added
        *   config
            *   userCls
        *   method
            *   getUserCls
            *   setUserCls

*    Ext.app.Application
    *   Modified
        *   config
            *   currentProfile
                *   6.0.0
                    *   private is true
                    *   type is Object
                *   6.0.1
                    *   private is false
                    *   type is Ext.app.Profile
        *   method
            *   getCurrentProfile
                *   6.0.0
                    *   return type is Object
                *   6.0.1
                    *   return type is Ext.app.Profile

*    Ext.app.Profile
    *   Added
        *   method
            *   init
    *   Modified
        *   config
            *   views
                *   6.0.0
                    *   type is Array
                *   6.0.1
                    *   type is Object/String[]

*    Ext.app.ViewController
    *   Added
        *   method
            *   lookup

*    Ext.chart.series.Pie
    *   Modified
        *   config
            *   radiusField
                *   6.0.0
                    *   default value is false
                *   6.0.1
                    *   default value is null

*    Ext.data.BufferedStore
    *   Added
        *   method
            *   flushLoad

*    Ext.data.Connection
    *   Modified
        *   method
            *   request
                *   6.0.0
                    *   return type is Ext.data.AjaxRequest
                *   6.0.1
                    *   return type is Ext.data.request.Base

*    Ext.data.ProxyStore
    *   Added
        *   config
            *   asynchronousLoad
        *   method
            *   flushLoad
            *   getAsynchronousLoad
            *   setAsynchronousLoad

*    Ext.data.TreeStore
    *   Added
        *   method
            *   flushLoad
    *   Modified
        *   method
            *   isVisible
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*    Ext.data.proxy.Server
    *   Modified
        *   method
            *   processResponse
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*    Ext.data.reader.Reader
    *   Modified
        *   config
            *   rootProperty
                *   6.0.0
                    *   type is String
                *   6.0.1
                    *   type is String/Function
            *   transform
                *   6.0.0
                    *   type is Function|Object
                *   6.0.1
                    *   type is Function|String|Object
        *   method
            *   getRootProperty
                *   6.0.0
                    *   return type is String
                *   6.0.1
                    *   return type is String/Function
            *   getTransform
                *   6.0.0
                    *   return type is Function|Object
                *   6.0.1
                    *   return type is Function|String|Object

*    Ext.dataview.List
    *   Added
        *   config
            *   container
        *   method
            *   getContainer
            *   getItem
            *   setContainer

*    Ext.direct.Manager
    *   Modified
        *   config
            *   varName
                *   6.0.0
                    *   default value is "Ext.app.REMOTING_API"
                *   6.0.1
                    *   default value is "Ext.REMOTING_API"

*    Ext.direct.RemotingProvider
    *   Added
        *   config
            *   bufferLimit

*    Ext.direct.Transaction
    *   6.0.0
        *   alternateClassNames is [Ext.Direct.Transaction]
    *   6.0.1
        *   alternateClassNames is []

*    Ext.draw.Matrix
    *   Added
        *   method
            *   isEqual
            *   shearX
            *   shearY

*    Ext.draw.Surface
    *   Modified
        *   method
            *   remove
                *   6.0.0
                    *   return type is Boolean
                *   6.0.1
                    *   return type is Ext.draw.sprite.Sprite
            *   setDirty
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*    Ext.draw.engine.Svg
    *   Modified
        *   method
            *   remove
                *   6.0.0
                    *   return type is Boolean
                *   6.0.1
                    *   return type is Ext.draw.sprite.Sprite

*    Ext.draw.sprite.Sprite
    *   Added
        *   config
            *   animation
        *   method
            *   resetTransform
            *   setTransform
            *   transform
        *   property
            *   debug
    *   Modified
        *   method
            *   remove
                *   6.0.0
                    *   return type is Boolean
                *   6.0.1
                    *   return type is Ext.draw.sprite.Sprite

*    Ext.draw.sprite.Text
    *   6.0.0
        *   aliases is {sprite=[text]}
    *   6.0.1
        *   aliases is {}

*    Ext.field.Checkbox
    *   Modified
        *   cssVar
            *   $checkboxfield-checkbox-font-size
                *   6.0.0
                    *   default value is dynamic ( 1.24em )
                *   6.0.1
                    *   default value is dynamic ( 1.24rem )
            *   $checkboxfield-checkbox-font-size-big
                *   6.0.0
                    *   default value is dynamic ( 1.2em )
                *   6.0.1
                    *   default value is dynamic ( 1.2rem )

*    Ext.field.DatePicker
    *   Modified
        *   method
            *   reset
                *   6.0.0
                    *   private is true
                    *   return type is void
                *   6.0.1
                    *   private is false
                    *   return type is Ext.field.Field

*    Ext.field.Select
    *   Added
        *   config
            *   publishes
            *   twoWayBindable
    *   Modified
        *   method
            *   getValue
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*    Ext.grid.Grid
    *   Added
        *   config
            *   hideHeaders
        *   cssVar
            *   $grid-cell-background-color
            *   $grid-cell-border-color
            *   $grid-cell-color
            *   $grid-cell-font-family
            *   $grid-cell-font-size
            *   $grid-cell-font-size-big
            *   $grid-cell-font-weight
            *   $grid-cell-line-height
            *   $grid-cell-line-height-big
            *   $grid-cell-padding
            *   $grid-cell-padding-big
            *   $grid-cell-pressed-background-color
            *   $grid-cell-selected-background-color
            *   $grid-group-header-background-color
            *   $grid-group-header-border-color
            *   $grid-group-header-color
            *   $grid-group-header-font-family
            *   $grid-group-header-font-size
            *   $grid-group-header-font-size-big
            *   $grid-group-header-font-weight
            *   $grid-group-header-line-height
            *   $grid-group-header-line-height-big
            *   $grid-group-header-padding
            *   $grid-group-header-padding-big
            *   $grid-summary-row-cell-background-color
            *   $grid-summary-row-cell-border-color
            *   $grid-summary-row-cell-color
            *   $grid-summary-row-cell-font-family
            *   $grid-summary-row-cell-font-size
            *   $grid-summary-row-cell-font-size-big
            *   $grid-summary-row-cell-font-weight
            *   $grid-summary-row-cell-line-height
            *   $grid-summary-row-cell-line-height-big
            *   $grid-summary-row-cell-padding
            *   $grid-summary-row-cell-padding-big
        *   method
            *   getHideHeaders
            *   setHideHeaders

*    Ext.grid.HeaderContainer
    *   Added
        *   method
            *   getGrid
            *   setGrid
    *   Modified
        *   config
            *   layout
                *   6.0.0
                    *   default value is 'default'
                *   6.0.1
                    *   default value is {type: 'hbox', align: 'stretch'}
        *   method
            *   getLayout
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false
    *   Removed
        *   method
            *   getTranslationMethod
            *   setTranslationMethod

*    Ext.grid.HeaderGroup
    *   Modified
    *   Removed
        *   property
            *   columns

*    Ext.grid.Row
    *   6.0.0
        *   mixins is []
    *   6.0.1
        *   mixins is [Ext.mixin.Queryable]

*    Ext.grid.column.Column
    *   Added
        *   config
            *   computedWidth
        *   cssVar
            *   $grid-column-background-color
            *   $grid-column-border-color
            *   $grid-column-color
            *   $grid-column-font-family
            *   $grid-column-font-size
            *   $grid-column-font-size-big
            *   $grid-column-font-weight
            *   $grid-column-line-height
            *   $grid-column-line-height-big
            *   $grid-column-padding
            *   $grid-column-padding-big
            *   $grid-column-sort-asc-icon
            *   $grid-column-sort-desc-icon
            *   $grid-column-sort-icon-color
            *   $grid-column-sort-icon-font-size
            *   $grid-column-sort-icon-spacing
            *   $grid-column-sorted-background-color
        *   method
            *   setComputedWidth
    *   Modified
        *   config
            *   minWidth
                *   6.0.0
                    *   default value is 20
                *   6.0.1
                    *   default value is 40

*    Ext.list.AbstractTreeItem
    *   Added
        *   method
            *   setExpandable
            *   setExpanded
            *   setIconCls
            *   setLeaf
            *   setLoading
            *   setNode
            *   setOwner
            *   setParentItem
            *   setText

*    Ext.list.TreeItem
    *   Added
        *   config
            *   rowCls
            *   rowClsProperty
        *   method
            *   getRowCls
            *   setRowCls

*    Ext.scroll.Scroller
    *   Added
        *   method
            *   getScrollbarSize
            *   getSpacerXY
            *   setSpacerXY

*    Ext.supports
    *   Added
        *   property
            *   AsyncFocusEvents
            *   SpecialKeyDownRepeat

*    Ext.util.Geolocation
    *   Added
        *   method
            *   getAccuracy
            *   getAltitude
            *   getAltitudeAccuracy
            *   getHeading
            *   getLatitude
            *   getLongitude
            *   getSpeed
            *   getTimestamp
            *   setAccuracy
            *   setAltitude
            *   setAltitudeAccuracy
            *   setHeading
            *   setLatitude
            *   setLongitude
            *   setSpeed
            *   setTimestamp

*    Ext.util.HashMap
    *   Modified
        *   property
            *   generation
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*    global ?
    *   Removed
        *   config
            *   defaultPhonePickerConfig
            *   defaultTabletPickerConfig
            *   usePicker
        *   cssVar
            *   $base-color
            *   $css-shadow-border-radius
            *   $enable-font-smoothing
            *   $font-size
            *   $grid-cell-background-color
            *   $grid-cell-border-color
            *   $grid-cell-color
            *   $grid-cell-font-family
            *   $grid-cell-font-size
            *   $grid-cell-font-size-big
            *   $grid-cell-font-weight
            *   $grid-cell-line-height
            *   $grid-cell-line-height-big
            *   $grid-cell-padding
            *   $grid-cell-padding-big
            *   $grid-cell-pressed-background-color
            *   $grid-cell-selected-background-color
            *   $grid-column-background-color
            *   $grid-column-border-color
            *   $grid-column-color
            *   $grid-column-font-family
            *   $grid-column-font-size
            *   $grid-column-font-size-big
            *   $grid-column-font-weight
            *   $grid-column-line-height
            *   $grid-column-line-height-big
            *   $grid-column-padding
            *   $grid-column-padding-big
            *   $grid-column-sort-asc-icon
            *   $grid-column-sort-desc-icon
            *   $grid-column-sort-icon-color
            *   $grid-column-sort-icon-font-size
            *   $grid-column-sort-icon-spacing
            *   $grid-column-sorted-background-color
            *   $grid-group-header-background-color
            *   $grid-group-header-border-color
            *   $grid-group-header-color
            *   $grid-group-header-font-family
            *   $grid-group-header-font-size
            *   $grid-group-header-font-size-big
            *   $grid-group-header-font-weight
            *   $grid-group-header-line-height
            *   $grid-group-header-line-height-big
            *   $grid-group-header-padding
            *   $grid-group-header-padding-big
            *   $grid-summary-row-cell-background-color
            *   $grid-summary-row-cell-border-color
            *   $grid-summary-row-cell-color
            *   $grid-summary-row-cell-font-family
            *   $grid-summary-row-cell-font-size
            *   $grid-summary-row-cell-font-size-big
            *   $grid-summary-row-cell-font-weight
            *   $grid-summary-row-cell-line-height
            *   $grid-summary-row-cell-line-height-big
            *   $grid-summary-row-cell-padding
            *   $grid-summary-row-cell-padding-big
            *   $image-extension
            *   $image-search-path
            *   $include-not-found-images
            *   $relative-image-path-for-uis
            *   $theme-resource-path
            *   $toolbar-input-bg
            *   $toolbar-input-border-color
            *   $toolbar-input-color
            *   $toolbar-input-height
