# [Calculator (beta)](https://relaxed-kangaroo-e4f3b3.netlify.app/) 

# Objective : Understanding VueJS

## Description
- A very basic [calculator](https://relaxed-kangaroo-e4f3b3.netlify.app/) project, based on Android phone calculator
- Coded in VueJS, Vanilla JavaScript, and some TailwindCSS
- page hot-reload by Vite (on Chrome + inspect)
- Practice of using math.js [mathjs](https://mathjs.org/) library (eval() can be used too)
- Data manipulation through [Map](https://www.w3schools.com/js/js_object_maps.asp) objects
- Removal of polarity toggle and % to reduce algorithm complexity for structuring strings

#### My VueJS study
- use of import / export across Vue files
- the subtle differences between <script setup> and <script>
- the subtle differences between <style scoped> and <style>
- the reactivity feature that allows data access without query selectors
- using the built-in darkmode theme (CSS)
- use of slot and @click listeners
```
    <button @click="calcProcessor">
      <slot name="key"></slot>
    </button>
```
```
    \\ initiating vue project
    npm init vue@latest
    cd "calc"
    npm install
    npm run dev
```

```
    npm run build  // go for production
```

#### General studies
- scaling SVG file properly and respecting its svg containers  (not using <img> tag)
- Map objects vs. normal Objects
- import of an extension library


#### Code Components : Result retrieval from mathjs
```
    npm init
    npm install mathjs
```
```
    import { simplify, parse, evaluate } from "mathjs"
```
```
    evaluate(simplify(parse(rawString)).toString())  //get result in integer instead of fraction
```
#### Code Components : Object build through function call on every button clicked (keypad)
```
  export function buildObj(char, userString) {
    this.char = char
    this.userString = userString
    this.lcdmain_display = stringFormatterForDisplay(this.userString)
    this.lcdpreview_display = getResult(this.userString, this.char)
    this.isOperator = isOperator(this.char)
    this.isEqual =  this.char =="="?true:false
    this.isClear = this.char=="C"?true:false
    this.isDel = this.char=="D"?true:false
    this.isDecimal = this.char=="."?true:false
  }
```

#### Code component : Mapping objects
```
    let clicked = new buildObj(x, lcdmaintemp.value)
    let current = new Map(Object.entries(clicked))
```


