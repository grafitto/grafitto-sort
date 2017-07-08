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
    var complexObj = [
      {
        name: {
          first: "Kevin",
          second: "Nderitu"
        },
        home: "Thika"
      },
      {
        name: {
          first: "Miss",
          second: "Mtu"
        },
        home: "Orara"
      },
      {
        name: {
          first: "Clemento",
          second: "Alexandra"
        },
        home: "Kilimall"
      }
    ];
    var items = [
                    {
                    "code": "+7 840",
                    "name": "Abkhazia"
                    },
                    {
                    "code": "+93",
                    "name": "Afghanistan"
                    },
                    {
                    "code": "+355",
                    "name": "Albania"
                    },
                    {
                    "code": "+213",
                    "name": "Algeria"
                    },
                    {
                    "code": "+1 684",
                    "name": "American Samoa"
                    },
                    {
                    "code": "+376",
                    "name": "Andorra"
                    },
                    {
                    "code": "+244",
                    "name": "Angola"
                    },
                    {
                    "code": "+1 264",
                    "name": "Anguilla"
                    },
                    {
                    "code": "+1 268",
                    "name": "Antigua and Barbuda"
                    },
                    {
                    "code": "+54",
                    "name": "Argentina"
                    },
                    {
                    "code": "+374",
                    "name": "Armenia"
                    },
                    {
                    "code": "+297",
                    "name": "Aruba"
                    },
                    {
                    "code": "+247",
                    "name": "Ascension"
                    },
                    {
                    "code": "+61",
                    "name": "Australia"
                    },
                    {
                    "code": "+672",
                    "name": "Australian External Territories"
                    },
                    {
                    "code": "+43",
                    "name": "Austria"
                    },
                    {
                    "code": "+994",
                    "name": "Azerbaijan"
                    },
                    {
                    "code": "+1 242",
                    "name": "Bahamas"
                    },
                    {
                    "code": "+973",
                    "name": "Bahrain"
                    },
                    {
                    "code": "+1 246",
                    "name": "Barbados"
                    },
                    {
                    "code": "+1 268",
                    "name": "Barbuda"
                    },
                    {
                    "code": "+375",
                    "name": "Belarus"
                    },
                    {
                    "code": "+236",
                    "name": "Central African Republic"
                    },
                    {
                    "code": "+235",
                    "name": "Chad"
                    },
                    {
                    "code": "+56",
                    "name": "Chile"
                    },
                    {
                    "code": "+86",
                    "name": "China"
                    },
                    {
                    "code": "+61",
                    "name": "Christmas Island"
                    },
                    {
                    "code": "+61",
                    "name": "Cocos-Keeling Islands"
                    },
                    {
                    "code": "+57",
                    "name": "Colombia"
                    },
                    {
                    "code": "+269",
                    "name": "Comoros"
                    },
                    {
                    "code": "+242",
                    "name": "Congo"
                    },
                    {
                    "code": "+372",
                    "name": "Estonia"
                    },
                    {
                    "code": "+251",
                    "name": "Ethiopia"
                    },
                    {
                    "code": "+500",
                    "name": "Falkland Islands"
                    },
                    {
                    "code": "+298",
                    "name": "Faroe Islands"
                    },
                    {
                    "code": "+679",
                    "name": "Fiji"
                    },
                    {
                    "code": "+358",
                    "name": "Finland"
                    },
                    {
                    "code": "+33",
                    "name": "France"
                    },
                    {
                    "code": "+596",
                    "name": "French Antilles"
                    },
                    {
                    "code": "+594",
                    "name": "French Guiana"
                    },
                    {
                    "code": "+689",
                    "name": "French Polynesia"
                    },
                    {
                    "code": "+241",
                    "name": "Gabon"
                    },
                    {
                    "code": "+63",
                    "name": "Philippines"
                    },
                    {
                    "code": "+48",
                    "name": "Poland"
                    },
                    {
                    "code": "+351",
                    "name": "Portugal"
                    },
                    {
                    "code": "+1 787",
                    "name": "Puerto Rico"
                    },
                    {
                    "code": "+974",
                    "name": "Qatar"
                    },
                    {
                    "code": "+262",
                    "name": "Reunion"
                    },
                    {
                    "code": "+381",
                    "name": "Serbia"
                    },
                    {
                    "code": "+248",
                    "name": "Seychelles"
                    },
                    {
                    "code": "+232",
                    "name": "Sierra Leone"
                    },
                    {
                    "code": "+65",
                    "name": "Singapore"
                    },
                    {
                    "code": "+421",
                    "name": "Slovakia"
                    },
                    {
                    "code": "+386",
                    "name": "Slovenia"
                    },
                    {
                    "code": "+677",
                    "name": "Solomon Islands"
                    },
                    {
                    "code": "+27",
                    "name": "South Africa"
                    },
                    {
                    "code": "+500",
                    "name": "South Georgia and the South Sandwich Islands"
                    },
                    {
                    "code": "+82",
                    "name": "South Korea"
                    },
                    {
                    "code": "+34",
                    "name": "Spain"
                    },
                    {
                    "code": "+94",
                    "name": "Sri Lanka"
                    },
                    {
                    "code": "+249",
                    "name": "Sudan"
                    },
                    {
                    "code": "+597",
                    "name": "Suriname"
                    },
                    {
                    "code": "+268",
                    "name": "Swaziland"
                    },
                    {
                    "code": "+46",
                    "name": "Sweden"
                    },
                    {
                    "code": "+41",
                    "name": "Switzerland"
                    },
                    {
                    "code": "+963",
                    "name": "Syria"
                    },
                    {
                    "code": "+886",
                    "name": "Taiwan"
                    },
                    {
                    "code": "+992",
                    "name": "Tajikistan"
                    },
                    {
                    "code": "+255",
                    "name": "Tanzania"
                    },
                    {
                    "code": "+66",
                    "name": "Thailand"
                    },
                    {
                    "code": "+670",
                    "name": "Timor Leste"
                    },
                    {
                    "code": "+228",
                    "name": "Togo"
                    },
                    {
                    "code": "+690",
                    "name": "Tokelau"
                    },
                    {
                    "code": "+676",
                    "name": "Tonga"
                    },
                    {
                    "code": "+1 868",
                    "name": "Trinidad and Tobago"
                    },
                    {
                    "code": "+216",
                    "name": "Tunisia"
                    },
                    {
                    "code": "+90",
                    "name": "Turkey"
                    },
                    {
                    "code": "+993",
                    "name": "Turkmenistan"
                    },
                    {
                    "code": "+1 649",
                    "name": "Turks and Caicos Islands"
                    },
                    {
                    "code": "+688",
                    "name": "Tuvalu"
                    },
                    {
                    "code": "+1 340",
                    "name": "U.S. Virgin Islands"
                    },
                    {
                    "code": "+256",
                    "name": "Uganda"
                    },
                    {
                    "code": "+380",
                    "name": "Ukraine"
                    },
                    {
                    "code": "+971",
                    "name": "United Arab Emirates"
                    },
                    {
                    "code": "+44",
                    "name": "United Kingdom"
                    },
                    {
                    "code": "+1",
                    "name": "United States"
                    },
                    {
                    "code": "+598",
                    "name": "Uruguay"
                    },
                    {
                    "code": "+998",
                    "name": "Uzbekistan"
                    },
                    {
                    "code": "+678",
                    "name": "Vanuatu"
                    },
                    {
                    "code": "+58",
                    "name": "Venezuela"
                    },
                    {
                    "code": "+84",
                    "name": "Vietnam"
                    },
                    {
                    "code": "+1 808",
                    "name": "Wake Island"
                    },
                    {
                    "code": "+681",
                    "name": "Wallis and Futuna"
                    },
                    {
                    "code": "+967",
                    "name": "Yemen"
                    },
                    {
                    "code": "+260",
                    "name": "Zambia"
                    },
                    {
                    "code": "+255",
                    "name": "Zanzibar"
                    },
                    {
                    "code": "+263",
                    "name": "Zimbabwe"
                    }
                ];
    
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