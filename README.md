cytoscape-css-renderer
================================================================================


## Description

Cytoscape renderer that uses CSS transforms to provide label formatting.


## Dependencies

 * Cytoscape.js >=2.3.5


## Usage instructions

Download the library:
 * via npm: `npm install cytoscape-css-renderer`,
 * via bower: `bower install cytoscape-css-renderer`, or
 * via direct download in the repository (probably from a tag).

`require()` the library as appropriate for your project:

CommonJS:
```js
var cytoscape = require('cytoscape');
var css_renderer = require('cytoscape-css-renderer');

css_renderer( cytoscape ); // register extension
```

AMD:
```js
require(['cytoscape', 'cytoscape-css-renderer'], function( cytoscape, css_renderer ){
  css_renderer( cytoscape ); // register extension
});
```

Plain HTML/JS has the extension registered for you automatically, because no `require()` is needed.


## API

Require the library and specify 'css' as renderer.name.

```js
  $(function(){
    var cy = window.cy = cytoscape({
      container: document.getElementById('cy'),
      renderer: {
        name: "css"
      },
      ready: function(){
      },
      style: [
        {
          selector: 'node',
          css: {
            'content': 'data(name)',
            "font-size":"10px",
          }
        },
        {
          selector: 'edge',
          css: {
            'target-arrow-shape': 'triangle'
          }
        }
      ],
      elements: {
        nodes: [
          { data: { id: 'j', name: '<b>Jerry</b><br />Seinfeld' } },
          { data: { id: 'e', name: 'Elaine' } },
          { data: { id: 'k', name: 'Kramer' } },
          { data: { id: 'g', name: 'George' } }
        ],
        edges: [
          { data: { source: 'j', target: 'e' } },
          { data: { source: 'j', target: 'k' } },
          { data: { source: 'j', target: 'g' } },
          { data: { source: 'e', target: 'j' } },
          { data: { source: 'e', target: 'k' } },
          { data: { source: 'k', target: 'j' } },
          { data: { source: 'k', target: 'e' } },
          { data: { source: 'k', target: 'g' } },
          { data: { source: 'g', target: 'j' } }
        ]
      }
    });
  });

```
