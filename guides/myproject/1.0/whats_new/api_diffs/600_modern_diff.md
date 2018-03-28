<style>
.toc-page{
     display:none !important;
}
</style>
		
#Differences Between Touch 2.4.1 and Ext JS 6 Modern Toolkit

We believe developers can glean a lot of useful information by evaluating these diff guides when upgrading their 
applications. That said, these reports are automated and may not always accurately depict change in these early 
releases. Unwanted change may be indicated due to doc updates, formatting omissions, etc. We will review and adjust 
these guides for accuracy prior our GA release. In the meantime, please evaluate these diffs knowing that some level of 
inaccuracy may exist. If you see anything in this report that is incorrect or undesirable, please report them on the 
Ext JS 6 forums.

## Added
 * Color
 * Ext.Assert
 * Ext.BingMap
 * Ext.Deferred
 * Ext.Error
 * Ext.Factory
 * Ext.GlobalEvents
 * Ext.Mixin <small>(renamed from Ext.mixin.Mixin)</small>
 * Ext.Widget
 * Ext.app.BaseController
 * Ext.app.EventDomain
 * Ext.app.ViewController
 * Ext.app.ViewModel
 * Ext.app.bind.Binding
 * Ext.app.bind.Formula
 * Ext.app.bind.Multi
 * Ext.app.bind.TemplateBinding
 * Ext.app.domain.View
 * Ext.chart.axis.Axis3D
 * Ext.chart.axis.Category3D
 * Ext.chart.axis.Numeric3D
 * Ext.chart.axis.Time3D
 * Ext.chart.grid.HorizontalGrid3D
 * Ext.chart.grid.VerticalGrid3D
 * Ext.chart.interactions.ItemEdit
 * Ext.chart.plugin.ItemEvents
 * Ext.chart.series.Bar3D
 * Ext.chart.series.sprite.Bar3D
 * Ext.chart.series.sprite.Box
 * Ext.chart.series.sprite.Series
 * Ext.chart.theme.Base
 * Ext.data.AbstractStore
 * Ext.data.BufferedStore
 * Ext.data.ChainedStore
 * Ext.data.ErrorCollection
 * Ext.data.JsonPStore
 * Ext.data.ProxyStore
 * Ext.data.Session
 * Ext.data.TreeModel
 * Ext.data.XmlStore
 * Ext.data.field.Boolean
 * Ext.data.field.Date
 * Ext.data.field.Field
 * Ext.data.field.Integer
 * Ext.data.field.Number
 * Ext.data.field.String
 * Ext.data.identifier.Generator
 * Ext.data.identifier.Negative
 * Ext.data.operation.Create
 * Ext.data.operation.Destroy
 * Ext.data.operation.Operation
 * Ext.data.operation.Read
 * Ext.data.operation.Update
 * Ext.data.request.Ajax
 * Ext.data.request.Base
 * Ext.data.request.Form
 * Ext.data.schema.Association
 * Ext.data.schema.ManyToMany
 * Ext.data.schema.ManyToOne
 * Ext.data.schema.Namer
 * Ext.data.schema.OneToOne
 * Ext.data.schema.Schema
 * Ext.data.session.BatchVisitor
 * Ext.data.session.ChangesVisitor
 * Ext.data.session.ChildChangesVisitor
 * Ext.data.soap.Proxy
 * Ext.data.soap.Reader
 * Ext.data.validator.Bound
 * Ext.data.validator.Email
 * Ext.data.validator.Exclusion
 * Ext.data.validator.Format
 * Ext.data.validator.Inclusion
 * Ext.data.validator.Length
 * Ext.data.validator.Presence
 * Ext.data.validator.Range
 * Ext.data.validator.Validator
 * Ext.dom.CompositeElement
 * Ext.dom.Fly
 * Ext.dom.Helper
 * Ext.draw.Container
 * Ext.draw.Point
 * Ext.draw.gradient.GradientDefinition
 * Ext.draw.plugin.SpriteEvents
 * Ext.draw.sprite.Arrow
 * Ext.draw.sprite.Cross
 * Ext.draw.sprite.Diamond
 * Ext.draw.sprite.Line
 * Ext.draw.sprite.Plus
 * Ext.draw.sprite.Square
 * Ext.draw.sprite.Tick
 * Ext.draw.sprite.Triangle
 * Ext.field.DatePickerNative
 * Ext.field.SingleSlider
 * Ext.list.AbstractItem
 * Ext.list.Item
 * Ext.list.RootItem
 * Ext.list.Tree
 * Ext.mixin.Factoryable
 * Ext.mixin.Mashup
 * Ext.mixin.Responsive
 * Ext.plugin.Abstract
 * Ext.plugin.LazyItems
 * Ext.plugin.field.PlaceHolderLabel
 * Ext.promise.Promise
 * Ext.util.Base64
 * Ext.util.CSV
 * Ext.util.CollectionKey
 * Ext.util.DelimitedValue
 * Ext.util.Group
 * Ext.util.History
 * Ext.util.LocalStorage
 * Ext.util.ObjectTemplate
 * Ext.util.Observable
 * Ext.util.TSV
 * Ext.util.TaskManager
 * Ext.util.TaskRunner
 * Ext.util.TaskRunner.Task
 * Ext.util.TextMetrics
 * Ext.ux.ajax.DataSimlet
 * Ext.ux.ajax.JsonSimlet
 * Ext.ux.ajax.SimManager
 * Ext.ux.ajax.SimXhr
 * Ext.ux.ajax.Simlet
 * Ext.ux.ajax.XmlSimlet
 * Ext.ux.event.Driver
 * Ext.ux.event.Maker
 * Ext.ux.event.Player
 * Ext.ux.event.Recorder
 * Ext.ux.google.Api
 * Ext.ux.google.Feeds

## Modified
* ### Ext
     * Added
         * config
             * debugConfig
             * manifest
         * method
             * all
             * asap
             * asapCancel
             * checkVersion
             * coerce
             * copyToIf
             * destroyMembers
             * getNamespace
             * getScrollbarSize
             * getWin
             * interval
             * isDebugEnabled
             * log
             * now
             * on
             * raise
             * returnId
             * returnTrue
             * un
         * property
             * BLANK\_IMAGE\_URL
             * USE\_NATIVE\_JSON
             * baseCSSPrefix
             * chromeVersion
             * emptyString
             * enableAria
             * enableAriaButtons
             * enableAriaPanels
             * firefoxVersion
             * identityFn
             * ieVersion
             * isChrome
             * isDomReady
             * isGecko
             * isIE
             * isIE10
             * isIE10m
             * isIE10p
             * isIE11
             * isIE11m
             * isIE11p
             * isIE8
             * isIE8m
             * isIE8p
             * isIE9
             * isIE9m
             * isIE9p
             * isLinux
             * isMac
             * isOpera
             * isSafari
             * isWebKit
             * isWindows
             * name
             * operaVersion
             * platformTags
             * privateFn
             * safariVersion
             * webKitVersion
     * Modified
         * method
             * callback
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Object
             * createWidget
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
         * property
             * isReady
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * method
             * createInterceptor
             * dispatch
             * getOrientation
             * preg
             * redirect
             * reg
             * regApplication
             * regController
             * regLayout
             * regModel
             * repaint
             * setup
             * type
         * property
             * version
 * Ext.Ajax

     * Added
         * property
             * defaultHeaders
             * disableCaching
             * extraParams
             * method
             * timeout
             * url
 * Ext.Anim

     * Modified
         * method
             * constructor
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.Array

     * Added
         * method
             * binarySearch
             * equals
             * findBy
             * numericSortFn
             * push
             * reduce
             * removeAt
             * toMap
             * toValueMap
 * Ext.Audio

     * Modified
         * property
             * template
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.Base

     * Added
         * method
             * callSuper
         * property
             * destroyed
             * isConfiguring
             * isFirstInstance
             * isInstance
     * Modified
         * method
             * getConfig
                 * 2.4.1
                     * private is true
                     * return type is void
                 * 6.0.0
                     * private is false
                     * return type is Object
             * initConfig
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.Base
             * setConfig
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.Button

     * Added
         * cssVar
             * $button-action-ui
             * $button-background-color
             * $button-background-gradient
             * $button-badge-background-color
             * $button-badge-background-gradient
             * $button-badge-border-color
             * $button-badge-border-radius
             * $button-badge-bottom
             * $button-badge-color
             * $button-badge-font-family
             * $button-badge-font-size
             * $button-badge-font-weight
             * $button-badge-left
             * $button-badge-line-height
             * $button-badge-max-width
             * $button-badge-min-width
             * $button-badge-padding
             * $button-badge-right
             * $button-badge-top
             * $button-border-color
             * $button-border-radius
             * $button-border-radius-big
             * $button-border-style
             * $button-border-width
             * $button-color
             * $button-confirm-ui
             * $button-decline-ui
             * $button-disabled-opacity
             * $button-font-size-big
             * $button-font-weight
             * $button-icon-font-size
             * $button-icon-font-size-big
             * $button-icon-horizontal-spacing
             * $button-icon-horizontal-spacing-big
             * $button-icon-size
             * $button-icon-size-big
             * $button-icon-vertical-spacing
             * $button-icon-vertical-spacing-big
             * $button-line-height-big
             * $button-padding
             * $button-padding-big
             * $button-pressed-background-color
             * $button-pressed-background-gradient
             * $button-pressed-border-color
             * $button-pressed-color
             * $button-round-ui
             * $button-small-ui
         * property
             * defaultBindProperty
     * Modified
         * config
             * ui
                 * 2.4.1
                     * default value is 'normal'
                 * 6.0.0
                     * default value is null
         * cssVar
             * $button-font-family
                 * 2.4.1
                     * type is font-family
                 * 6.0.0
                     * type is string
             * $button-font-size
                 * 2.4.1
                     * default value is 1em
                     * type is measurement
                 * 6.0.0
                     * default value is 1rem
                     * type is number
             * $button-line-height
                 * 2.4.1
                     * default value is 1.2em
                     * type is measurement
                 * 6.0.0
                     * default value is 1.23em
                     * type is number
         * property
             * template
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * config
             * badge
         * cssMixin
             * sencha-button-ui
         * cssVar
             * $button-gradient
             * $button-height
             * $button-radius
             * $button-stroke-weight
             * $include-button-highlights
             * $toolbar-icon-size
         * method
             * setBadge
             * setIconClass
 * Ext.Class

     * Added
         * config
             * cachedConfig
             * override
             * privates
             * requires
             * xtype
 * Ext.ClassManager

     * Added
         * config
             * debugHooks
             * deprecated
     * Modified
         * method
             * addNameAliasMappings
                 * 2.4.1
                     * return type is Ext.ClassManager
                 * 6.0.0
                     * return type is void
             * addNameAlternateMappings
                 * 2.4.1
                     * return type is Ext.ClassManager
                 * 6.0.0
                     * return type is void
     * Removed
         * method
             * getAliasesByName
             * getNameByAlias
             * getNameByAlternate
             * getNamesByExpression
             * setAlias
 * Ext.Component

     * 2.4.1
         * superclass is Ext.AbstractComponent
     * 6.0.0
         * superclass is Ext.Widget
     * Added
         * config
             * scrollable
         * cssVar
             * $scroll-indicator-background-color
             * $scroll-indicator-border-radius
             * $scroll-indicator-margin
             * $scroll-indicator-opacity
             * $scroll-indicator-size
         * event
             * added
             * moved
             * removed
             * scrollablechange
         * method
             * getScrollable
             * onScrollEnd
             * onScrollMove
             * onScrollStart
             * updateHeight
             * updateWidth
         * property
             * defaultBindProperty
     * Modified
         * config
             * border
                 * 2.4.1
                     * type is Number/String
                 * 6.0.0
                     * type is Boolean
             * xtype
                 * 2.4.1
                     * default value is null
                     * type is String[]
                 * 6.0.0
                     * default value is 'component'
                     * type is String
         * method
             * getBorder
                 * 2.4.1
                     * return type is Number/String
                 * 6.0.0
                     * return type is Boolean
             * initElement
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
         * property
             * element
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * config
             * componentCls
             * dock
             * floating
             * hideOnMaskTap
             * layoutOnOrientationChange
             * modal
             * monitorOrientation
             * scroll
             * stopMaskTapEvent
         * event
             * flexchange
         * method
             * getEl
             * setFloating
             * update
 * Ext.ComponentManager

     * Added
         * method
             * each
             * getAll
             * getCount
             * onAvailable
     * Modified
         * method
             * registerType
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.ComponentQuery

     * 2.4.1
         * superclass is null
     * 6.0.0
         * superclass is Ext.Base
     * Added
         * method
             * first
             * visitPostOrder
             * visitPreOrder
     * Removed
         * property
             * val
 * Ext.Container

     * 2.4.1
         * alternateClassNames is [Ext.lib.Container]
         * mixins is []
     * 6.0.0
         * alternateClassNames is [Ext.lib.Container, Ext.container.Container]
         * mixins is [Ext.mixin.Queryable, Ext.mixin.Container]
     * Added
         * config
             * manageBorders
         * method
             * initInheritedState
     * Modified
         * config
             * layout
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is 'default'
             * scrollable
                 * 2.4.1
                     * type is Ext.scroll.View
                 * 6.0.0
                     * type is Ext.scroll.Scroller
         * method
             * add
                 * 2.4.1
                     * return type is Ext.Component
                 * 6.0.0
                     * return type is Ext.Component/Ext.Component[]
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * getElementConfig
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
             * removeAll
                 * 2.4.1
                     * return type is Ext.Component
                 * 6.0.0
                     * return type is Ext.Component[]
             * removeAt
                 * 2.4.1
                     * return type is Ext.Container
                 * 6.0.0
                     * return type is Ext.Component
     * Removed
         * config
             * scroll
         * method
             * addAll
             * removeDocked
         * property
             * items
 * Ext.Date

     * 2.4.1
         * mixins is [Ext.DateExtras]
     * 6.0.0
         * mixins is null
     * Added
         * method
             * formatContainsDateInfo
             * formatContainsHourInfo
             * isEqual
             * subtract
             * unescapeFormat
     * Modified
         * property
             * monthNumbers
                 * 2.4.1
                     * default value is {Jan: 0, Feb: 1, Mar: 2, Apr: 3, May: 4, Jun: 5, Jul: 6, Aug: 7, Sep: 8, Oct: 9, Nov: 10, Dec: 11}
                 * 6.0.0
                     * default value is {January: 0, Jan: 0, February: 1, Feb: 1, March: 2, Mar: 2, April: 3, Apr: 3, May: 4, June: 5, Jun: 5, July: 6, Jul: 6, August: 7, Aug: 7, September: 8, Sep: 8, October: 9, Oct: 9, November: 10, Nov: 10, December: 11, Dec: 11}
 * Ext.Function

     * 2.4.1
         * alternateClassNames is [Ext.util.Functions]
     * 6.0.0
         * alternateClassNames is []
     * Added
         * method
             * bindCallback
             * createBarrier
             * interval
             * memoize
     * Removed
         * method
             * createDelegate
 * Ext.Img

     * Added
         * method
             * updateHeight
             * updateWidth
 * Ext.JSON

     * Added
         * method
             * encodeString
             * encodeValue
 * Ext.LoadMask

     * Removed
         * config
             * msg
             * msgCls
             * store
         * method
             * bindStore
 * Ext.Loader

     * Added
         * config
             * preserveScripts
             * scriptChainDelay
             * scriptCharset
         * method
             * addBaseUrlClassPathMappings
             * loadScript
     * Modified
         * property
             * history
                 * 2.4.1
                     * default value is []
                 * 6.0.0
                     * default value is null
     * Removed
         * method
             * exclude
             * require
             * syncRequire
 * Ext.Map

     * Modified
         * method
             * getElementConfig
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
     * Removed
         * config
             * maskMap
             * maskMapCls
         * method
             * getState
             * update
 * Ext.Menu

     * Added
         * method
             * updateHidden
     * Removed
         * method
             * doSetHidden
 * Ext.MessageBox

     * 2.4.1
         * aliases is {}
     * 6.0.0
         * aliases is {widget=[messagebox]}
     * Added
         * property
     * Modified
         * method
             * constructor
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * config
             * icon
         * method
             * setIcon
             * updateText
 * Ext.Number

     * Added
         * method
             * clipIndices
             * correctFloat
             * randomInt
             * sign
             * snapInRange
 * Ext.Object

     * Added
         * method
             * clear
             * eachValue
             * equals
             * freeze
             * getAllKeys
             * isEmpty
     * Modified
         * method
             * mergeIf
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.Panel

     * Added
         * config
             * manageBorders
         * cssMixin
             * panel-ui
         * cssVar
             * $panel-body-background-color
             * $panel-body-border-color
             * $panel-body-border-style
             * $panel-body-border-width
             * $panel-body-color
             * $panel-body-font-family
             * $panel-body-font-size
             * $panel-body-font-size-big
             * $panel-body-font-weight
             * $panel-body-line-height
             * $panel-body-line-height-big
             * $panel-border-color
             * $panel-border-style
             * $panel-border-width
             * $panel-manage-borders
         * method
             * addBodyCls
             * removeBodyCls
     * Modified
         * config
             * bodyBorder
                 * 2.4.1
                     * type is Number/Boolean/String
                 * 6.0.0
                     * type is Boolean
             * border
                 * 2.4.1
                     * type is Number/String
                 * 6.0.0
                     * type is Boolean
         * method
             * getBodyBorder
                 * 2.4.1
                     * return type is Number/Boolean/String
                 * 6.0.0
                     * return type is Boolean
             * getBorder
                 * 2.4.1
                     * return type is Number/String
                 * 6.0.0
                     * return type is Boolean
             * getElementConfig
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
     * Removed
         * config
             * bodyMargin
         * method
             * getBodyMargin
             * setBodyMargin
 * Ext.ProgressIndicator

     * Modified
         * method
             * getElementConfig
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
 * Ext.Promise

     * Added
         * method
             * all
             * resolve
     * Modified
         * method
             * reject
                 * 2.4.1
                     * private is true
                     * static is false
                 * 6.0.0
                     * private is false
                     * static is true
 * Ext.SegmentedButton

     * Added
         * config
             * defaultUI
         * method
             * getDefaultUI
             * setDefaultUI
     * Removed
         * method
             * getPressed
             * setPressed
 * Ext.Sheet

     * Added
         * config
             * manageBorders
         * cssVar
             * $sheet-background-color
             * $sheet-border-color
     * Modified
         * config
             * border
                 * 2.4.1
                     * type is Number/String
                 * 6.0.0
                     * type is Boolean
         * cssVar
             * $sheet-bg-color
                 * 2.4.1
                     * default value is transparentize ( darken ( $base-color , 40% ) , .1 )
                 * 6.0.0
                     * default value is #fff
             * $sheet-padding
                 * 2.4.1
                     * default value is .7em
                 * 6.0.0
                     * default value is 0em
     * Removed
         * cssVar
             * $sheet-bg-gradient
 * Ext.String

     * Added
         * method
             * addCharacterEntities
             * createRegex
             * createVarName
             * endsWith
             * insert
             * resetCharacterEntities
             * splitWords
             * startsWith
             * uncapitalize
 * Ext.Template

     * Modified
         * config
             * compiled
                 * 2.4.1
                     * default value is false
                 * 6.0.0
                     * default value is null
 * Ext.TitleBar

     * Added
         * property
             * defaultBindProperty
 * Ext.Toast

     * Added
         * property
 * Ext.Toolbar

     * Added
         * config
             * defaultButtonUI
         * cssVar
             * $toolbar-background-color
             * $toolbar-background-gradient
             * $toolbar-border-color
             * $toolbar-border-style
             * $toolbar-border-width
             * $toolbar-horizontal-spacing
             * $toolbar-horizontal-spacing-big
             * $toolbar-padding
             * $toolbar-padding-big
             * $toolbar-spacing
             * $toolbar-title-color
             * $toolbar-title-font-family
             * $toolbar-title-font-size
             * $toolbar-title-font-size-big
             * $toolbar-title-font-weight
             * $toolbar-vertical-spacing
             * $toolbar-vertical-spacing-big
         * method
             * getDefaultButtonUI
             * setDefaultButtonUI
     * Removed
         * config
             * titleCls
         * cssMixin
             * sencha-toolbar-ui
         * cssVar
             * $include-toolbar-uis
             * $toolbar-base-color
             * $toolbar-gradient
 * Ext.Version

     * Added
         * method
             * compareTo
             * getReleaseValue
         * property
             * build
             * major
             * minor
             * patch
             * release
     * Removed
         * method
             * constructor
             * deprecate
             * getVersion
             * setVersion
             * toNumber
 * Ext.Video

     * Modified
         * property
             * template
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.XTemplate

     * Added
         * config
             * definitions
             * strict
 * Ext.app.Application

     * Added
         * config
             * appProperty
             * defaultToken
             * extend
             * glyphFontFamily
             * mainView
             * namespaces
             * paths
             * scope
         * method
             * createController
             * destroyController
             * getAppProperty
             * getDefaultToken
             * getGlyphFontFamily
             * getMainView
             * launch
             * onAppUpdate
             * setAppProperty
             * setDefaultToken
             * setGlyphFontFamily
             * setMainView
     * Modified
         * config
             * controllers
                 * 2.4.1
                     * default value is []
                     * type is Array
                 * 6.0.0
                     * default value is null
                     * type is String/String[]
             * currentProfile
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * name
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is ''
             * profiles
                 * 2.4.1
                     * type is Array
                 * 6.0.0
                     * type is String/String[]
         * method
             * getProfiles
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is String/String[]
     * Removed
         * config
             * glossOnIcon
             * history
             * icon
             * isIconPrecomposed
             * launch
             * phoneIcon
             * phoneStartupScreen
             * requires
             * router
             * startupImage
             * statusBarStyle
             * tabletIcon
             * tabletStartupScreen
             * themeVariation
             * themeVariationPrefix
             * themeVariationTransitionCls
         * method
             * dispatch
             * getAppFolder
             * getControllers
             * getHistory
             * getLaunch
             * getRequires
             * getRouter
             * getThemeVariation
             * getThemeVariationPrefix
             * getThemeVariationTransitionCls
             * setAppFolder
             * setControllers
             * setHistory
             * setLaunch
             * setRequires
             * setRouter
             * setThemeVariation
             * setThemeVariationPrefix
             * setThemeVariationTransitionCls
 * Ext.app.Controller

     * 2.4.1
         * mixins is [Ext.mixin.Observable]
         * superclass is Ext.Base
     * 6.0.0
         * mixins is []
         * superclass is Ext.app.BaseController
     * Added
         * method
             * activate
             * addRef
             * deactivate
             * getActive
             * getProfile
             * getStore
             * getView
             * init
             * isActive
             * onLaunch
             * setActive
     * Modified
         * config
             * application
                 * 2.4.1
                     * default value is {}
                 * 6.0.0
                     * default value is null
             * before
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * models
                 * 2.4.1
                     * default value is []
                 * 6.0.0
                     * default value is null
             * refs
                 * 2.4.1
                     * default value is {}
                     * type is Object
                 * 6.0.0
                     * default value is null
                     * type is Object/Object[]
             * stores
                 * 2.4.1
                     * default value is []
                     * type is String[]
                 * 6.0.0
                     * default value is null
                     * type is String/String[]
             * views
                 * 2.4.1
                     * default value is []
                     * type is Array
                 * 6.0.0
                     * default value is null
                     * type is String/String[]
         * method
             * getController
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.app.Controller
             * getModel
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.Class
             * getRefs
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Object/Object[]
             * hasRef
                 * 2.4.1
                     * private is true
                     * return type is void
                 * 6.0.0
                     * private is false
                     * return type is Boolean
             * redirectTo
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Boolean
     * Removed
         * config
             * init
             * launch
         * method
             * getModels
             * getStores
             * getViews
             * setModels
             * setStores
             * setViews
 * Ext.app.Profile

     * Added
         * config
             * mainView
         * method
             * getMainView
             * setMainView
         * property
             * isProfile
 * Ext.carousel.Carousel

     * Modified
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
     * Removed
         * method
             * isHorizontal
             * isVertical
             * prev
 * Ext.chart.AbstractChart

     * 2.4.1
         * superclass is Ext.draw.Component
     * 6.0.0
         * superclass is Ext.draw.Container
     * Added
         * config
             * animation
             * theme
         * event
             * itemdblclick
             * storechange
         * method
             * addSeries
             * cancelChartLayout
             * getAxis
             * getInteraction
             * getTheme
             * removeSeries
             * resumeChartLayout
             * setAnimation
             * setTheme
             * suspendChartLayout
     * Modified
         * config
             * colors
                 * 2.4.1
                     * type is Boolean/Array
                 * 6.0.0
                     * type is Array
             * insetPadding
                 * 2.4.1
                     * type is Object|Number
                 * 6.0.0
                     * type is Object|Number|String
             * store
                 * 2.4.1
                     * default value is null
                     * type is Ext.data.Store
                 * 6.0.0
                     * default value is 'ext-empty-store'
                     * type is Ext.data.Store/String/Object
             * style
                 * 2.4.1
                     * type is String/Object
                 * 6.0.0
                     * type is Object
         * method
             * getInsetPadding
                 * 2.4.1
                     * return type is Object|Number
                 * 6.0.0
                     * return type is Object|Number|String
             * getStore
                 * 2.4.1
                     * return type is Ext.data.Store
                 * 6.0.0
                     * return type is Ext.data.Store/String/Object
             * getStyle
                 * 2.4.1
                     * return type is String/Object
                 * 6.0.0
                     * return type is Object
     * Removed
         * config
             * animate
             * innerPadding
             * shadow
         * event
             * itemdoubleclick
             * itemdoubletap
             * itemdrag
             * itemdragend
             * itemdragstart
             * itempinch
             * itempinchend
             * itempinchstart
             * itemsingletap
             * itemswipe
             * itemtapcancel
             * itemtapend
             * itemtaphold
             * itemtapstart
             * itemtouchend
             * itemtouchmove
             * itemtouchstart
         * method
             * cancelLayout
             * flatten
             * getInnerPadding
             * getShadow
             * initialize
             * setAnimate
             * setInnerPadding
             * setShadow
         * property
             * version
 * Ext.chart.CartesianChart

     * 2.4.1
         * aliases is {widget=[chart]}
     * 6.0.0
         * aliases is {widget=[cartesian]}
     * Added
         * method
             * getInnerRect
             * setInnerRect
     * Removed
         * method
             * getInnerRegion
             * onPlaceWatermark
             * setInnerRegion
 * Ext.chart.Legend

     * 2.4.1
         * superclass is Ext.dataview.DataView
     * 6.0.0
         * superclass is Ext.chart.LegendBase
     * Added
         * config
             * rect
         * method
             * getRect
             * setRect
     * Modified
         * config
             * baseCls
                 * 2.4.1
                     * default value is 'x-legend'
                     * private is false
                 * 6.0.0
                     * default value is Ext.baseCSSPrefix + 'legend'
                     * private is true
             * disableSelection
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * padding
                 * 2.4.1
                     * private is false
                     * type is Number/String
                 * 6.0.0
                     * private is true
                     * type is Number
     * Removed
         * config
             * inline
             * itemTpl
             * position
         * method
             * getHorizontalHeight
             * getInline
             * getItemTpl
             * getVerticalWidth
             * setHorizontalHeight
             * setInline
             * setItemTpl
             * setScrollable
             * setVerticalWidth
 * Ext.chart.MarkerHolder

     * 2.4.1
         * superclass is Ext.mixin.Mixin
     * 6.0.0
         * superclass is Ext.Mixin
     * Added
         * method
             * getMarker
     * Modified
         * method
             * getBoundMarker
                 * 2.4.1
                     * private is true
                     * return type is void
                 * 6.0.0
                     * deprecated
                     * private is false
                     * return type is Ext.chart.Markers[]
 * Ext.chart.PolarChart

     * Modified
         * config
             * innerPadding
                 * 2.4.1
                     * default value is {top: 0, left: 0, right: 0, bottom: 0}
                     * type is Object
                 * 6.0.0
                     * default value is 0
                     * type is Number
         * method
             * getInnerPadding
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Number
 * Ext.chart.axis.Axis

     * Added
         * config
             * adjustByMajorUnit
             * floating
             * limits
             * linkedTo
             * margin
             * reconcileRange
         * event
             * rangechange
             * visiblerangechange
         * method
             * getAdjustByMajorUnit
             * getFloating
             * getLimits
             * getLinkedTo
             * getMargin
             * getReconcileRange
             * reconcileRange
             * resolveListenerScope
             * setAdjustByMajorUnit
             * setFloating
             * setLimits
             * setLinkedTo
             * setMargin
             * setReconcileRange
     * Modified
         * config
             * label
                 * 2.4.1
                     * default value is {x: 0, y: 0, textBaseline: 'middle', textAlign: 'center', fontSize: 12, fontFamily: 'Helvetica'}
                 * 6.0.0
                     * default value is undefined
             * majorTickSteps
                 * 2.4.1
                     * default value is false
                 * 6.0.0
                     * default value is 0
             * title
                 * 2.4.1
                     * default value is {fontSize: 18, fontFamily: 'Helvetica'}
                 * 6.0.0
                     * default value is null
 * Ext.chart.axis.Numeric

     * 2.4.1
         * aliases is {axis=[numeric]}
     * 6.0.0
         * aliases is {axis=[numeric, radial]}
 * Ext.chart.axis.layout.Layout

     * 2.4.1
         * mixins is []
     * 6.0.0
         * mixins is [Ext.mixin.Observable]
 * Ext.chart.interactions.Abstract

     * Removed
         * config
             * gesture
         * method
             * getGesture
             * setGesture
 * Ext.chart.interactions.ItemHighlight

     * Added
         * config
             * sticky
         * method
             * getSticky
             * setGestures
             * setSticky
 * Ext.chart.interactions.ItemInfo

     * Modified
         * config
             * panel
                 * 2.4.1
                     * default value is {modal: true, centered: true, width: 250, height: 300, styleHtmlContent: true, scrollable: 'vertical', hideOnMaskTap: true, fullscreen: false, hidden: true, zIndex: 30, items: [{docked: 'top', xtype: 'toolbar', title: 'Item Detail'}]}
                 * 6.0.0
                     * default value is {modal: true, centered: true, width: 300, height: 200, styleHtmlContent: true, scrollable: 'vertical', hideOnMaskTap: true, fullscreen: false, hidden: false, zIndex: 30}
 * Ext.chart.interactions.PanZoom

     * Modified
         * config
             * zoomOnPanGesture
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
         * method
             * getPanGesture
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * setPanGesture
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.chart.interactions.Rotate

     * Added
         * method
             * setGestures
     * Modified
         * config
             * gesture
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
         * method
             * getGesture
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * getGestures
                 * 2.4.1
                     * private is true
                     * return type is void
                 * 6.0.0
                     * private is false
                     * return type is Object
             * rotateTo
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * setGesture
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.chart.label.Label

     * Added
         * config
             * calloutLine
         * method
             * getCalloutLine
             * setCalloutLine
     * Modified
         * config
             * fx
                 * 2.4.1
                     * default value is {customDuration: {callout: 200}}
                 * 6.0.0
                     * default value is {customDurations: {callout: 200}}
 * Ext.chart.series.Area

     * Added
         * config
             * splitStacks
         * method
             * getSplitStacks
             * setSplitStacks
 * Ext.chart.series.Cartesian

     * Modified
         * config
             * xAxis
                 * 2.4.1
                     * type is Ext.chart.axis.Axis
                 * 6.0.0
                     * type is Ext.chart.axis.Axis|Number|String
             * yAxis
                 * 2.4.1
                     * type is Ext.chart.axis.Axis
                 * 6.0.0
                     * type is Ext.chart.axis.Axis|Number|String
         * method
             * getXAxis
                 * 2.4.1
                     * return type is Ext.chart.axis.Axis
                 * 6.0.0
                     * return type is Ext.chart.axis.Axis|Number|String
             * getYAxis
                 * 2.4.1
                     * return type is Ext.chart.axis.Axis
                 * 6.0.0
                     * return type is Ext.chart.axis.Axis|Number|String
 * Ext.chart.series.Gauge

     * Added
         * config
             * rect
         * method
             * getRect
             * setRect
     * Removed
         * config
             * region
             * field
             * needleLengthRatio
         * method
             * getField
             * setField
             * getNeedleLengthRatio
             * setNeedleLengthRatio
             * getRegion
             * setRegion
 * Ext.chart.series.Pie

     * Added
         * config
             * clockwise
             * radiusFactor
             * radiusField
         * method
             * getClockwise
             * getRadiusFactor
             * getRadiusField
             * setClockwise
             * setRadiusFactor
             * setRadiusField
     * Modified
         * config
             * highlightCfg
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Ext.chart.series.sprite.PieSlice/Object
         * method
             * getHighlightCfg
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.chart.series.sprite.PieSlice/Object
     * Removed
         * config
             * Allows
             * field
             * labelField
         * method
             * getLabelField
             * setLabelField
 * Ext.chart.series.Pie3D

     * Added
         * config
             * angleField
         * method
             * getRect
             * setRect
     * Modified
         * config
             * hidden
                 * 2.4.1
                     * default value is false
                     * type is Boolean|Array
                 * 6.0.0
                     * default value is []
                     * type is Array
         * method
             * getField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * getHidden
                 * 2.4.1
                     * return type is Boolean|Array
                 * 6.0.0
                     * return type is Array
             * setField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * config
             * field
         * method
             * getRegion
             * setRegion
 * Ext.chart.series.Polar

     * Added
         * config
             * angleField
             * radiusField
         * method
             * getAngleField
             * getRadiusField
             * setAngleField
             * setRadiusField
     * Modified
         * config
             * xField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * yField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
         * method
             * getXField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * getYField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * setXField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * setYField
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.chart.series.Radar

     * Modified
         * config
             * style
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is {}
 * Ext.chart.series.Scatter

     * Modified
         * config
             * itemInstancing
                 * 2.4.1
                     * default value is {fx: {customDuration: {translationX: 0, translationY: 0}}}
                 * 6.0.0
                     * default value is {fx: {customDurations: {translationX: 0, translationY: 0}}}
 * Ext.chart.series.Series

     * 2.4.1
         * mixins is [Ext.mixin.Observable]
     * 6.0.0
         * mixins is [Ext.mixin.Observable, Ext.mixin.Bindable]
     * Added
         * config
             * animation
             * highlight
             * showMarkers
             * tooltip
             * useDarkerStrokeColor
         * event
             * itemclick
             * itemdblclick
             * itemmousedown
             * itemmousemove
             * itemmouseout
             * itemmouseover
             * itemmouseup
             * itemtap
             * storechange
         * method
             * getHighlight
             * getItemByIndex
             * getShowMarkers
             * getTooltip
             * getUseDarkerStrokeColor
             * setAnimation
             * setHighlight
             * setShowMarkers
             * setTooltip
             * setUseDarkerStrokeColor
         * property
             * defaultBindProperty
     * Modified
         * config
             * highlightCfg
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * label
                 * 2.4.1
                     * default value is {textBaseline: 'middle', textAlign: 'center', font: '14px Helvetica'}
                 * 6.0.0
                     * default value is {}
             * labelOverflowPadding
                 * 2.4.1
                     * default value is 5
                 * 6.0.0
                     * default value is null
             * marker
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Object|Boolean
         * method
             * getHighlightCfg
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * getMarker
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Object|Boolean
             * setHighlightCfg
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
     * Removed
         * config
             * animate
             * labelField
         * method
             * getAnimate
             * getLabelField
             * setAnimate
             * setLabelField
 * Ext.chart.series.StackedCartesian

     * Added
         * config
             * fullStack
             * fullStackTotal
             * splitStacks
         * method
             * getFullStack
             * getFullStackTotal
             * getSplitStacks
             * setFullStack
             * setFullStackTotal
             * setSplitStacks
 * Ext.chart.series.sprite.Cartesian

     * 2.4.1
         * extends Ext.draw.sprite.Sprite
     * 6.0.0
         * extends Ext.chart.series.sprite.Series
 * Ext.chart.series.sprite.Line

     * Added
         * config
             * yCap
 * Ext.chart.series.sprite.Pie3DPart

     * Added
         * attribute
             * bevelWidth
             * colorSpread
             * label
 * Ext.chart.series.sprite.PieSlice

     * Added
         * method
             * getSeries
             * setSeries
     * Removed
         * config
             * rotateLabels
 * Ext.chart.series.sprite.Polar

     * 2.4.1
         * extends Ext.draw.sprite.Sprite
     * 6.0.0
         * extends Ext.chart.series.sprite.Series
 * Ext.data.ArrayStore

     * 2.4.1
         * alternateClassNames is []
     * 6.0.0
         * alternateClassNames is [Ext.data.SimpleStore]
 * Ext.data.Batch

     * Added
         * method
             * getCurrent
             * getExceptions
             * getOperations
             * getTotal
             * hasException
             * isComplete
             * isRunning
             * retry
             * sort
         * property
             * exceptions
     * Modified
         * config
             * pauseOnException
                 * 2.4.1
                     * default value is true
                 * 6.0.0
                     * default value is false
         * method
             * add
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.data.Batch
             * pause
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.data.Batch
             * runOperation
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * start
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.data.Batch
         * property
             * current
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * operations
                 * 2.4.1
                     * private is false
                     * type is Ext.data.Operation[]
                 * 6.0.0
                     * private is true
                     * type is Ext.data.operation.Operation[]
             * total
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * config
             * autoStart
             * proxy
         * method
             * getAutoStart
             * getProxy
             * setAutoStart
             * setProxy
         * property
             * hasException
             * isComplete
             * isRunning
 * Ext.data.Connection

     * Added
         * config
             * binary
             * cors
             * withCredentials
         * method
             * getBinary
             * getCors
             * getDefaultXdrContentType
             * getIsXdr
             * getWithCredentials
             * setBinary
             * setCors
             * setDefaultXdrContentType
             * setIsXdr
             * setWithCredentials
     * Modified
         * config
             * async
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * autoAbort
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * defaultPostHeader
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * method
                 * 2.4.1
                     * default value is undefined
                 * 6.0.0
                     * default value is null
             * password
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * username
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
         * method
             * request
                 * 2.4.1
                     * return type is Object/null
                 * 6.0.0
                     * return type is Ext.data.AjaxRequest
     * Removed
         * method
             * constructor
             * getUseDefaultHeader
             * parseStatus
             * setUseDefaultHeader
             * upload
 * Ext.data.DirectStore

     * Modified
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.data.Store
                 * 6.0.0
                     * return type is Ext.data.DirectStore
             * getProxy
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is String/Ext.data.proxy.Proxy/Object
 * Ext.data.JsonP

     * 2.4.1
         * alternateClassNames is [Ext.util.JSONP]
     * 6.0.0
         * alternateClassNames is []
 * Ext.data.JsonStore

     * 2.4.1
         * aliases is {widget=[jsonstore]}
     * 6.0.0
         * aliases is {store=[json]}
     * Modified
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.data.Store
                 * 6.0.0
                     * return type is Ext.data.JsonStore
 * Ext.data.Model

     * 2.4.1
         * mixins is [Ext.mixin.Observable]
     * 6.0.0
         * mixins is []
     * Added
         * config
             * convertOnSet
             * manyToMany
             * schema
             * validationSeparator
             * validators
             * versionProperty
         * method
             * abort
             * addFields
             * clone
             * drop
             * getCriticalFields
             * getModified
             * getPrevious
             * getProxy
             * getTransientFields
             * getValidation
             * isLoading
             * load
             * onLoad
             * removeFields
             * replaceFields
             * setSession
         * property
             * defaultProxy
             * dropped
             * entityName
             * erased
             * generation
             * isEntity
             * schema
             * session
             * store
     * Modified
         * config
             * clientIdProperty
                 * 2.4.1
                     * default value is 'clientId'
                 * 6.0.0
                     * default value is null
             * identifier
                 * 2.4.1
                     * default value is {type: 'simple'}
                     * type is Object/String
                 * 6.0.0
                     * default value is null
                     * type is String/Object
             * proxy
                 * 2.4.1
                     * type is Object/Ext.data.Proxy
                 * 6.0.0
                     * type is String/Object/Ext.data.proxy.Proxy
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * erase
                 * 2.4.1
                     * return type is Ext.data.Model
                 * 6.0.0
                     * return type is Ext.data.operation.Destroy
             * getFields
                 * 2.4.1
                     * return type is Object[]/String[]
                 * 6.0.0
                     * return type is Ext.data.field.Field[]
             * getObservableId
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
             * getProxy
                 * 2.4.1
                     * return type is Object/Ext.data.Proxy
                 * 6.0.0
                     * return type is Ext.data.proxy.Proxy
             * load
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.data.Model
             * save
                 * 2.4.1
                     * return type is Ext.data.Model
                 * 6.0.0
                     * return type is Ext.data.operation.Create/Ext.data.operation.Update/Ext.data.operation.Destroy
             * set
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is String[]
             * setProxy
                 * 2.4.1
                     * return type is void
                     * static is false
                 * 6.0.0
                     * return type is Ext.data.proxy.Proxy
                     * static is true
             * validate
                 * 2.4.1
                     * return type is Ext.data.Errors
                 * 6.0.0
                     * return type is Ext.data.ErrorCollection
         * property
             * fields
                 * 2.4.1
                     * private is false
                     * type is Ext.util.MixedCollection
                 * 6.0.0
                     * private is true
                     * type is Ext.data.field.Field[]
             * isModel
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * modified
                 * 2.4.1
                     * default value is {}
                 * 6.0.0
                     * default value is null
     * Removed
         * config
             * hasOne
             * useCache
             * validations
         * method
             * getAssociations
             * getBelongsTo
             * getClientIdProperty
             * getHasMany
             * getHasOne
             * getIdentifier
             * getIsErased
             * getUseCache
             * getValidations
             * setAssociations
             * setBelongsTo
             * setClientIdProperty
             * setConvertedData
             * setData
             * setDirty
             * setFields
             * setHasMany
             * setHasOne
             * setIdProperty
             * setIdentifier
             * setUseCache
             * setValidations
         * property
             * associations
             * raw
             * stores
             * validations
 * Ext.data.ModelManager

     * 2.4.1
         * alternateClassNames is [Ext.ModelMgr, Ext.ModelManager]
         * superclass is Ext.AbstractManager
     * 6.0.0
         * alternateClassNames is [Ext.ModelMgr]
         * superclass is Ext.Base
     * Removed
         * method
             * create
             * registerType
         * property
             * associationStack
             * defaultProxyType
 * Ext.data.NodeInterface

     * 2.4.1
         * alternateClassNames is [Ext.data.Node]
     * 6.0.0
         * alternateClassNames is []
     * Added
         * config
             * allowDrag
             * allowDrop
             * checked
             * children
             * cls
             * expandable
             * expanded
             * href
             * hrefTarget
             * icon
             * iconCls
             * leaf
             * qshowDelay
             * qtip
             * qtitle
             * text
         * method
             * collapseChildren
             * erase
             * expandChildren
             * fireEvent
             * getOwnerTree
             * getTreeStore
             * indexOfId
             * isBranchLoaded
             * serialize
         * property
             * isNode
     * Modified
         * method
             * createNode
                 * 2.4.1
                     * private is true
                     * return type is Boolean
                 * 6.0.0
                     * private is false
                     * return type is Ext.data.NodeInterface
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * insertChild
                 * 2.4.1
                     * return type is Ext.data.Model
                 * 6.0.0
                     * return type is Ext.data.NodeInterface
             * updateInfo
                 * 2.4.1
                     * protected is false
                     * return type is Boolean
                 * 6.0.0
                     * protected is true
                     * return type is void
         * property
             * childNodes
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Ext.data.NodeInterface[]
             * firstChild
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Ext.data.NodeInterface
             * lastChild
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Ext.data.NodeInterface
             * nextSibling
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Ext.data.NodeInterface
             * parentNode
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Ext.data.NodeInterface
             * previousSibling
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Ext.data.NodeInterface
 * Ext.data.Request

     * Added
         * config
             * binary
         * method
             * getBinary
             * getParam
             * setBinary
             * setParam
     * Modified
         * config
             * operation
                 * 2.4.1
                     * type is Ext.data.Operation
                 * 6.0.0
                     * type is Ext.data.operation.Operation
             * withCredentials
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is false
         * method
             * getOperation
                 * 2.4.1
                     * return type is Ext.data.Operation
                 * 6.0.0
                     * return type is Ext.data.operation.Operation
     * Removed
         * config
             * jsonp
 * Ext.data.ResultSet

     * Added
         * property
             * isResultSet
     * Modified
         * config
             * records
                 * 2.4.1
                     * type is Ext.data.Model[]
                 * 6.0.0
                     * type is Ext.data.Model[]/Object[]
         * method
             * getCount
                 * 2.4.1
                     * private is false
                     * return type is Number
                 * 6.0.0
                     * private is true
                     * return type is void
             * getRecords
                 * 2.4.1
                     * return type is Ext.data.Model[]
                 * 6.0.0
                     * return type is Ext.data.Model[]/Object[]
 * Ext.data.SortTypes

     * Added
         * property
             * stripCommasRe
 * Ext.data.Store

     * 2.4.1
         * mixins is []
         * superclass is Ext.Evented
     * 6.0.0
         * mixins is [Ext.data.LocalStore]
         * superclass is Ext.data.ProxyStore
     * Added
         * config
             * clearRemovedOnLoad
             * session
         * event
             * beforeprefetch
             * filterchange
             * groupchange
             * prefetch
         * method
             * addSorted
             * aggregate
             * collect
             * commitChanges
             * count
             * getByInternalId
             * getClearRemovedOnLoad
             * getSession
             * loadRawData
             * query
             * rejectChanges
             * setClearRemovedOnLoad
             * setSession
         * property
             * loadCount
     * Modified
         * config
             * data
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is 0
             * fields
                 * 2.4.1
                     * type is Object[]/Ext.util.Collection
                 * 6.0.0
                     * type is Object[]
             * filters
                 * 2.4.1
                     * type is Object[]
                 * 6.0.0
                     * type is Object[]/Function[]
             * groupDir
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is 'ASC'
             * grouper
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Object/Ext.util.Grouper
             * model
                 * 2.4.1
                     * type is String
                 * 6.0.0
                     * type is String/Ext.data.Model
             * sorters
                 * 2.4.1
                     * type is Object[]
                 * 6.0.0
                     * type is Ext.util.Sorter[]/Object[]
         * method
             * applyData
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * average
                 * 2.4.1
                     * return type is Number
                 * 6.0.0
                     * return type is Object
             * getAt
                 * 2.4.1
                     * return type is Ext.data.Model/undefined
                 * 6.0.0
                     * return type is Ext.data.Model
             * getById
                 * 2.4.1
                     * return type is Ext.data.Model/undefined
                 * 6.0.0
                     * return type is Ext.data.Model
             * getData
                 * 2.4.1
                     * return type is Object[]/Ext.data.Model[]
                 * 6.0.0
                     * return type is Ext.util.Collection
             * getFields
                 * 2.4.1
                     * return type is Object[]/Ext.util.Collection
                 * 6.0.0
                     * return type is Object[]
             * getGroupField
                 * 2.4.1
                     * private is false
                     * return type is String
                 * 6.0.0
                     * private is true
                     * return type is void
             * getGrouper
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Object/Ext.util.Grouper
             * getGroups
                 * 2.4.1
                     * return type is Object/Object[]
                 * 6.0.0
                     * return type is Ext.util.Collection
             * getModel
                 * 2.4.1
                     * return type is String
                 * 6.0.0
                     * return type is String/Ext.data.Model
             * insert
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.data.Model[]
             * load
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
             * loadRecords
                 * 2.4.1
                     * return type is Ext.data.Model[]
                 * 6.0.0
                     * return type is void
             * max
                 * 2.4.1
                     * return type is Object/undefined
                 * 6.0.0
                     * return type is Object
             * min
                 * 2.4.1
                     * return type is Object/undefined
                 * 6.0.0
                     * return type is Object
             * queryBy
                 * 2.4.1
                     * return type is Ext.util.MixedCollection
                 * 6.0.0
                     * return type is Ext.util.Collection
             * removeAll
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.data.Model[]
             * setFields
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
             * sync
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.data.Store
     * Removed
         * config
             * buffered
             * destroyRemovedRecords
             * getGroupString
             * params
             * plugins
             * remoteGroup
             * syncRemovedRecords
             * totalCount
         * event
             * addrecords
             * removerecords
             * updaterecord
         * method
             * addData
             * getAllCount
             * getBuffered
             * getDestroyRemovedRecords
             * getGetGroupString
             * getGroupString
             * getModelDefaults
             * getParams
             * getPlugins
             * getRemoteGroup
             * getSyncRemovedRecords
             * isAutoLoading
             * setBuffered
             * setDestroyRemovedRecords
             * setGetGroupString
             * setModelDefaults
             * setParams
             * setPlugins
             * setRemoteGroup
             * setSyncRemovedRecords
             * setTotalCount
 * Ext.data.StoreManager

     * 2.4.1
         * superclass is Ext.util.Collection
     * 6.0.0
         * superclass is Ext.util.MixedCollection
 * Ext.data.TreeStore

     * 2.4.1
         * superclass is Ext.data.NodeStore
     * 6.0.0
         * superclass is Ext.data.Store
     * Added
         * config
             * clearRemovedOnLoad
             * defaultRootText
             * lazyFill
             * parentIdProperty
         * event
             * nodeappend
             * nodebeforeappend
             * nodebeforecollapse
             * nodebeforeexpand
             * nodebeforeinsert
             * nodebeforemove
             * nodebeforeremove
             * nodecollapse
             * nodeexpand
             * nodeinsert
             * nodemove
             * noderemove
             * nodesort
         * method
             * commitChanges
             * findNode
             * getClearRemovedOnLoad
             * getDefaultRootText
             * getParentIdProperty
             * setClearRemovedOnLoad
             * setDefaultRootText
             * setParentIdProperty
         * property
             * isTreeStore
     * Modified
         * config
             * defaultRootId
                 * 2.4.1
                     * default value is 'root'
                 * 6.0.0
                     * default value is "root"
             * defaultRootProperty
                 * 2.4.1
                     * default value is 'children'
                 * 6.0.0
                     * default value is "children"
             * fields
                 * 2.4.1
                     * type is Object[]/Ext.util.Collection
                 * 6.0.0
                     * type is Object[]
             * nodeParam
                 * 2.4.1
                     * default value is 'node'
                 * 6.0.0
                     * default value is "node"
             * root
                 * 2.4.1
                     * type is Ext.data.Model/Ext.data.NodeInterface/Object
                 * 6.0.0
                     * type is Ext.data.TreeModel/Ext.data.NodeInterface/Object
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.data.Store
                 * 6.0.0
                     * return type is Ext.data.TreeStore
             * getById
                 * 2.4.1
                     * return type is Ext.data.Model/undefined
                 * 6.0.0
                     * return type is Ext.data.Model
             * getRoot
                 * 2.4.1
                     * return type is Ext.data.Model/Ext.data.NodeInterface/Object
                 * 6.0.0
                     * return type is Ext.data.TreeModel/Ext.data.NodeInterface/Object
             * getRootNode
                 * 2.4.1
                     * return type is Ext.data.Model
                 * 6.0.0
                     * return type is Ext.data.NodeInterface
             * load
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
             * onProxyLoad
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * removeAll
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.data.Model[]
             * setRootNode
                 * 2.4.1
                     * return type is Ext.data.Model
                 * 6.0.0
                     * return type is Ext.data.NodeInterface
 * Ext.data.identifier.Sequential

     * 2.4.1
         * superclass is Ext.data.identifier.Simple
     * 6.0.0
         * superclass is Ext.data.identifier.Generator
     * Added
         * config
             * increment
         * method
             * getIncrement
             * setIncrement
     * Modified
         * config
             * prefix
                 * 2.4.1
                     * default value is ''
                 * 6.0.0
                     * default value is null
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.data.identifier.Sequential
                 * 6.0.0
                     * return type is Ext.data.identifier.Generator
             * generate
                 * 2.4.1
                     * private is true
                     * return type is void
                 * 6.0.0
                     * private is false
                     * return type is String/Number
 * Ext.data.identifier.Uuid

     * 2.4.1
         * superclass is Ext.data.identifier.Simple
     * 6.0.0
         * superclass is Ext.data.identifier.Generator
     * Added
         * config
             * clockSeq
             * salt
             * timestamp
     * Modified
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.data.identifier.Uuid
                 * 6.0.0
                     * return type is Ext.data.identifier.Generator
     * Removed
         * method
             * getVersion
             * setVersion
         * property
             * salt
             * timestamp
 * Ext.data.proxy.Ajax

     * Added
         * config
             * actionMethods
             * binary
             * paramsAsJson
         * method
             * abort
             * getActionMethods
             * getBinary
             * getParamsAsJson
             * setActionMethods
             * setBinary
             * setParamsAsJson
     * Modified
         * config
             * headers
                 * 2.4.1
                     * default value is undefined
                 * 6.0.0
                     * default value is null
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * doRequest
                 * 2.4.1
                     * protected is true
                     * return type is Object
                 * 6.0.0
                     * protected is false
                     * return type is void
     * Removed
         * property
             * actionMethods
 * Ext.data.proxy.Direct

     * Added
         * config
             * metadata
         * method
             * getMetadata
             * setMetadata
     * Modified
         * config
             * extraParams
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is {}
         * method
             * applyEncoding
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * doRequest
                 * 2.4.1
                     * protected is true
                 * 6.0.0
                     * protected is false
             * extractResponseData
                 * 2.4.1
                     * private is true
                     * return type is void
                 * 6.0.0
                     * private is false
                     * return type is Object
             * setException
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.data.proxy.JsonP

     * Added
         * method
             * encodeRecords
     * Modified
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * doRequest
                 * 2.4.1
                     * private is false
                     * protected is true
                     * return type is Object
                 * 6.0.0
                     * private is true
                     * protected is false
                     * return type is void
     * Removed
         * method
             * getDefaultWriterType
             * setDefaultWriterType
 * Ext.data.proxy.Memory

     * Added
         * config
             * enablePaging
         * method
             * erase
             * getEnablePaging
             * setEnablePaging
     * Modified
         * config
             * data
                 * 2.4.1
                     * default value is []
                 * 6.0.0
                     * default value is null
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
 * Ext.data.proxy.Proxy

     * 2.4.1
         * mixins is []
         * superclass is Ext.Evented
     * 6.0.0
         * mixins is [Ext.mixin.Factoryable, Ext.mixin.Observable]
         * superclass is Ext.Base
     * Added
         * method
             * erase
         * property
             * isSynchronous
     * Modified
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.Evented
                 * 6.0.0
                     * return type is Ext.data.proxy.Proxy
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
         * property
             * isProxy
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.data.proxy.Rest

     * Modified
         * config
             * actionMethods
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
         * method
             * buildUrl
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
         * property
             * actionMethods
                 * 2.4.1
                     * default value is {create: 'POST', read: 'GET', update: 'POST', destroy: 'POST'}
                 * 6.0.0
                     * default value is null
 * Ext.data.proxy.Server

     * Added
         * config
             * groupDirectionParam
             * idParam
             * simpleGroupMode
         * method
             * erase
             * getGroupDirectionParam
             * getIdParam
             * getSimpleGroupMode
             * setGroupDirectionParam
             * setIdParam
             * setSimpleGroupMode
     * Modified
         * config
             * directionParam
                 * 2.4.1
                     * default value is 'dir'
                 * 6.0.0
                     * default value is "dir"
             * filterParam
                 * 2.4.1
                     * default value is 'filter'
                 * 6.0.0
                     * default value is "filter"
             * groupParam
                 * 2.4.1
                     * default value is 'group'
                 * 6.0.0
                     * default value is "group"
             * limitParam
                 * 2.4.1
                     * default value is 'limit'
                 * 6.0.0
                     * default value is "limit"
             * pageParam
                 * 2.4.1
                     * default value is 'page'
                 * 6.0.0
                     * default value is "page"
             * sortParam
                 * 2.4.1
                     * default value is 'sort'
                 * 6.0.0
                     * default value is "sort"
             * startParam
                 * 2.4.1
                     * default value is 'start'
                 * 6.0.0
                     * default value is "start"
         * method
             * afterRequest
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * applyEncoding
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
             * doRequest
                 * 2.4.1
                     * protected is true
                 * 6.0.0
                     * protected is false
 * Ext.data.reader.Array

     * Modified
         * config
             * successProperty
                 * 2.4.1
                     * default value is 'success'
                 * 6.0.0
                     * default value is null
             * totalProperty
                 * 2.4.1
                     * default value is 'total'
                 * 6.0.0
                     * default value is null
 * Ext.data.reader.Json

     * Added
         * config
             * metaProperty
             * preserveRawData
         * method
             * getMetaProperty
             * getPreserveRawData
             * setMetaProperty
             * setPreserveRawData
     * Modified
         * config
             * record
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is null
 * Ext.data.reader.Reader

     * 2.4.1
         * aliases is {}
         * mixins is [Ext.mixin.Observable]
     * 6.0.0
         * aliases is {reader=[base]}
         * mixins is [Ext.mixin.Observable, Ext.mixin.Factoryable]
     * Added
         * config
             * keepRawData
             * readRecordsOnFailure
             * transform
             * typeProperty
         * event
             * exception
         * method
             * getKeepRawData
             * getReadRecordsOnFailure
             * getTransform
             * getTypeProperty
             * setKeepRawData
             * setReadRecordsOnFailure
             * setTransform
             * setTypeProperty
         * property
             * factoryConfig
     * Modified
         * config
             * messageProperty
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is ''
             * model
                 * 2.4.1
                     * private is true
                     * type is Object
                 * 6.0.0
                     * private is false
                     * type is String/Ext.data.Model
         * method
             * getData
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
             * getModel
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is String/Ext.data.Model
         * property
             * isReader
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * config
             * clientIdProperty
             * idProperty
             * root
         * method
             * getClientIdProperty
             * getIdProperty
             * setClientIdProperty
             * setIdProperty
 * Ext.data.reader.Xml

     * Added
         * config
             * namespace
         * method
             * getNamespace
             * setNamespace
         * property
             * xmlData
     * Modified
         * config
             * record
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is ''
 * Ext.data.writer.Json

     * Added
         * config
             * expandData
         * method
             * getExpandData
             * getExpandedData
             * setExpandData
     * Modified
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.data.writer.Writer
                 * 6.0.0
                     * return type is Ext.data.writer.Json
             * writeRecords
                 * 2.4.1
                     * private is true
                     * protected is false
                     * return type is void
                 * 6.0.0
                     * private is false
                     * protected is true
                     * return type is Ext.data.Request
     * Removed
         * config
             * root
         * method
             * getEncodeRequest
             * setEncodeRequest
 * Ext.data.writer.Writer

     * 2.4.1
         * mixins is []
     * 6.0.0
         * mixins is [Ext.mixin.Factoryable]
     * Added
         * config
             * allDataOptions
             * clientIdProperty
             * dateFormat
             * partialDataOptions
             * transform
             * writeRecordId
         * method
             * getAllDataOptions
             * getClientIdProperty
             * getDateFormat
             * getPartialDataOptions
             * getTransform
             * getWriteRecordId
             * setAllDataOptions
             * setClientIdProperty
             * setDateFormat
             * setPartialDataOptions
             * setTransform
             * setWriteRecordId
             * writeRecords
         * property
             * factoryConfig
             * isWriter
     * Modified
         * config
             * writeAllFields
                 * 2.4.1
                     * default value is true
                 * 6.0.0
                     * default value is false
 * Ext.data.writer.Xml

     * Added
         * method
             * objectToElement
     * Modified
         * method
             * writeRecords
                 * 2.4.1
                     * protected is false
                     * return type is Object
                 * 6.0.0
                     * protected is true
                     * return type is Ext.data.Request
 * Ext.dataview.DataView

     * Added
         * property
             * defaultBindProperty
     * Modified
         * method
             * indexOf
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * config
             * blockRefresh
             * itemSelector
             * multiSelect
             * overItemCls
             * selectedItemCls
             * simpleSelect
             * singleSelect
             * trackOver
         * method
             * bindStore
             * collectData
             * findItemByChild
             * findTargetByEvent
             * getNode
             * getNodes
             * getRecords
             * getSelectedNodes
             * getSelectedRecords
             * refreshNode
 * Ext.dataview.IndexBar

     * Modified
         * cssVar
             * $index-bar-bg-color
                 * 2.4.1
                     * default value is hsla ( hue ( $base-color ) , 10% , 60% , .8 )
                 * 6.0.0
                     * default value is hsla ( hue ( $base-color , 10% , 60% , .8 ) )
             * $index-bar-color
                 * 2.4.1
                     * default value is darken ( desaturate ( $base-color , 5% ) , 15% )
                 * 6.0.0
                     * default value is darken ( desaturate ( $base-color , 5% , 15% ) )
         * method
             * getElementConfig
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
     * Removed
         * config
             * alphabet
             * itemSelector
             * store
         * method
             * isHorizontal
             * isVertical
             * refresh
 * Ext.dataview.List

     * 2.4.1
         * mixins is [Ext.mixin.Bindable]
     * 6.0.0
         * mixins is [Ext.mixin.Hookable]
     * Added
         * config
             * bufferSize
         * cssVar
             * $list-group-header-background-color
             * $list-group-header-border-color
             * $list-group-header-color
             * $list-group-header-font-family
             * $list-group-header-font-size
             * $list-group-header-font-size-big
             * $list-group-header-font-weight
             * $list-group-header-line-height
             * $list-group-header-line-height-big
             * $list-group-header-padding
             * $list-group-header-padding-big
             * $list-item-background-color
             * $list-item-border-color
             * $list-item-color
             * $list-item-font-family
             * $list-item-font-size
             * $list-item-font-size-big
             * $list-item-font-weight
             * $list-item-line-height
             * $list-item-line-height-big
             * $list-item-padding
             * $list-item-padding-big
             * $list-item-pressed-background-color
             * $list-item-selected-background-color
         * method
             * getBufferSize
             * setBufferSize
     * Modified
         * config
             * itemHeight
                 * 2.4.1
                     * default value is 42
                 * 6.0.0
                     * default value is null
             * variableHeights
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
         * cssVar
             * $list-active-color
                 * 2.4.1
                     * default value is $active-color
                 * 6.0.0
                     * default value is null
             * $list-active-gradient
                 * 2.4.1
                     * default value is $base-gradient
                 * 6.0.0
                     * default value is null
             * $list-bg-color
                 * 2.4.1
                     * default value is #f7f7f7
                 * 6.0.0
                     * default value is null
             * $list-color
                 * 2.4.1
                     * default value is #000
                 * 6.0.0
                     * default value is null
             * $list-disclosure-size
                 * 2.4.1
                     * default value is 32px
                 * 6.0.0
                     * default value is 26px
             * $list-header-bg-color
                 * 2.4.1
                     * default value is lighten ( saturate ( $base-color , 10% ) , 20% )
                 * 6.0.0
                     * default value is null
             * $list-header-gradient
                 * 2.4.1
                     * default value is $base-gradient
                 * 6.0.0
                     * default value is null
             * $list-pressed-color
                 * 2.4.1
                     * default value is lighten ( $active-color , 50% )
                 * 6.0.0
                     * default value is null
         * method
             * getScrollable
                 * 2.4.1
                     * private is true
                     * return type is Object
                 * 6.0.0
                     * private is false
                     * return type is Boolean
             * getVariableHeights
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * setVariableHeights
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * cssVar
             * $include-list-highlights
         * method
             * getUseHeaders
             * setUseHeaders
         * property
             * bufferSize
 * Ext.dataview.NestedList

     * Modified
         * config
             * itemHeight
                 * 2.4.1
                     * default value is 47
                 * 6.0.0
                     * default value is null
     * Removed
         * config
             * clearSelectionDelay
         * method
             * getSubList
 * Ext.dataview.component.ListItem

     * Modified
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
 * Ext.direct.Event

     * Modified
         * method
             * getData
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Mixed
     * Removed
         * config
             * data
             * name
         * method
             * getCode
             * getMessage
             * getResult
             * getStatus
             * getTransaction
             * getXhr
             * setCode
             * setData
             * setMessage
             * setName
             * setResult
             * setStatus
             * setTransaction
             * setXhr
 * Ext.direct.ExceptionEvent

     * Removed
         * config
             * name
         * method
             * getError
             * getStatus
             * setError
             * setName
             * setStatus
 * Ext.direct.JsonProvider

     * Modified
         * method
             * createEvents
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.direct.Manager

     * Added
         * config
             * varName
         * event
             * providerload
             * providerloaderror
         * method
             * getVarName
             * loadProvider
             * setVarName
     * Modified
         * method
             * addProvider
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
             * getProvider
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
             * parseMethod
                 * 2.4.1
                     * protected is true
                 * 6.0.0
                     * protected is false
             * removeProvider
                 * 2.4.1
                     * return type is Ext.direct.Provider/null
                 * 6.0.0
                     * return type is Ext.direct.Provider
         * property
             * exceptions
                 * 2.4.1
                     * default value is {TRANSPORT: 'xhr', PARSE: 'parse', LOGIN: 'login', SERVER: 'exception'}
                     * private is true
                 * 6.0.0
                     * default value is {TRANSPORT: 'xhr', PARSE: 'parse', DATA: 'data', LOGIN: 'login', SERVER: 'exception'}
                     * private is false
 * Ext.direct.PollingProvider

     * Added
         * config
             * pollFn
         * method
             * checkConfig
             * doConnect
             * doDisconnect
     * Modified
         * method
             * getInterval
                 * 2.4.1
                     * private is false
                     * return type is Number
                 * 6.0.0
                     * private is true
                     * return type is void
             * isConnected
                 * 2.4.1
                     * return type is Boolean
                 * 6.0.0
                     * return type is void
             * setInterval
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * method
             * getBaseParams
             * getUrl
             * setBaseParams
             * setUrl
 * Ext.direct.Provider

     * Added
         * config
             * relayedEvents
         * method
             * checkConfig
             * doConnect
             * doDisconnect
     * Modified
         * method
             * isConnected
                 * 2.4.1
                     * return type is Boolean
                 * 6.0.0
                     * return type is void
         * property
             * isProvider
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * method
             * getId
             * setId
 * Ext.direct.RemotingEvent

     * Removed
         * config
             * name
         * method
             * getTid
             * setName
             * setTid
             * setTransaction
 * Ext.direct.RemotingProvider

     * Added
         * config
             * disableNestedActions
         * event
             * beforecallback
         * method
             * checkConfig
             * doConnect
     * Modified
         * config
             * actions
                 * 2.4.1
                     * default value is {}
                 * 6.0.0
                     * default value is null
             * enableUrlEncode
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is data
         * method
             * getNamespace
                 * 2.4.1
                     * private is false
                     * return type is String/Object
                 * 6.0.0
                     * private is true
                     * return type is void
             * isConnected
                 * 2.4.1
                     * return type is Boolean
                 * 6.0.0
                     * return type is void
     * Removed
         * method
             * getActions
             * getEnableBuffer
             * getEnableUrlEncode
             * getMaxRetries
             * getTimeout
             * getUrl
             * setActions
             * setEnableBuffer
             * setEnableUrlEncode
             * setMaxRetries
             * setNamespace
             * setTimeout
             * setUrl
 * Ext.direct.Transaction

     * Modified
         * config
             * provider
                 * 2.4.1
                     * private is true
                     * type is Object
                 * 6.0.0
                     * private is false
                     * type is Ext.direct.Provider
         * method
             * getProvider
                 * 2.4.1
                     * private is false
                     * return type is Object
                 * 6.0.0
                     * private is true
                     * return type is void
     * Removed
         * method
             * getAction
             * getArgs
             * getCallback
             * getData
             * getForm
             * getId
             * getMethod
             * getRetryCount
             * setAction
             * setArgs
             * setCallback
             * setData
             * setForm
             * setId
             * setMethod
             * setProvider
             * setRetryCount
 * Ext.dom.CompositeElementLite

     * 2.4.1
         * alternateClassNames is [Ext.CompositeElementLite, Ext.CompositeElement]
     * 6.0.0
         * alternateClassNames is [Ext.CompositeElementLite]
     * Added
         * config
             * bubbleEvents
         * method
             * slice
     * Modified
         * method
             * addListener
                 * 2.4.1
                     * return type is Ext.dom.CompositeElementLite
                 * 6.0.0
                     * return type is Object
         * property
             * elements
                 * 2.4.1
                     * default value is []
                 * 6.0.0
                     * default value is null
             * isComposite
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.dom.Element

     * 2.4.1
         * aliases is {widget=[element]}
         * mixins is [Ext.mixin.Observable]
     * 6.0.0
         * aliases is {}
         * mixins is [Ext.util.Positionable, Ext.mixin.Observable]
     * Added
         * event
             * DOMActivate
             * DOMAttrModified
             * DOMCharacterDataModified
             * DOMFocusIn
             * DOMFocusOut
             * DOMNodeInserted
             * DOMNodeInsertedIntoDocument
             * DOMNodeRemoved
             * DOMNodeRemovedFromDocument
             * DOMSubtreeModified
             * abort
             * blur
             * change
             * click
             * contextmenu
             * dblclick
             * error
             * focus
             * focusmove
             * keydown
             * keypress
             * keyup
             * load
             * mousedown
             * mouseenter
             * mouseleave
             * mousemove
             * mouseout
             * mouseover
             * mouseup
             * reset
             * scroll
             * select
             * submit
             * unload
         * method
             * blur
             * cacheScrollValues
             * center
             * clone
             * focus
             * getActiveElement
             * getAttributes
             * getById
             * getCommonAncestor
             * getScroll
             * getScrollLeft
             * getScrollTop
             * getTextWidth
             * getZIndex
             * isScrollable
             * isVisible
             * position
             * query
             * scroll
             * scrollBy
             * scrollIntoView
             * scrollTo
             * selectNode
             * setDisplayed
             * setOpacity
             * setScrollLeft
             * setScrollTop
             * setZIndex
             * toggle
         * property
             * CLIP
             * component
     * Modified
         * method
             * appendChild
                 * 2.4.1
                     * return type is Ext.dom.Element
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * createChild
                 * 2.4.1
                     * return type is Ext.dom.Element
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * findParent
                 * 2.4.1
                     * return type is HTMLElement/null
                 * 6.0.0
                     * return type is HTMLElement/Ext.dom.Element
             * findParentNode
                 * 2.4.1
                     * return type is HTMLElement/null
                 * 6.0.0
                     * return type is HTMLElement/Ext.dom.Element
             * first
                 * 2.4.1
                     * return type is Ext.dom.Element/HTMLElement/null
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * getAlignToXY
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Number[]
             * getAnchorXY
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Number[]
             * getOffsetsTo
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Number[]
             * getPageBox
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Object/Ext.util.Region
             * getStyle
                 * 2.4.1
                     * return type is String
                 * 6.0.0
                     * return type is String/Object
             * hide
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.dom.Element
             * insertFirst
                 * 2.4.1
                     * return type is Ext.dom.Element
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * insertSibling
                 * 2.4.1
                     * return type is Ext.dom.Element
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * isAncestor
                 * 2.4.1
                     * private is true
                     * static is true
                 * 6.0.0
                     * private is false
                     * static is false
             * last
                 * 2.4.1
                     * return type is Ext.dom.Element/HTMLElement/null
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * next
                 * 2.4.1
                     * return type is Ext.dom.Element/HTMLElement/null
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * parent
                 * 2.4.1
                     * return type is Ext.dom.Element/HTMLElement/null
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * prev
                 * 2.4.1
                     * return type is Ext.dom.Element/HTMLElement/null
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * query
                 * 2.4.1
                     * return type is HTMLElement[]
                 * 6.0.0
                     * return type is HTMLElement[]/Ext.dom.Element[]
             * removeCls
                 * 2.4.1
                     * return type is Ext.dom.Element
                 * 6.0.0
                     * return type is void
             * setBox
                 * 2.4.1
                     * return type is Ext.dom.Element
                 * 6.0.0
                     * return type is Ext.util.Positionable
             * setHTML
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.dom.Element
             * setHtml
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.dom.Element
             * show
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.dom.Element
             * up
                 * 2.4.1
                     * return type is Ext.dom.Element/null
                 * 6.0.0
                     * return type is Ext.dom.Element/HTMLElement
             * update
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.dom.Element
         * property
             * DISPLAY
                 * 2.4.1
                     * static is false
                 * 6.0.0
                     * static is true
             * OFFSETS
                 * 2.4.1
                     * static is false
                 * 6.0.0
                     * static is true
             * VISIBILITY
                 * 2.4.1
                     * static is false
                 * 6.0.0
                     * static is true
     * Removed
         * method
             * mask
             * serializeForm
             * serializeNode
             * unmask
         * property
             * defaultUnit
 * Ext.dom.Query

     * 2.4.1
         * alternateClassNames is []
         * singleton is false
     * 6.0.0
         * alternateClassNames is [Ext.DomQuery, Ext.core.DomQuery]
         * singleton is true
     * Added
         * method
             * compile
             * filter
             * getNodeValue
             * jsSelect
             * selectNumber
             * selectValue
         * property
             * matchers
             * operators
             * pseudos
 * Ext.draw.Animator

     * Added
         * method
             * scheduleIf
 * Ext.draw.Color

     * Added
         * method
             * fromHSV
             * getHSV
             * setHSV
     * Modified
         * method
             * getHSL
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Number[]
             * setHSL
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.draw.Color
 * Ext.draw.Draw

     * Added
         * method
             * isPointInBBox
 * Ext.draw.Path

     * Added
         * method
             * getSegmentIntersections
             * isPointOnPath
 * Ext.draw.Surface

     * 2.4.1
         * superclass is Ext.Component
     * 6.0.0
         * superclass is Ext.draw.SurfaceBase
     * Added
         * config
             * flipRtlText
             * rect
         * method
             * flatten
             * getFlipRtlText
             * getRect
             * hitTest
             * hitTestEvent
             * setFlipRtlText
             * setRect
     * Modified
         * method
             * add
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.draw.sprite.Sprite/Ext.draw.sprite.Sprite[]
             * getCls
                 * 2.4.1
                     * return type is String/String[]
                 * 6.0.0
                     * return type is String
             * remove
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.draw.sprite.Sprite/null
             * stableSort
                 * 2.4.1
                     * return type is void
                     * static is true
                 * 6.0.0
                     * deprecated
                     * return type is Array
                     * static is false
     * Removed
         * config
             * region
         * method
             * getRegion
             * setRegion
 * Ext.draw.TextMeasurer

     * Added
         * config
             * precise
 * Ext.draw.engine.Canvas

     * Added
         * method
             * flatten
             * setLineDash
     * Modified
         * method
             * clearTransform
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * method
             * initElement
 * Ext.draw.engine.Svg

     * Added
         * method
             * flatten
     * Modified
         * method
             * remove
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.draw.sprite.Sprite/null
 * Ext.draw.gradient.Gradient

     * Added
         * config
             * stops
         * method
             * getStops
             * setStops
 * Ext.draw.gradient.Linear

     * Added
         * config
             * degrees
             * radians
         * method
             * getDegrees
             * getRadians
             * setDegrees
             * setRadians
 * Ext.draw.modifier.Animation

     * Added
         * config
             * customDurations
         * method
             * getCustomDurations
             * setCustomDurations
     * Modified
         * config
             * customDuration
                 * 2.4.1
                     * default value is {}
                 * 6.0.0
                     * deprecated
                     * default value is null
 * Ext.draw.modifier.Modifier

     * 2.4.1
         * mixins is []
     * 6.0.0
         * mixins is [Ext.mixin.Observable]
 * Ext.draw.sprite.Composite

     * Added
         * method
             * getSprites
             * setSprites
 * Ext.draw.sprite.Image

     * Modified
         * attributes
             * height
                 * 2.4.1
                     * default value is 1
                 * 6.0.0
                     * default value is null
             * width
                 * 2.4.1
                     * default value is 1
                 * 6.0.0
                     * default value is null
 * Ext.draw.sprite.Path

     * 2.4.1
         * aliases is {sprite=[path]}
     * 6.0.0
         * aliases is {sprite=[path], Ext=[draw.Sprite]}
     * Added
         * method
             * getIntersections
             * hitTest
             * isPointInPath
             * isPointOnPath
         * property
             * debug
 * Ext.draw.sprite.Rect

     * Modified
         * attributes
             * height
                 * 2.4.1
                     * default value is 1
                 * 6.0.0
                     * default value is 8
             * width
                 * 2.4.1
                     * default value is 1
                 * 6.0.0
                     * default value is 8
 * Ext.draw.sprite.Sprite

     * Added
         * config
             * surface
         * attributes
             * globalCompositeOperation
             * lineDash
             * lineDashOffset
         * method
             * getSurface
             * hitTest
             * remove
             * setSurface
     * Modified
         * config
             * parent
                 * 2.4.1
                     * private is true
                     * type is Object
                 * 6.0.0
                     * private is false
                     * type is Ext.draw.Surface/Ext.draw.sprite.Instancing/Ext.draw.sprite.Composite
         * attribute
             * miterLimit
                 * 2.4.1
                     * default value is 1
                 * 6.0.0
                     * default value is 10
         * method
             * getParent
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.draw.Surface/Ext.draw.sprite.Instancing/Ext.draw.sprite.Composite
 * Ext.draw.sprite.Text

     * Added
         * property
             * debug
 * Ext.event.Event

     * 2.4.1
         * alternateClassNames is [Ext.EventObject]
         * mixins is [Ext.event.Touch]
     * 6.0.0
         * alternateClassNames is [Ext.EventObjectImpl]
         * mixins is []
     * Added
         * method
             * getCharCode
             * getKey
             * getKeyName
             * getPoint
             * getRelatedTarget
             * getWheelDelta
             * getWheelDeltas
             * getX
             * getY
             * hasModifier
             * isNavKeyPress
             * isSpecialKey
             * within
         * property
             * A
             * ALT
             * B
             * BACKSPACE
             * C
             * CAPS_LOCK
             * CONTEXT_MENU
             * CTRL
             * D
             * DELETE
             * DOWN
             * E
             * EIGHT
             * END
             * ENTER
             * ESC
             * F
             * F1
             * F10
             * F11
             * F12
             * F2
             * F3
             * F4
             * F5
             * F6
             * F7
             * F8
             * F9
             * FIVE
             * FOUR
             * G
             * H
             * HOME
             * I
             * INSERT
             * J
             * K
             * L
             * LEFT
             * M
             * N
             * NINE
             * NUM_CENTER
             * NUM_DIVISION
             * NUM_EIGHT
             * NUM_FIVE
             * NUM_FOUR
             * NUM_MINUS
             * NUM_MULTIPLY
             * NUM_NINE
             * NUM_ONE
             * NUM_PERIOD
             * NUM_PLUS
             * NUM_SEVEN
             * NUM_SIX
             * NUM_THREE
             * NUM_TWO
             * NUM_ZERO
             * O
             * ONE
             * P
             * PAGE_DOWN
             * PAGE_UP
             * PAUSE
             * PRINT_SCREEN
             * Q
             * R
             * RETURN
             * RIGHT
             * S
             * SEVEN
             * SHIFT
             * SIX
             * SPACE
             * T
             * TAB
             * THREE
             * TWO
             * U
             * UP
             * V
             * W
             * WHEEL_SCALE
             * X
             * Y
             * Z
             * ZERO
             * altKey
             * browserEvent
             * button
             * ctrlKey
             * currentTarget
             * defaultPrevented
             * delegatedTarget
             * shiftKey
     * Modified
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.event.Touch
                 * 6.0.0
                     * return type is Ext.event.Event
             * getXY
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Number[]
             * preventDefault
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Ext.event.Event
 * Ext.feature

     * 2.4.1
         * superclass is Ext.env.Feature
     * 6.0.0
         * superclass is null
 * Ext.field.Checkbox

     * Added
         * config
             * publishes
             * twoWayBindable
         * cssVar
             * $checkboxfield-checkbox-color
             * $checkboxfield-checkbox-font-size
             * $checkboxfield-checkbox-font-size-big
             * $checkboxfield-checkbox-icon
             * $checkboxfield-checkbox-size
             * $checkboxfield-checked-checkbox-icon
         * property
             * defaultBindProperty
     * Modified
         * method
             * getChecked
                 * 2.4.1
                     * return type is Mixed
                 * 6.0.0
                     * return type is Boolean
             * setChecked
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * method
             * doChecked
             * doUnChecked
 * Ext.field.DatePicker

     * 2.4.1
         * superclass is Ext.field.Select
     * 6.0.0
         * superclass is null
     * Modified
         * config
             * ui
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
         * method
             * reset
                 * 2.4.1
                     * private is false
                     * return type is Ext.field.Select
                 * 6.0.0
                     * private is true
                     * return type is void
     * Removed
         * method
             * getDatePicker
             * onChange
 * Ext.field.Field

     * Added
         * cssVar
             * $field-background-color
             * $field-border-color
             * $field-label-background-color
             * $field-label-border-color
             * $field-label-color
             * $field-label-font-family
             * $field-label-font-size
             * $field-label-font-size-big
             * $field-label-font-weight
             * $field-label-line-height
             * $field-label-line-height-big
             * $field-label-padding
             * $field-label-padding-big
         * property
     * Removed
         * config
             * fieldCls
             * fieldLabel
             * useClearIcon
         * cssVar
             * $form-field-border-bottom-color
             * $form-field-border-bottom-width
             * $form-field-color
             * $form-field-label-bg-color
             * $form-field-label-border-top-color
             * $form-field-label-border-top-width
             * $form-field-label-color
             * $form-field-label-text-shadow
             * $toolbar-input-bg
             * $toolbar-input-border-color
             * $toolbar-input-color
             * $toolbar-input-height
 * Ext.field.Radio

     * Added
         * cssVar
             * $radiofield-checkbox-color
             * $radiofield-checkbox-font-size
             * $radiofield-checkbox-font-size-big
             * $radiofield-checkbox-icon
             * $radiofield-checkbox-size
             * $radiofield-checked-checkbox-icon
 * Ext.field.Select

     * 2.4.1
         * superclass is Ext.field.Text
     * 6.0.0
         * superclass is null
     * Added
         * config
             * selection
             * useClearIcon
         * cssVar
             * $selectfield-trigger-color
             * $selectfield-trigger-font-size
             * $selectfield-trigger-font-size-big
             * $selectfield-trigger-icon
             * $selectfield-trigger-size
         * method
             * getSelection
             * setSelection
     * Modified
         * method
             * destroy
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
     * Removed
         * config
             * defaultPhonePickerConfig
             * defaultTabletPickerConfig
             * usePicker
         * method
             * getDefaultPhonePickerConfig
             * getDefaultTabletPickerConfig
             * getRecord
             * getUsePicker
             * setDefaultPhonePickerConfig
             * setDefaultTabletPickerConfig
             * setUsePicker
 * Ext.field.Slider

     * Added
         * config
             * liveUpdate
             * twoWayBindable
         * event
             * dragchange
         * method
             * getLiveUpdate
             * setLiveUpdate
         * property
             * defaultBindProperty
 * Ext.field.Spinner

     * Added
         * cssVar
             * $spinnerfield-button-color
             * $spinnerfield-button-down-icon
             * $spinnerfield-button-font-size
             * $spinnerfield-button-font-size-big
             * $spinnerfield-button-size
             * $spinnerfield-button-up-icon
     * Modified
         * method
             * getValue
                 * 2.4.1
                     * return type is Mixed
                 * 6.0.0
                     * return type is Number
     * Removed
         * config
             * increment
             * incrementValue
         * cssVar
             * $form-spinner-button-width
 * Ext.field.Text

     * Added
         * config
             * publishes
             * twoWayBindable
         * cssVar
             * $textfield-clear-icon
             * $textfield-clear-icon-color
             * $textfield-clear-icon-font-size
             * $textfield-clear-icon-font-size-big
             * $textfield-clear-icon-size
             * $textfield-input-background-color
             * $textfield-input-font-family
             * $textfield-input-font-size
             * $textfield-input-font-size-big
             * $textfield-input-font-weight
             * $textfield-input-line-height
             * $textfield-input-line-height-big
             * $textfield-input-padding
             * $textfield-input-padding-big
         * property
             * defaultBindProperty
     * Modified
         * config
             * bubbleEvents
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * component
                 * 2.4.1
                     * default value is {xtype: 'input', type: 'text', fastFocus: true}
                 * 6.0.0
                     * default value is {xtype: 'input', type: 'text', fastFocus: false}
     * Removed
         * property
             * startValue
 * Ext.field.TextArea

     * Added
         * method
             * updateHeight
             * updateWidth
     * Removed
         * cssVar
             * $form-textarea-height
 * Ext.field.Toggle

     * 2.4.1
         * superclass is Ext.field.Slider
     * 6.0.0
         * superclass is Ext.field.SingleSlider
     * Modified
         * config
             * value
                 * 2.4.1
                     * default value is 0
                     * type is Number/Number[]
                 * 6.0.0
                     * default value is false
                     * type is Boolean
         * method
             * getValue
                 * 2.4.1
                     * return type is Number/Number[]
                 * 6.0.0
                     * return type is Boolean
             * setValue
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
 * Ext.form.FieldSet

     * Added
         * cssVar
             * $fieldset-border-color
             * $fieldset-border-radius
             * $fieldset-border-width
             * $fieldset-title-color
         * method
             * updateDisabled
         * property
     * Removed
         * cssVar
             * $form-fieldset-border-color
             * $form-fieldset-border-width
             * $form-fieldset-title-color
             * $form-fieldset-title-text-shadow
         * method
             * doSetDisabled
 * Ext.form.Panel

     * Added
         * cssVar
             * $formpanel-body-background-color
         * method
             * updateDisabled
         * property
     * Modified
         * config
             * enctype
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is String
             * scrollable
                 * 2.4.1
                     * default value is {translatable: {translationMethod: 'scrollposition'}}
                 * 6.0.0
                     * default value is {}
         * cssVar
             * $form-spacing
                 * 2.4.1
                     * default value is .6em
                 * 6.0.0
                     * default value is .3em
         * method
             * getElementConfig
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
     * Removed
         * config
             * waitMsgTarget
             * waitTpl
         * method
             * doSetDisabled
             * loadModel
             * loadRecord
 * Ext.grid.Grid

     * Added
         * event
             * columnmove
     * Modified
         * config
             * variableHeights
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
         * method
             * getVariableHeights
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * setVariableHeights
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.grid.HeaderContainer

     * Modified
         * method
             * getHeight
                 * 2.4.1
                     * return type is Number
                 * 6.0.0
                     * return type is Number/String
 * Ext.grid.HeaderGroup

     * Added
         * property
             * columns
     * Modified
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
 * Ext.grid.Row

     * Added
         * method
             * getHeader
             * setHeader
 * Ext.grid.column.Action

     * Modified
         * method
             * defaultRenderer
                 * 2.4.1
                     * private is false
                     * protected is true
                 * 6.0.0
                     * private is true
                     * protected is false
 * Ext.grid.column.Boolean

     * Added
         * method
             * getCell
             * setCell
     * Modified
         * config
             * falseText
                 * 2.4.1
                     * default value is 'False'
                 * 6.0.0
                     * default value is 'false'
             * trueText
                 * 2.4.1
                     * default value is 'True'
                 * 6.0.0
                     * default value is 'true'
     * Removed
         * method
             * defaultRenderer
 * Ext.grid.column.Column

     * Added
         * config
             * groupable
         * method
             * getCell
             * getGroupable
             * setCell
             * setGroupable
             * updateWidth
     * Removed
         * method
             * defaultRenderer
 * Ext.grid.column.Date

     * Added
         * method
             * getCell
             * setCell
     * Removed
         * method
             * defaultRenderer
 * Ext.grid.column.Number

     * Added
         * method
             * getCell
             * setCell
     * Removed
         * method
             * defaultRenderer
 * Ext.grid.column.Template

     * Removed
         * method
             * defaultRenderer
 * Ext.grid.plugin.Editable

     * Added
         * config
             * formConfig
             * triggerEvent
         * method
             * getFormConfig
             * getTriggerEvent
             * setFormConfig
             * setTriggerEvent
     * Modified
         * config
             * defaultFormConfig
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * enableDeleteButton
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * toolbarConfig
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * property
             * formConfig
             * triggerEvent
 * Ext.grid.plugin.MultiSelection

     * 2.4.1
         * superclass is null
     * 6.0.0
         * superclass is Ext.Component
     * Modified
         * config
             * cancelText
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * deleteText
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * selectionColumn
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * triggerText
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * useTriggerButton
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
         * method
             * getGrid
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * setGrid
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.grid.plugin.PagingToolbar

     * 2.4.1
         * mixins is [Ext.mixin.Bindable]
     * 6.0.0
         * mixins is [Ext.mixin.Hookable]
 * Ext.grid.plugin.SummaryRow

     * 2.4.1
         * mixins is [Ext.mixin.Bindable]
     * 6.0.0
         * mixins is [Ext.mixin.Hookable]
     * Modified
         * method
             * getHeight
                 * 2.4.1
                     * return type is Number
                 * 6.0.0
                     * return type is Number/String
 * Ext.grid.plugin.ViewOptions

     * Added
         * config
             * groupIndicatorSelector
         * method
             * getGroupIndicatorSelector
             * setGroupIndicatorSelector
     * Modified
         * config
             * columnList
                 * 2.4.1
                     * default value is {xtype: 'nestedlist', title: 'Column', listConfig: {plugins: [{type: 'sortablelist', handleSelector: '.x-column-options-sortablehandle'}], mode: 'MULTI', infinite: true, itemTpl: ['<div class="x-column-options-sortablehandle"></div>', '<tpl if="header">', '<div class="x-column-options-folder"></div>', '<tpl else>', '<div class="x-column-options-leaf"></div>', '</tpl>', '<div class="x-column-options-text">{text}</div>', '<div class="x-column-options-visibleindicator"></div>'], triggerEvent: null, bufferSize: 1, minimumBufferSize: 1}, store: {type: 'tree', fields: ['id', 'text', 'header'], root: {text: 'Columns'}}, clearSelectionOnListChange: false}
                     * private is true
                 * 6.0.0
                     * default value is {xtype: 'nestedlist', title: 'Column', listConfig: {plugins: [{type: 'sortablelist', handleSelector: '.x-column-options-sortablehandle'}], mode: 'MULTI', infinite: true, itemTpl: ['<div class="x-column-options-itemwrap<tpl if="hidden"> {hiddenCls}</tpl>', '<tpl if="grouped"> {groupedCls}</tpl>">', '<div class="x-column-options-sortablehandle"></div>', '<tpl if="header">', '<div class="x-column-options-folder"></div>', '<tpl else>', '<div class="x-column-options-leaf"></div>', '</tpl>', '<div class="x-column-options-text">{text}</div>', '<tpl if="groupable">', '<div class="x-column-options-groupindicator"></div>', '</tpl>', '<div class="x-column-options-visibleindicator"></div>', '</div>'], triggerEvent: null, bufferSize: 1, minimumBufferSize: 1}, store: {type: 'tree', fields: ['id', 'text', 'dataIndex', 'header', 'hidden', 'hiddenCls', 'grouped', 'groupedCls', 'groupable'], root: {text: 'Columns'}}, clearSelectionOnListChange: false}
                     * private is false
             * sheet
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * sheetWidth
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * visibleIndicatorSelector
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
         * property
             * sheetVisible
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.mixin.Bindable

     * 2.4.1
         * superclass is Ext.mixin.Mixin
     * 6.0.0
         * superclass is Ext.Base
 * Ext.mixin.Observable

     * 2.4.1
         * alternateClassNames is [Ext.util.Observable]
         * mixins is [Ext.mixin.Identifiable]
         * superclass is Ext.mixin.Mixin
     * 6.0.0
         * alternateClassNames is []
         * mixins is []
         * superclass is Ext.Base
     * Added
         * method
             * capture
             * fireEventArgs
             * fireEventedAction
             * isSuspended
             * observe
             * releaseCapture
             * resolveListenerScope
             * resumeEvent
             * suspendEvent
         * property
             * hasListeners
     * Modified
         * method
             * clearManagedListeners
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * fireAction
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is void
             * mon
                 * 2.4.1
                     * return type is void
                 * 6.0.0
                     * return type is Object
             * relayEvents
                 * 2.4.1
                     * return type is Ext.mixin.Observable
                 * 6.0.0
                     * return type is Object
         * property
             * isObservable
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * config
             * bubbleEvents
         * method
             * addEvents
             * constructor
             * getBubbleEvents
             * getListeners
             * setBubbleEvents
 * Ext.mixin.Templatable

     * 2.4.1
         * superclass is Ext.mixin.Mixin
     * 6.0.0
         * superclass is Ext.Mixin
 * Ext.picker.Picker

     * Modified
         * cssVar
             * $picker-active-border-color
                 * 2.4.1
                     * default value is $active-color
                 * 6.0.0
                     * default value is red
             * $picker-row-height
                 * 2.4.1
                     * default value is 2.5em
                 * 6.0.0
                     * default value is 80px
             * $picker-title-bg-color
                 * 2.4.1
                     * default value is lighten ( saturate ( $base-color , 10% ) , 5% )
                 * 6.0.0
                     * default value is null
             * $picker-title-color
                 * 2.4.1
                     * default value is darken ( desaturate ( $base-color , 10% ) , 25% )
                 * 6.0.0
                     * default value is null
         * method
             * destroy
                 * 2.4.1
                     * protected is false
                 * 6.0.0
                     * protected is true
     * Removed
         * config
             * activeCls
         * cssVar
             * $include-picker-highlights
             * $picker-bar-gradient
             * $picker-title-bg-gradient
         * method
             * getCard
             * setCard
 * Ext.plugin.PullRefresh

     * Modified
         * method
             * getElementConfig
                 * 2.4.1
                     * private is true
                     * protected is false
                 * 6.0.0
                     * private is false
                     * protected is true
     * Removed
         * config
             * pullRefreshText
             * pullReleaseText
         * method
             * setPullRefreshText
             * setReleaseRefreshText
 * Ext.plugin.SortableList

     * 2.4.1
         * mixins is [Ext.mixin.Bindable]
     * 6.0.0
         * mixins is [Ext.mixin.Hookable]
 * Ext.scroll.Indicator

     * 2.4.1
         * aliases is {}
         * alternateClassNames is [Ext.util.Indicator]
         * superclass is Ext.Base
     * 6.0.0
         * aliases is {widget=[scrollindicator]}
         * alternateClassNames is []
         * superclass is Ext.Widget
     * Added
         * config
             * hideDelay
             * minLength
         * method
             * getHideDelay
             * getMinLength
             * hide
             * setHideDelay
             * setMinLength
             * setValue
             * show
 * Ext.scroll.Scroller

     * 2.4.1
         * aliases is {}
         * mixins is []
     * 6.0.0
         * aliases is {scroller=[scroller]}
         * mixins is [Ext.mixin.Factoryable]
     * Added
         * config
             * indicators
             * x
             * y
         * method
             * addPartner
             * getClientSize
             * getIndicators
             * getMaxUserPosition
             * getPosition
             * getScroller
             * getX
             * getY
             * isInView
             * setIndicators
             * setX
             * setY
         * property
             * factoryConfig
     * Modified
         * config
             * element
                 * 2.4.1
                     * private is true
                     * type is Object
                 * 6.0.0
                     * private is false
                     * type is String/HTMLElement/Ext.dom.Element
             * momentumEasing
                 * 2.4.1
                     * default value is {momentum: {acceleration: 30, friction: 0.5}, bounce: {acceleration: 30, springTension: 0.3}, minVelocity: 1}
                 * 6.0.0
                     * default value is null
         * method
             * constructor
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * create
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Ext.scroll.Scroller
             * getElement
                 * 2.4.1
                     * private is true
                     * return type is Object
                 * 6.0.0
                     * private is false
                     * return type is String/HTMLElement/Ext.dom.Element
             * getMaxPosition
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * getSize
                 * 2.4.1
                     * private is true
                     * return type is String
                 * 6.0.0
                     * private is false
                     * return type is Object
             * refresh
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
             * scrollBy
                 * 2.4.1
                     * return type is Ext.scroll.Scroller
                 * 6.0.0
                     * return type is void
             * scrollToEnd
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
             * setElement
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
     * Removed
         * config
             * acceleration
             * friction
             * initialOffset
         * event
             * maxpositionchange
         * method
             * getInitialOffset
             * getSlotSnapEasing
             * getTranslatable
             * isAxisEnabled
             * setInitialOffset
             * setOffset
             * setSlotSnapEasing
             * setTranslatable
             * updateBoundary
 * Ext.supports

     * 2.4.1
         * singleton is false
     * 6.0.0
         * singleton is true
     * Added
         * property
             * Audio
             * BoundingClientRect
             * CSS3BorderRadius
             * CSS3BoxShadow
             * CSS3LinearGradient
             * CSSPointerEvents
             * Canvas
             * ChildContentClearedWhenSettingInnerHTML
             * ClassList
             * CloneNodeCopiesExpando
             * ComputedStyle
             * CreateContextualFragment
             * Css3DTransforms
             * DeviceMotion
             * Direct2DBug
             * DisplayChangeInputSelectionBug
             * DisplayChangeTextAreaSelectionBug
             * EmulatedMouseOver
             * Float
             * Geolocation
             * GetPositionPercentage
             * Hashchange
             * HighContrastMode
             * History
             * LocalStorage
             * MouseEnterLeave
             * MouseWheel
             * NumericInputPlaceHolder
             * Opacity
             * Orientation
             * OrientationChange
             * Placeholder
             * Range
             * RightMargin
             * RotatedBoundingClientRect
             * ScrollWidthInlinePaddingBug
             * Svg
             * TextAreaMaxLength
             * Touch
             * TouchEvents
             * TransparentColor
             * Video
             * Vml
             * XHR2
             * XHRUploadProgress
             * matchesSelector
     * Modified
         * property
             * AudioTag
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Boolean
             * GeoLocation
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Boolean
             * Transitions
                 * 2.4.1
                     * type is Object
                 * 6.0.0
                     * type is Boolean
     * Removed
         * property
             * SVG
             * VML
 * Ext.tab.Panel

     * Added
         * config
             * scroll
     * Removed
         * config
             * tabBarDock
 * Ext.util.BufferedCollection

     * 2.4.1
         * mixins is [Ext.util.Observable]
     * 6.0.0
         * mixins is [Ext.mixin.Observable]
 * Ext.util.Collection

     * 2.4.1
         * mixins is [Ext.mixin.Sortable, Ext.mixin.Filterable]
     * 6.0.0
         * mixins is [Ext.mixin.Observable]
     * Added
         * config
             * decoder
             * extraKeys
             * grouper
             * groups
             * keyFn
             * multiSortLimit
             * rootProperty
             * source
         * event
             * add
             * beforeitemchange
             * beginupdate
             * endupdate
             * itemchange
             * refresh
             * remove
             * sort
             * updatekey
         * method
             * aggregate
             * aggregateByGroup
             * average
             * averageByGroup
             * beginUpdate
             * bounds
             * boundsByGroup
             * collect
             * count
             * countByGroup
             * createFiltered
             * decodeRemoveItems
             * endUpdate
             * extremes
             * extremesByGroup
             * find
             * findIndex
             * getDecoder
             * getExtraKeys
             * getGrouper
             * getMultiSortLimit
             * getRootProperty
             * getSource
             * getValues
             * isItemFiltered
             * itemChanged
             * max
             * maxByGroup
             * maxItem
             * maxItemByGroup
             * min
             * minByGroup
             * minItem
             * minItemByGroup
             * onFilterChange
             * onSortChange
             * removeByKey
             * replaceAll
             * setDecoder
             * setExtraKeys
             * setGrouper
             * setGroups
             * setMultiSortLimit
             * setRootProperty
             * setSource
             * sortBy
             * sortData
             * sortItems
             * splice
             * sum
             * sumByGroup
             * update
             * updateKey
         * property
             * generation
             * grouped
             * isCollection
             * updating
     * Modified
         * config
             * filters
                 * 2.4.1
                     * type is Object[]
                 * 6.0.0
                     * type is Array/Ext.util.FilterCollection
             * sorters
                 * 2.4.1
                     * type is Object[]
                 * 6.0.0
                     * type is Array/Ext.util.SorterCollection
         * method
             * add
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Object/Object[]
             * clone
                 * 2.4.1
                     * return type is Ext.util.MixedCollection
                 * 6.0.0
                     * return type is Ext.util.Collection
             * destroy
                 * 2.4.1
                     * protected is true
                 * 6.0.0
                     * protected is false
             * filterBy
                 * 2.4.1
                     * return type is Ext.util.MixedCollection
                 * 6.0.0
                     * return type is Ext.util.Collection
             * getFilters
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Ext.util.FilterCollection
             * getSorters
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Ext.util.SorterCollection
             * insert
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Object/Object[]
             * remove
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Number
             * removeAll
                 * 2.4.1
                     * return type is Ext.util.MixedCollection
                 * 6.0.0
                     * return type is Ext.util.Collection
             * removeAt
                 * 2.4.1
                     * return type is Object
                 * 6.0.0
                     * return type is Object/Number
             * sort
                 * 2.4.1
                     * return type is Array
                 * 6.0.0
                     * return type is Ext.util.Collection
 * Ext.util.DelayedTask

     * 2.4.1
         * mixins is []
         * superclass is Ext.Base
     * 6.0.0
         * mixins is null
         * superclass is null
     * Added
         * property
             * id
     * Removed
         * method
             * getArgs
             * getDelay
             * getFn
             * getInterval
             * getScope
             * setArgs
             * setDelay
             * setFn
             * setInterval
             * setScope
 * Ext.util.Filter

     * Added
         * config
             * disableOnEmpty
             * disabled
             * operator
         * method
             * getDisableOnEmpty
             * getDisabled
             * getOperator
             * getState
             * serialize
             * setDisableOnEmpty
             * setDisabled
             * setOperator
     * Modified
         * config
             * scope
                 * 2.4.1
                     * default value is null
                 * 6.0.0
                     * default value is null
         * method
             * createFilterFn
                 * 2.4.1
                     * private is true
                     * return type is void
                     * static is false
                 * 6.0.0
                     * private is false
                     * return type is Function
                     * static is true
             * getFilterFn
                 * 2.4.1
                     * private is false
                     * return type is Function
                 * 6.0.0
                     * private is true
                     * return type is void
             * getId
                 * 2.4.1
                     * private is false
                     * return type is String
                 * 6.0.0
                     * private is true
                     * return type is void
             * getScope
                 * 2.4.1
                     * private is false
                     * return type is Object
                 * 6.0.0
                     * private is true
                     * return type is void
     * Removed
         * method
             * setScope
 * Ext.util.Format

     * Added
         * method
             * attributes
             * capitalize
             * currency
             * dateRenderer
             * defaultValue
             * fileSize
             * hex
             * lowercase
             * math
             * nl2br
             * number
             * numberRenderer
             * or
             * parseBox
             * percent
             * pick
             * plural
             * round
             * stripScripts
             * stripTags
             * substr
             * uncapitalize
             * undef
             * uppercase
             * usMoney
         * property
             * currencyAtEnd
             * currencyPrecision
             * currencySign
             * decimalSeparator
             * percentSign
             * thousandSeparator
     * Removed
         * property
             * potentialUndefinedKeys
 * Ext.util.Grouper

     * Modified
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.util.Sorter
                 * 6.0.0
                     * return type is Ext.util.Grouper
             * getGroupString
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.util.HashMap

     * Added
         * method
             * getKeyFn
             * removeAtKey
             * setKeyFn
     * Modified
         * method
             * getKey
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.util.MixedCollection

     * Added
         * method
             * findInsertionIndex
     * Modified
         * config
             * allowFunctions
                 * 2.4.1
                     * default value is false
                 * 6.0.0
                     * default value is null
         * method
             * constructor
                 * 2.4.1
                     * return type is Ext.util.AbstractMixedCollection
                 * 6.0.0
                     * return type is Ext.util.MixedCollection
     * Removed
         * event
             * sort
 * Ext.util.Point

     * 2.4.1
         * superclass is Ext.Base
     * 6.0.0
         * superclass is Ext.util.Region
     * Added
         * method
             * isContainedBy
     * Modified
         * method
             * translate
                 * 2.4.1
                     * return type is Boolean
                 * 6.0.0
                     * return type is Ext.util.Region
 * Ext.util.Region

     * Added
         * method
             * copyFrom
     * Modified
         * method
             * getOutOfBoundOffset
                 * 2.4.1
                     * return type is Ext.util.Region
                 * 6.0.0
                     * return type is Ext.util.Offset
             * toString
                 * 2.4.1
                     * private is false
                 * 6.0.0
                     * private is true
 * Ext.util.Sortable

     * 2.4.1
         * superclass is Ext.mixin.Mixin
     * 6.0.0
         * superclass is Ext.Base
     * Added
         * config
             * defaultSortDirection
             * multiSortLimit
             * sortRoot
             * sorters
         * event
             * beforesort
         * method
             * createComparator
             * generateComparator
             * getFirstSorter
             * getSorterCount
             * setSorters
     * Modified
         * method
             * getSorters
                 * 2.4.1
                     * private is true
                     * return type is void
                 * 6.0.0
                     * private is false
                     * return type is Ext.util.Sorter[]/Object[]
     * Removed
         * method
             * initSortable
         * property
             * defaultSortDirection
             * sortRoot
             * sorters
 * Ext.util.Sorter

     * Added
         * method
             * createComparator
             * getState
             * serialize
     * Modified
         * method
             * getId
                 * 2.4.1
                     * private is false
                     * return type is Mixed
                 * 6.0.0
                     * private is true
                     * return type is void
 * Ext.util.TapRepeater

     * Modified
         * method
             * destroy
                 * 2.4.1
                     * private is true
                 * 6.0.0
                     * private is false
 * Ext.util.Wrapper

     * 2.4.1
         * mixins is [Ext.mixin.Bindable]
     * 6.0.0
         * mixins is [Ext.mixin.Hookable]
 * Global_CSS

     * Added
         * cssVar
             * $background-color
             * $base-background-gradient
             * $base-dark-color
             * $base-highlight-color
             * $base-light-color
             * $color
             * $dark-background-color
             * $dark-theme
             * $enable-big
             * $font-size
             * $font-size-small
             * $font-weight-bold
             * $font-weight-normal
             * $highlight-color
             * $include-html-style
             * $light-background-color
             * $light-color
             * $line-height
             * $neutral-dark-color
             * $neutral-highlight-color
             * $neutral-light-color
             * $neutral-medium-dark-color
         * method
     * Modified
         * cssVar
             * $active-color
                 * 2.4.1
                     * default value is darken ( saturate ( $base-color , 55% ) , 10% )
                 * 6.0.0
                     * default value is null
             * $base-color
                 * 2.4.1
                     * default value is #1985D0
                 * 6.0.0
                     * default value is rgba ( 145 , 0 , 145 , 1 )
             * $font-family
                 * 2.4.1
                     * default value is "Helvetica Neue" , HelveticaNeue , "Helvetica-Neue" , Helvetica , "BBAlpha Sans" , sans-serif
                 * 6.0.0
                     * default value is helvetica , arial , sans-serif
             * $page-bg-color
                 * 2.4.1
                     * default value is #eee
                 * 6.0.0
                     * default value is null
     * Removed
         * cssMixin
             * ellipsis
             * icon
             * insertion
             * mask-by-background
             * toolbar-button
         * cssVar
             * $base-gradient
             * $include-default-icons
             * $include-pictos-font
             * $toolbar-spacing
 * global

     * Added
         * config
             * defaultPhonePickerConfig
             * defaultTabletPickerConfig
             * falseText
             * format
             * trueText
             * undefinedText
             * usePicker
         * cssVar
             * $base-color
             * $css-shadow-border-radius
             * $enable-font-smoothing
             * $font-size
             * $grid-cell-background-color
             * $grid-cell-border-color
             * $grid-cell-color
             * $grid-cell-font-family
             * $grid-cell-font-size
             * $grid-cell-font-size-big
             * $grid-cell-font-weight
             * $grid-cell-line-height
             * $grid-cell-line-height-big
             * $grid-cell-padding
             * $grid-cell-padding-big
             * $grid-cell-pressed-background-color
             * $grid-cell-selected-background-color
             * $grid-column-background-color
             * $grid-column-border-color
             * $grid-column-color
             * $grid-column-font-family
             * $grid-column-font-size
             * $grid-column-font-size-big
             * $grid-column-font-weight
             * $grid-column-line-height
             * $grid-column-line-height-big
             * $grid-column-padding
             * $grid-column-padding-big
             * $grid-column-sort-asc-icon
             * $grid-column-sort-desc-icon
             * $grid-column-sort-icon-color
             * $grid-column-sort-icon-font-size
             * $grid-column-sort-icon-spacing
             * $grid-column-sorted-background-color
             * $grid-group-header-background-color
             * $grid-group-header-border-color
             * $grid-group-header-color
             * $grid-group-header-font-family
             * $grid-group-header-font-size
             * $grid-group-header-font-size-big
             * $grid-group-header-font-weight
             * $grid-group-header-line-height
             * $grid-group-header-line-height-big
             * $grid-group-header-padding
             * $grid-group-header-padding-big
             * $grid-summary-row-cell-background-color
             * $grid-summary-row-cell-border-color
             * $grid-summary-row-cell-color
             * $grid-summary-row-cell-font-family
             * $grid-summary-row-cell-font-size
             * $grid-summary-row-cell-font-size-big
             * $grid-summary-row-cell-font-weight
             * $grid-summary-row-cell-line-height
             * $grid-summary-row-cell-line-height-big
             * $grid-summary-row-cell-padding
             * $grid-summary-row-cell-padding-big
             * $image-extension
             * $image-search-path
             * $include-not-found-images
             * $loading-spinner-color
             * $relative-image-path-for-uis
             * $theme-resource-path
             * $toolbar-input-bg
             * $toolbar-input-border-color
             * $toolbar-input-color
             * $toolbar-input-height
     * Removed
         * config
             * autoLoad
             * autoSync
             * store
             * storeName
         * method
             * generate
             * set
         * property
             * defaultUrl
             * heightParam
             * supportedTypes
             * svgParam
             * typeParam
             * widthParam

## Removed
 * Ext.DateExtras
 * Ext.data.association.Association
 * Ext.data.association.BelongsTo
 * Ext.data.association.HasMany
 * Ext.data.association.HasOne
 * Ext.data.identifier.Simple
 * Ext.data.plugin.Buffered
 * Ext.data.proxy.Sql
 * Ext.device.Accelerometer
 * Ext.device.Browser
 * Ext.device.Camera
 * Ext.device.Capture
 * Ext.device.Compass
 * Ext.device.Connection
 * Ext.device.Contacts
 * Ext.device.Device
 * Ext.device.FileSystem
 * Ext.device.Geolocation
 * Ext.device.Globalization
 * Ext.device.Media
 * Ext.device.Notification
 * Ext.device.Orientation
 * Ext.device.Purchases
 * Ext.device.Purchases.Product
 * Ext.device.Push
 * Ext.device.SQLite
 * Ext.device.Splashscreen
 * Ext.device.filesystem.Cordova
 * Ext.device.filesystem.DirectoryEntry
 * Ext.device.filesystem.Entry
 * Ext.device.filesystem.FileEntry
 * Ext.device.filesystem.FileSystem
 * Ext.device.purchases.Purchase
 * Ext.device.sqlite.Database
 * Ext.device.sqlite.SQLResultSet
 * Ext.device.sqlite.SQLResultSetRowList
 * Ext.device.sqlite.SQLTransaction
 * Ext.device.tunnel.Abstract
 * Ext.direct.AmfRemotingProvider
 * Ext.draw.Component
 * Ext.scroll.View
 * Ext.ux.ActionOverFlowMenuButton
 * Ext.ux.ApplicationMenu
 * Ext.ux.ContextMenu
 * Ext.ux.TabMenuButton
 * Ext.ux.device.Analytics
 * Ext.ux.device.Twitter