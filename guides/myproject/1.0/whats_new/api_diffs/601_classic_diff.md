<style>
.toc-page{
     display:none !important;
}
</style>

#Differences Between Ext JS 6.0.0 Classic and Ext JS 6.0.1 Classic

We believe developers can glean a lot of useful information by evaluating these diff guides when upgrading their 
applications. That said, these reports are automated and may not always accurately depict change in these early 
releases. Unwanted change may be indicated due to doc updates, formatting omissions, etc. We will review and adjust 
these guides for accuracy prior our GA release. In the meantime, please evaluate these diffs knowing that some level of 
inaccuracy may exist. If you see anything in this report that is incorrect or undesirable, please report them on the 
Ext JS 6 forums.

## Modified

*   Ext
    *   Added
        *   method
            *   copy
            *   copyIf
            *   first
            *   getResourcePath
            *   resolveResource
            *   ticks

*   Ext.Component
    *   Added
        *   config
            *   userCls

*   Ext.Editor
    *   Modified
        *   method
            *   onFocusLeave
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   onHide
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   onShow
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.Img
    *   Added
        *   method
            *   getSrc
            *   setAlt
            *   setTitle

*   Ext.LoadMask
    *   Modified
        *   property
            *   maskOnDisable
                *   6.0.0
                    *   default value is true
                *   6.0.1
                    *   default value is false

*   Ext.Widget
    *   Added
        *   config
            *   userCls
        *   method
            *   getUserCls
            *   setUserCls

*   Ext.app.Application
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

*   Ext.app.Profile
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

*   Ext.app.ViewController
    *   Added
        *   method
            *   lookup

*   Ext.button.Button
    *   Modified
        *   property
            *   isButton
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*   Ext.button.Segmented
    *   Added
        *   method
            *   getValue
            *   setValue

*   Ext.chart.series.Pie
    *   Modified
        *   config
            *   radiusField
                *   6.0.0
                    *   default value is false
                *   6.0.1
                    *   default value is null

*   Ext.container.Container
    *   Modified
        *   method
            *   lookupComponent
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   moveAfter
                *   6.0.0
                    *   return type is Ext.Component
                *   6.0.1
                    *   return type is Ext.Component/Ext.Component[]
            *   moveBefore
                *   6.0.0
                    *   return type is Ext.Component
                *   6.0.1
                    *   return type is Ext.Component/Ext.Component[]
        *   property
            *   items
                *   6.0.0
                    *   type is Ext.util.AbstractMixedCollection
                *   6.0.1
                    *   type is Ext.util.ItemCollection

*   Ext.dashboard.Dashboard
    *   Added
        *   method
            *   getMaxColumns
            *   setMaxColumns

*   Ext.data.BufferedStore
    *   Added
        *   method
            *   flushLoad

*   Ext.data.Connection
    *   Modified
        *   method
            *   request
                *   6.0.0
                    *   return type is Ext.data.AjaxRequest
                *   6.0.1
                    *   return type is Ext.data.request.Base

*   Ext.data.ProxyStore
    *   Added
        *   config
            *   asynchronousLoad
        *   method
            *   flushLoad
            *   getAsynchronousLoad
            *   setAsynchronousLoad

*   Ext.data.TreeStore
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

*   Ext.data.proxy.Server
    *   Modified
        *   method
            *   processResponse
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*   Ext.data.reader.Reader
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

*   Ext.dd.StatusProxy
    *   Added
        *   cssVar
            *   $statusproxy-add-glyph
            *   $statusproxy-add-glyph-color
            *   $statusproxy-background-color
            *   $statusproxy-border-color
            *   $statusproxy-border-style
            *   $statusproxy-border-width
            *   $statusproxy-color
            *   $statusproxy-font-family
            *   $statusproxy-font-size
            *   $statusproxy-font-weight
            *   $statusproxy-glyph-font-size
            *   $statusproxy-icon-size
            *   $statusproxy-line-height
            *   $statusproxy-nodrop-glyph
            *   $statusproxy-nodrop-glyph-color
            *   $statusproxy-ok-glyph
            *   $statusproxy-ok-glyph-color
            *   $statusproxy-padding

*   Ext.direct.Manager
    *   Modified
        *   config
            *   varName
                *   6.0.0
                    *   default value is "Ext.app.REMOTING_API"
                *   6.0.1
                    *   default value is "Ext.REMOTING_API"

*   Ext.direct.RemotingProvider
    *   Added
        *   config
            *   bufferLimit

*   Ext.direct.Transaction
    *   6.0.0
        *   alternateClassNames is [Ext.Direct.Transaction]
    *   6.0.1
        *   alternateClassNames is []

*   Ext.draw.Matrix
    *   Added
        *   method
            *   isEqual
            *   shearX
            *   shearY

*   Ext.draw.Surface
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

*   Ext.draw.engine.Svg
    *   Modified
        *   method
            *   remove
                *   6.0.0
                    *   return type is Boolean
                *   6.0.1
                    *   return type is Ext.draw.sprite.Sprite

*   Ext.draw.sprite.Sprite
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

*   Ext.draw.sprite.Text
    *   6.0.0
        *   aliases is {sprite=[text]}
    *   6.0.1
        *   aliases is {}

*   Ext.form.CheckboxGroup
    *   Modified
        *   config
            *   defaultType
                *   6.0.0
                    *   default value is "panel"
                *   6.0.1
                    *   default value is 'checkboxfield'
            *   layout
                *   6.0.0
                    *   default value is 'auto'
                *   6.0.1
                    *   default value is 'checkboxgroup'
        *   property
            *   defaultBindProperty
                *   6.0.0
                    *   default value is 'html'
                *   6.0.1
                    *   default value is 'value'

*   Ext.form.RadioGroup
    *   Added
        *   config
            *   local
    *   Modified
        *   config
            *   defaultType
                *   6.0.0
                    *   default value is "panel"
                *   6.0.1
                    *   default value is 'radiofield'
        *   property
            *   defaultBindProperty
                *   6.0.0
                    *   default value is 'html'
                *   6.0.1
                    *   default value is 'value'

*   Ext.form.field.Base
    *   Modified
        *   method
            *   onDisable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   onEnable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.form.field.Checkbox
    *   Modified
        *   cssVar
            *   $form-checkbox-checked-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-check-square-o $form-checkbox-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-checkbox-checked $form-checkbox-size ExtJS )
            *   $form-checkbox-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-square-o $form-checkbox-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-checkbox-unchecked $form-checkbox-size ExtJS )
        *   method
            *   onEnable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
        *   property
            *   isCheckbox
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*   Ext.form.field.Display
    *   Modified
        *   cssVar
            *   $grid-cell-display-field-color
                *   6.0.0
                    *   default value is dynamic ( $form-display-field-color )
                *   6.0.1
                    *   default value is dynamic ( $grid-cell-field-color )
            *   $grid-cell-display-field-font-family
                *   6.0.0
                    *   default value is dynamic ( $form-display-field-font-family )
                *   6.0.1
                    *   default value is dynamic ( $grid-cell-field-font-family )
            *   $grid-cell-display-field-font-size
                *   6.0.0
                    *   default value is dynamic ( $form-display-field-font-size )
                *   6.0.1
                    *   default value is dynamic ( $grid-cell-field-font-size )
            *   $grid-cell-display-field-font-weight
                *   6.0.0
                    *   default value is dynamic ( $form-display-field-font-weight )
                *   6.0.1
                    *   default value is dynamic ( $grid-cell-field-font-weight )
            *   $grid-cell-display-field-line-height
                *   6.0.0
                    *   default value is dynamic ( $form-display-field-line-height )
                *   6.0.1
                    *   default value is dynamic ( $grid-row-cell-line-height )

*   Ext.form.field.File
    *   Modified
        *   method
            *   onDisable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   onEnable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
    *   Removed
        *   method
            *   setValue

*   Ext.form.field.HtmlEditor
    *   Modified
        *   cssVar
            *   $html-editor-backcolor-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-font $html-editor-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-text-background-color $html-editor-glyph-font-size ExtJS )
            *   $html-editor-forecolor-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-font $html-editor-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-text-color $html-editor-glyph-font-size ExtJS )
            *   $html-editor-growtext-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-arrow-up $html-editor-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-text-increase $html-editor-glyph-font-size ExtJS )
            *   $html-editor-shrinktext-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-arrow-down $html-editor-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-text-decrease $html-editor-glyph-font-size ExtJS )
            *   $html-editor-sourceedit-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-pencil $html-editor-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-edit-html $html-editor-glyph-font-size ExtJS )

*   Ext.form.field.Spinner
    *   Modified
        *   cssVar
            *   $spinner-trigger-down-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-caret-down 16px $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-spinner-down 16px ExtJS )
            *   $spinner-trigger-up-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-caret-up 16px $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-spinner-up 16px ExtJS )

*   Ext.form.field.Text
    *   Added
        *   method
            *   getEmptyText
            *   setEmptyText
    *   Modified
        *   config
            *   emptyText
                *   6.0.0
                    *   default value is null
                *   6.0.1
                    *   default value is ''
        *   method
            *   beforeFocus
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   onDisable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   onEnable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
    *   Removed
        *   method
            *   setEditable

*   Ext.form.field.TextArea
    *   Modified
        *   method
            *   getSubTplData
                *   6.0.0
                    *   private is true
                    *   return type is void
                *   6.0.1
                    *   private is false
                    *   return type is Object

*   Ext.grid.column.Action
    *   Modified
        *   config
            *   icon
                *   6.0.0
                    *   default value is null
                *   6.0.1
                    *   default value is Ext#BLANK_IMAGE_URL

*   Ext.grid.column.Column
    *   Added
        *   config
            *   sorter
        *   method
            *   getSorter
            *   setSorter
    *   Modified
        *   method
            *   isLocked
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*   Ext.grid.column.RowNumberer
    *   Modified
        *   config
            *   resizable
                *   6.0.0
                    *   default value is true
                *   6.0.1
                    *   default value is false
        *   method
            *   defaultRenderer
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.grid.feature.AbstractSummary
    *   Modified
        *   method
            *   init
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.grid.feature.Feature
    *   Modified
        *   method
            *   init
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
        *   property
            *   isFeature
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*   Ext.grid.feature.Grouping
    *   Modified
        *   cssVar
            *   $grid-grouped-menu-group-by-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-group-by $grid-header-menu-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-group-by $grid-header-menu-glyph-font-size ExtJS )
        *   method
            *   init
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.grid.feature.RowBody
    *   Modified
        *   method
            *   getAdditionalData
                *   6.0.0
                    *   protected is false
                    *   return type is void
                *   6.0.1
                    *   protected is true
                    *   return type is Object
            *   init
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.grid.feature.Summary
    *   Modified
        *   method
            *   init
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.grid.filters.Filters
    *   Modified
        *   cssVar
            *   $grid-filters-header-menu-equals-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-equals $grid-header-menu-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-equals $grid-header-menu-glyph-font-size ExtJS )

*   Ext.grid.header.Container
    *   Modified
        *   cssVar
            *   $grid-header-menu-columns-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-columns $grid-header-menu-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-columns $grid-header-menu-glyph-font-size ExtJS )
            *   $grid-header-menu-sort-asc-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-sort-alpha-asc $grid-header-menu-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-sort-up $grid-header-menu-glyph-font-size ExtJS )
            *   $grid-header-menu-sort-desc-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-sort-alpha-desc $grid-header-menu-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-sort-down $grid-header-menu-glyph-font-size ExtJS )

*   Ext.grid.plugin.DragDrop
    *   Added
        *   config
            *   allowCopy
            *   copy

*   Ext.list.AbstractTreeItem
    *   Modified
        *   config
            *   owner
                *   6.0.0
                    *   type is Ext.list.TreeList
                *   6.0.1
                    *   type is Ext.list.Tree
        *   method
            *   getOwner
                *   6.0.0
                    *   return type is Ext.list.TreeList
                *   6.0.1
                    *   return type is Ext.list.Tree

*   Ext.list.TreeItem
    *   Added
        *   config
            *   rowCls
            *   rowClsProperty
        *   method
            *   getRowCls
            *   setRowCls

*   Ext.menu.DatePicker
    *   Modified
        *   config
            *   enableFocusableContainer
                *   6.0.0
                    *   default value is true
                *   6.0.1
                    *   default value is false

*   Ext.menu.Item
    *   Modified
        *   config
            *   icon
                *   6.0.0
                    *   default value is null
                *   6.0.1
                    *   default value is Ext#BLANK_IMAGE_URL

*   Ext.menu.Menu
    *   Added
        *   cssVar
            *   $menu-item-arrow-glyph-rtl

*   Ext.panel.Header
    *   Modified
        *   config
            *   titleAlign
                *   6.0.0
                    *   type is String
                *   6.0.1
                    *   type is 'left'/'center'/'right'

*   Ext.panel.Panel
    *   Modified
        *   config
            *   headerPosition
                *   6.0.0
                    *   type is String
                *   6.0.1
                    *   type is 'top'/'bottom'/'left'/'right'
            *   iconAlign
                *   6.0.0
                    *   default value is 'left'
                *   6.0.1
                    *   default value is null
            *   titleAlign
                *   6.0.0
                    *   default value is 'left'
                    *   type is String
                *   6.0.1
                    *   default value is null
                    *   type is 'left'/'center'/'right'
            *   titleRotation
                *   6.0.0
                    *   default value is 'default'
                *   6.0.1
                    *   default value is null

*   Ext.panel.Table
    *   Added
        *   event
            *   beforerowbodyclick
            *   beforerowbodycontextmenu
            *   beforerowbodydblclick
            *   beforerowbodykeydown
            *   beforerowbodykeypress
            *   beforerowbodykeyup
            *   beforerowbodylongpress
            *   beforerowbodymousedown
            *   beforerowbodymouseup
            *   rowbodyclick
            *   rowbodycontextmenu
            *   rowbodydblclick
            *   rowbodykeydown
            *   rowbodykeypress
            *   rowbodykeyup
            *   rowbodylongpress
            *   rowbodymousedown
            *   rowbodymouseup

*   Ext.panel.Title
    *   Modified
        *   config
            *   rotation
                *   6.0.0
                    *   default value is 0
                    *   type is 0/1/2
                *   6.0.1
                    *   default value is null
                    *   type is 'default'/0/1/2

*   Ext.panel.Tool
    *   Modified
        *   cssVar
            *   $tool-collapse-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-collapse $tool-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-collapse $tool-glyph-font-size ExtJS )
            *   $tool-expand-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-expand $tool-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-expand $tool-glyph-font-size ExtJS )
            *   $tool-minimize-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-minus $tool-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-minimize $tool-glyph-font-size ExtJS )
            *   $tool-unpin-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-unpin $tool-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-unpin $tool-glyph-font-size ExtJS )

*   Ext.picker.Time
    *   Modified
        *   method
            *   setStore
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*   Ext.pivot.dimension.Item
    *   Modified
        *   config
            *   blankText
                *   6.0.0
                    *   type is Strinbg
                *   6.0.1
                    *   type is String

*   Ext.pivot.plugin.DrillDown
    *   Added
        *   config
            *   remoteStore
    *   Modified
        *   config
            *   columns
                *   6.0.0
                    *   default value is []
                *   6.0.1
                    *   default value is null

*   Ext.resizer.Resizer
    *   Added
        *   cssVar
            *   $resizer-handle-background-color
            *   $resizer-handle-border-radius
            *   $resizer-handle-glyph-color
            *   $resizer-handle-glyph-font-size
            *   $resizer-handle-horizontal-glyph
            *   $resizer-handle-northeast-glyph
            *   $resizer-handle-northwest-glyph
            *   $resizer-handle-size
            *   $resizer-handle-southeast-glyph
            *   $resizer-handle-southwest-glyph
            *   $resizer-handle-vertical-glyph

*   Ext.scroll.Scroller
    *   Added
        *   method
            *   getScrollbarSize
            *   getSpacerXY
            *   setSpacerXY

*   Ext.slider.Multi
    *   Modified
        *   cssVar
            *   $horizontal-slider-thumb-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-equals-vertical $slider-thumb-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-equals-vertical $slider-thumb-glyph-font-size ExtJS )
            *   $vertical-slider-thumb-glyph
                *   6.0.0
                    *   default value is dynamic ( $ext-icon-equals $slider-thumb-glyph-font-size ExtJS )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-equals $slider-thumb-glyph-font-size ExtJS )
        *   method
            *   beforeDestroy
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   getSubTplData
                *   6.0.0
                    *   private is true
                    *   return type is void
                *   6.0.1
                    *   private is false
                    *   return type is Object
            *   initValue
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false
            *   onDisable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true
            *   onEnable
                *   6.0.0
                    *   private is true
                    *   protected is false
                *   6.0.1
                    *   private is false
                    *   protected is true

*   Ext.supports
    *   Added
        *   property
            *   AsyncFocusEvents
            *   SpecialKeyDownRepeat

*   Ext.toolbar.Paging
    *   Modified
        *   cssVar
            *   $grid-paging-toolbar-first-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-angle-double-left $grid-paging-toolbar-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-double-chevron-left $grid-paging-toolbar-glyph-font-size ExtJS )
            *   $grid-paging-toolbar-last-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-angle-double-right $grid-paging-toolbar-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-double-chevron-right $grid-paging-toolbar-glyph-font-size ExtJS )
            *   $grid-paging-toolbar-next-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-angle-right $grid-paging-toolbar-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-chevron-right $grid-paging-toolbar-glyph-font-size ExtJS )
            *   $grid-paging-toolbar-prev-glyph
                *   6.0.0
                    *   default value is dynamic ( $fa-var-angle-left $grid-paging-toolbar-glyph-font-size $font-icon-font-family )
                *   6.0.1
                    *   default value is dynamic ( $ext-var-chevron-left $grid-paging-toolbar-glyph-font-size ExtJS )

*   Ext.tree.Panel
    *   Added
        *   event
            *   beforecheckchange

*   Ext.tree.View
    *   Added
        *   cssVar
            *   $tree-statusproxy-ok-glyph

*   Ext.tree.plugin.TreeViewDragDrop
    *   Added
        *   config
            *   allowCopy
            *   copy

*   Ext.util.Focusable
    *   Added
        *   event
            *   focusenter
            *   focusleave

*   Ext.util.HashMap
    *   Modified
        *   property
            *   generation
                *   6.0.0
                    *   private is true
                *   6.0.1
                    *   private is false

*   Ext.ux.Explorer
    *   Added
        *   method
            *   getSelection
            *   setSelection

*   Ext.ux.layout.ResponsiveColumn
    *   Added
        *   cssMixin
            *   responsivecolumn-item
        *   cssVar
            *   $responsivecolumn-item-spacing

*   Ext.view.Table
    *   Added
        *   cssVar
            *   $grid-cell-dirty-glyph
            *   $grid-cell-dirty-glyph-color
            *   $grid-cell-dirty-glyph-rtl
        *   event
            *   beforerowbodyclick
            *   beforerowbodycontextmenu
            *   beforerowbodydblclick
            *   beforerowbodykeydown
            *   beforerowbodykeypress
            *   beforerowbodykeyup
            *   beforerowbodylongpress
            *   beforerowbodymousedown
            *   beforerowbodymouseup
            *   rowbodyclick
            *   rowbodycontextmenu
            *   rowbodydblclick
            *   rowbodykeydown
            *   rowbodykeypress
            *   rowbodykeyup
            *   rowbodylongpress
            *   rowbodymousedown
            *   rowbodymouseup

*   Ext.view.View
    *   Added
        *   event
            *   beforeitemlongpress
            *   itemlongpress
        *   method
            *   autoSizeColumn
            *   expandToFit
            *   focusCell
            *   walkRecs
        *   property
            *   actionRow
