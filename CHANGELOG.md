# Coco changelog

## 0.1.71

- Coco.Collection: sortByProperty() - Bugfix added missing import

## 0.1.70

- Coco.Collection: findBy, findOneBy, removeBy are no more type safe anymore
- added older browser support for Symbol-Event-handles

## 0.1.69

- added function removeBy to Coco.Collection
- added $compute functionality to all functions to implement computed properties for models, you can check a computed function by boolean '.isComputed' property

## 0.1.68

- fixed bug in Coco.Collection
- added babel/polyfill requirement for IE support
- enable application-loading again
- fixed bug in Coco.EventDispatcher to removeEvents by given Symbol-handle
- Rewrite modern console methods for old browsers (like IE 9/10)
- enable working with promises - Coco.BaseRestService now returns Promise object
- pass contentType as parameter for POST and PUT
- reactivate removal of application-loading class from main container

## 0.1.67

- added Coco.config.locale (default is 'de') for handlebars localization
- handlebars templates now get localization from Coco.config for other modules e.g. formatJS
- moved handlebars & underscore from dependencies to devDependencies to prevent double includes

## 0.1.66

- HOTFIX HandleBars-Helper, dont use ES6 syntax!

## 0.1.65

- Hotfix

## 0.1.64

- fixed bug to prevent executing model properties with type function during rendering
- added Coco.Utils.sizeOfObject function to count object properties
- added Coco.Collection.where function, based on underscore.where to get filtered array of models

## 0.1.63

- added Handlebars.Helper 'ifCond' - deprecates: 'is', 'isNot', 'isGreater', 'isGreaterThan', 'isLess', 'isLessThan'
- hotfix

## 0.1.6

- fixed require bugs for all Coco.Events

## 0.1.5

- added some error message for missing injected service
- moved CHANGE_ROUTE Event-Type from Coco.Event to Coco.RouterEvent
- moved FIRE_ROUTE Event-Type from Coco.Event to Coco.RouterEvent
- moved SHOW_VIEW Event-Type from Coco.Event to Coco.RouterEvent
- moved HIDE_VIEW Event-Type from Coco.Event to Coco.RouterEvent
- added oldRoute object to Coco.RouterEvent
- removed Coco.HashMap from library, use ES6 classes instead

## 0.1.4

- correct Reference to Coco.URLHelper class
- replaced Coco.HashMap by ECMA6 Map in RestBaseService
- removed Coco.EventDispatcher inheritance on Coco.Event

## 0.1.3

- Bugfix: fixed illegal usage of Coco.Classes in BaseRestService
- Added: Coco.URLHelper class

## 0.1.2

- Bugfix: fixed 'this'-bug in Coco.RouterService
- Bugfix: fixed logical bug in Coco.Model/ Coco.Collection (removed illegal call of no more existing functions)
- Update: Coco.Collection destroys now all model EventHandler after removing model
- Update: Coco.Model, Collection, View & ChildView now remove all their EventListener when .destroy() is called

## 0.1.1

- Bugfix: fixed logical bug in Coco.View (removed illegal call of no more existing functions)

## 0.1.0

- Change: use Coco.EventDispatcher instead of Coco.Event for Event-Handling
- Deprecated: Coco.Event.listenTo
- Deprecated: Coco.Event.trigger

## 0.0.981

- Change: trigger RENDER-Events & _onFirstRender in Coco.View delayed to get the DOM really rendered
- Change: replaced __tpl by _template in Coco.View

## 0.0.980

- Bugfix: fixed illegal call of service injection in Coco.ChildView
- Change: Coco.View now checks only for instanceof Coco.View before adding ChildView...Coco.ChildView is not available in Coco.View (circle dependency)

## 0.0.979

- Bugfix: added missing Coco.Event dependency in Coco.Model

## 0.0.978

- add Plugin i18n: Coco.Translator

## 0.0.977

- 1st stable/tested version with simple MVC function

