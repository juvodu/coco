<p align="center">
  <a href="https://www.npmjs.com/package/3m5-coco">
    <img height="192" width="192" src="https://www.3m5.de/fileadmin/coco/COCO.png">
  </a>
</p>

# 3m5-coco
**a simple JavaScript MVC Framework**
**developed by <a href="http://www.3m5.de" target="3m5">3m5. Media GmbH</a>**

## What is 3m5-coco?

+ based on dejavu class model

+ use handlebars template engine

+ use jQuery for DOM-manipulation

+ use ES6 standard - transpiled by babel --> ES5 standard published to npm

+ compatible to browserify and webpack

## installation

this framework is a <a href="https://www.npmjs.com/package/3m5-coco" target="npm">npm module</a>, use

```js
npm install 3m5-coco
```

## Sample `application.js`

This file will give you a taste of how to use Coco.JS

```js
/**
 * @author (c) Andreas Wiedenfeld <andreas.wiedenfeld@3m5.de>
 * updated at 16.09.2015
 */
/** @namespace **/

var Coco = require("3m5-coco");

var TestCollection = require("./test/testCollection");
var TestView2 = require("./test/testView2");

var CocoApplication = dejavu.Class.declare({

    initialize() {
        console.log("CocoTestApp initialized, look at available Coco-Classes: ", Coco);

        var innerModel = new Coco.Model({id:123, label:"innerModel", properts: "myInnerProperty"});
        var innerCollection = new TestCollection([{id:1, label:11}, {id:2, label:22}]);
        var testModel = new Coco.Model({id:12, label:"myLabel", property: innerModel, properties: innerCollection});

        console.log(testModel);
        console.log(testModel.getAttributes());

        //initialize a simple router
        new Coco.Router('.routerView', {
            dashboard: {
                path: '/',
                view: require("./test/testView"),
                model: testModel
            },
            imprint: {
                path: '/testView2',
                view: TestView2
            }
        }, '/');
    }

});

$(document).ready(() => {
    new CocoApplication();
});

Coco.config = {
    baseUrl: "baseURL",              //server context path
    router: {
        loaderDelay: 300        // When views are swapped by Router, this time adjusts when the loading class
    },
    restService: {              //restService configuration
        path: null,             //restService path
        cacheGet: 600,          //cache time for GET Requests of same url in seconds
        cachePost: null         //cache time for GET Requests of same url in seconds
    }
};
```

## Documentation
<p align="center">
    <a href="https://www.3m5.de/fileadmin/coco/" target="doc">https://www.3m5.de/coco/</a>
</p>

## License

Coco is under <a href="http://opensource.org/licenses/ISC" target="ISC">ISC-License</a>

[npm-url]: https://www.npmjs.com/package/3m5-coco