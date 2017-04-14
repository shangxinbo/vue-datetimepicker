# vue-datetimepicker

> A simple and customize datetimepicker component for vue

> This respository references [vue-datepicker](https://github.com/hilongjw/vue-datepicker),maybe you prefer it.

> __NOTE:__ This component is just for vue 2+.Please Check your vue version first. 

## Demo

This project is a runtime demo.you can get the demo by these clis:
```shell
git clone https://github.com/shangxinbo/vue-datetimepicker.git yourPath
cd yourPath
npm install 
npm run dev   // serve with hot reload at http://localhost:8080 to see the demo 
```

if you want to build production with minification. you can use this:

```shell
npm run build
```

## Use

It's a **single-file components** for vue.You must use it with webpack,babel and vue-loader to run.So I assume that you have node v4+ and npm v3+   

```shell
npm install --save shangxinbo/vue-datetimepicker
```
then in your component,you can use it by this:
```javascript
import dateTimePicker from 'vue-datetimepicker'
export default {
    …
    components:{
        dateTimePicker
    }
    …
}
```

## Docs

#### Props

- __init__

  type: String

  desc: init value for input and datetimepicker.__note that if you set `format`prop, this value must apply to your format__

  e.g. : `'2017-11-23'`

- __colors__

  type: Object

  desc: you can set this value to customize view of picker.This Object contain three available key/value.

  - header    : background-color for header(year and month) 
  - headerText : color for the font in header(year and month)
  - checkedDate : background-color for selected day

  e.g.:

  ```javascript
  {
    header:'#cccccc',
    headerText:'blue',
    checkedDate:'green'
  }
  ```

- __addClass__

  type:String

  desc: the class added to the input element

  e.g.: `'date'`

- __placeholder__

  type:String

  desc: the placeholder for input element

- __weeks__

  type:Array

  desc: the label for the weeks text.

  default:`['Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa', 'Su']`

- __months__

  type:Array

  desc: the label for the months text.

  default:`['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December']`

- __buttons__

  type:Object

  desc: the text for cancel and ok buttons

  - ok: key of ok
  - cancel: key of cancel

  default:`{ok:'OK',cancel:'Cancel'}`

  e.g.: {ok:'sure',cancel:'close'}

- __timepicker__

  type:Boolean

  desc: set true for using timepicker or false for not using 

  default : false

- __format__

  type:String

  desc: the format for the value of input 

  default : `'YYYY-MM-DD'  //TODO`

  e.g.: `'YYYY-MM-DD HH:mm'`

- __sundayFirst__

  type:Boolean

  desc: set true to make sunday to be the first day of week.or false to make monday the first

  default:false

- __min__

  type:String

  desc: set the min value for user to choose.__Note that it must be apply to the `format`__

  e.g.: `'2017-11-23'`

- __max__

  type:String

  desc: set the max value for user to choose.__Note that it must be apply to the `format`

  e.g.: `'2017-12-31'`

- __disabled__

  type:Object

  desc: set the disabled day in (month/week) that can't be checked.

  - type: `'inMonth' or 'inWeek'`
  - arr: the day index array

  e.g.: 

  ```javascript
  {
    type:inMonth
    arr:[1,2,3]  //every 1,2,3 date in month is not available
  }
  {
    type:inWeek
    arr:[1]  //every MonDay in weeks is not available //TODO SUNDAY FIRST
  }
  ```

#### Events

- change(value)

  triggler: when choose the date or time (click ok buttons).when the input value changed

  value : return the picked value that formatted by your format option 