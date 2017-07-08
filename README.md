[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg?style=flat-square)](https://www.webcomponents.org/element/grafitto/grafitto-sort)
[![Published on github pages](https://img.shields.io/badge/github.io-demo-blue.svg?style=flat-square)](https://grafitto.github.io/grafitto-filter/components/grafitto-sort/)

# grafitto-sort

A polymer compatible reusable web element providing a solution for sorting a list of items before displaying them. This component also supports use of custom sort functions using the `f` property. 

Install:   
```bash
bower install --save grafitto/grafitto-sort
```

View the API and Demo [Here](https://grafitto.github.io/grafitto-filter/components/grafitto-sort)
<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="grafitto-sort.html">
    <link rel="import" href="../iron-list/iron-list.html">
    <link rel="import" href="../paper-input/paper-input.html">
    <link rel="import" href="../paper-checkbox/paper-checkbox.html">
    <link rel="import" href="../paper-item/paper-item.html">
    <style>
    	#like{
     	  padding: 5px; 
          width: 95%;
          border:none;
          border-bottom: 1px solid #555;
      	}
        paper-checkbox.styled {
          width: 92%;
          align-self: center;
          border: 1px solid #ddd;
          padding: 8px 16px;
          --paper-checkbox-checked-color: #0f0;
          --paper-checkbox-checked-ink-color: #0f0;
          --paper-checkbox-unchecked-color: white;
          --paper-checkbox-unchecked-ink-color: black;
          --paper-checkbox-label-color: black;
          --paper-checkbox-label-spacing: 0;
          --paper-checkbox-margin: 8px 16px 8px 0;
          --paper-checkbox-vertical-align: top;
        }

        paper-checkbox .subtitle {
          display: block;
          font-size: 0.8em;
          margin-top: 2px;
          max-width: 150px;
        }
        .small{
          font-size: 0.7em;
          color: darkgrey;
        }
        .wrapper{
          width: 33%;
          margin-left: 33%;
        }
        @media only screen and (max-width: 768px) {
            .wrapper{
                width: 100%;
                margin: 0px;
                padding: 5px;
            }
            #like{
              width: 99%
            }
        }
    </style>
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<div class="wrapper">
      <h3>grafitto-sort DEMO</h3>
        <paper-checkbox class="styled" id="i" raised>
          Case
          <span class="subtitle">
            Enable case sensitivity
          </span>
        </paper-checkbox>
        <paper-checkbox class="styled" id="order" raised>
          Order
          <span class="subtitle">
            Enable descending order
          </span>
        </paper-checkbox>
        <grafitto-sort by="name" as="vitu">
          <template>
            <iron-list items=[[vitu]] as="item">
              <template>
                <paper-item>
                  <paper-item-body two-line>
                    <div>{{item.name}}</div>
                    <div class="small" secondary>{{item.code}}</div>
                  </paper-item-body>
                </paper-item>
              </template>
            </iron-list>
          </template>
        </grafitto-sort>
    </div>
  </body>
  <script>
    var f = document.querySelector("grafitto-sort");
    f.items = ["one", "two", "three", "four", "five", "six", "seven"];

    //Set case sensitivity event handler
    document.getElementById("i").addEventListener("checked-changed", function(e){
      console.log("Setting case sensitivity to: ", e.detail.value?"True":"False");
      f.caseSensitive = e.detail.value;
    })
    document.getElementById("order").addEventListener("checked-changed", function(e){
      console.log("Setting descending to: ", e.detail.value?"True":"False");
      f.desc = e.detail.value;
    })
    //Listen for value changed
    //document.getElementById("like").addEventListener("value-changed", function(from, to){
    //  f.like = from.detail.value;
    //});
  </script>
```
`array`:
```javascript
var array = ["one", "two", "three", "four", "five", "six", "seven"];
```
```html
<grafitto-sort item=[[array]] as="vitu">
  <template>
    <iron-list items=[[vitu]] as="item">
      <template>
        <div>{{item}}</div>
      </template>
    </iron-list>
  </template> 
</grafitto-sort>
```
Items will be sorted to this order: `"five","four","one","seven","six","three", "two"`
When a simple array is provided, a simple sort is done.

### Arrays of Objects   
`data`:
```javascript
var data = [
  {
    name:"John",
    home: "Thika"
  },
  {
    name: "Doe",
    home: "Nairobi"
  }
]
```
Example:
```html
<grafitto-sort items=[[data]] by="name" as="vitu">
  <template>
    <iron-list items=[[vitu]] as="item">
      <template>
        <div>{{item.name}} - {{grafitto.home}}</div>
      </template>
    </iron-list>
  </template>
</grafitto-sort>
```
Just incase you are wondering, `vitu` means `items` in Swahili :-)

Items are sorted using the `by` attribute

`grafitto-sort` also supports complex objects. consider:


```javascript
var complexObj = [
  {
    name: {
      first: "Thomas",
      second: "Kimtu"
    },
    home: "Thika"
  },
  {
    name: {
      first: "John",
      second: "Doe"
    },
    home: "Othaya"
  },
  {
    name: {
      first: "Clement",
      second: "Wainaina"
    },
    home: "Nakuru"
  }
]
``` 
Here is an example using the `complexObj` object above

```html
<grafitto-sort items=[[complexObj]] by="name.first" as="vitu">
  <template>
    <iron-list items=[[vitu]] as="item">
      <template>
        <div>{{item.name.first}} {{item.name.second}}, {{item.home}}</div>
      </template>
    </iron-list>
  </template>
</grafitto-sort>
```

You can also use your custom function to sort the items provided.
The function receives a two instances of the items provided and should return a `boolean` 

```html
<dom-module id="your-element">
  <template>
    <grafitto-sort items=[[data]] id="filter" as="vitu">
      <template>
        <iron-list items=[[vitu]] as="item">
          <template>
            <div>{{item.name}}, {{item.home}}</div>
          </template>
        </iron-list>
      </template>
    </grafitto-sort>
    <script>
      Polymer({
        is: "your-element",
        properties: {
          data: {
            type: Array,
            value: [
                    {
                      "name":"John",
                      "home": "Thika"
                    },
                    {
                      "name": "Doe",
                      "home": "Nairobi"
                    }
                  ]
          }
        },
        ready: function(){
          this.$.filter.f = function(first, second){
            return first.localCompare(second);
          };
          //treat f as if it will be used as a parameter in sort() function, 
          //because it will :-)
        }
       //Then you can call sort() function to trigger sort
      })
    </script>
  </template>
</dom-module>
```