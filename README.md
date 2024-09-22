# play-nodejs

My personal playground for nodejs coding and learning.

## :pushpin: Summary
### Table of contents
---
- [Module System](#label-module-system)

## :label: Module System
### Javascript module system
- CJS(Common JS)
   ```javascript
   // math.js - math module
   function add(a, b) {
     return a + b
   }
   
   function sub(a, b) {
     return a - b
   }
   
   module.exports = {
     add: add,
     sub: sub
   }
   
   // index.js
   {
     const moduleData = require('./math')
   
     console.log(moduleData)
   
     console.log(moduleData.add(1, 2))
     console.log(moduleData.sub(1, 2))
   }
   
   {
     // use destructuring assignment
   
     const { add, sub } = require('./math')
   
     console.log(add(1, 2))
     console.log(sub(1, 2))
   }
   ```
   <br>

- ESM(ES Module)
   - add `"type": "module"` in package.json
   - method 1
      ```javascript
      // math.js - math module
      {
         function add(a, b) {
           return a + b
         }
         
         function sub(a, b) {
           return a - b
         }
         
         function multiply(a, b) {
           return a * b
         }
         
         export { add, sub, multiply }
      }
      
      // index.js
      import { add, sub, multiply } from './math.js'
      
      console.log(add(1, 2))
      console.log(sub(1, 2))
      console.log(multiply(1, 2))
      ```
   <br>

   - method 2
      ```javascript
      // math.js - math module
      {
        // method 2
        export function add(a, b) {
          return a + b
        }
      
        export function sub(a, b) {
          return a - b
        }
      
        export default function multiply(a, b) {
          return a * b
        }
      }
            
      // index.js
      import { add, sub } from './math.js'
      import mul from './math.js'
      
      console.log(add(1, 2))
      console.log(sub(1, 2))
      console.log(mul(1, 2))
      ```
   <br>

