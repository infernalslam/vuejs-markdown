## Vuejs
### 1 Color palette

#### HTML
```html
<script src="https://npmcdn.com/vue/dist/vue.js"></script>

<div id="app">
<p class="title">Css custom</p>
R : <input type="range" min="100" max="255" v-model="R"> {{ R }} <br>
G : <input type="range" min="100" max="255" v-model="G"> {{ G }} <br>
B : <input type="range" min="100" max="255" V-model="B"> {{ B }} <br>
<div :style="color" class="box-color"></div>
</div>

```
#### JAVASCRIPT
```javascript
new Vue({
    el: '#app',
    data: {
        R: 0,
        G: 0,
        B: 0
    },
    computed: {
    	color: function () {
      	return 'background-color: rgb(' + this.R + ',' + this.G + ',' + this.B + ')'
      }
    }
})
```
#### CSS/STYLE
```css
.title {
  text-align: center;
}

.box-color {
  padding-bottom: 13%;
  padding-left: 19%;
  margin-left: 40%;
  margin-top: -15%;
}
```
## 2 simple counter

#### HTML
```html
<script src="https://npmcdn.com/vue/dist/vue.js"></script>

<div id="app">
<h1 class="title"> {{ number }}</h1>
<div class="plus" @click="add()">+</div>
<div class="sub" @click="sub()" :class="{ 'sub': toggle1, 'dissub': toggle2  }">-</div>
</div>
```

#### JAVASCRIPT
```javascript
new Vue({
    el: '#app',
    data: {
 			number: 1,
      toggle1: true,
      toggle2: false
    },
    methods: {
    	add: function () {
      	this.number += 1
        this.toggle1 = true
        this.toggle2 = false
      },
      sub: function () {
      	if (this.number > 0) this.number -= 1
  			else {
        	// alert('disable')
          this.toggle1 = false
          this.toggle2 = true
        }
      }
    }
})
```
#### CSS
```css
.title {
    font-size: 98px;
    text-align: center;
    color: red;
    font-weight: bold;
}

.plus {
    margin-top: -14%;
    margin-left: 66%;
    font-size: 40px;
    cursor: pointer;
    margin-right: 15%;
}
.sub {
    margin-top: -10%;
    font-size: 40px;
    margin-left: 28%;
    cursor: pointer;
    margin-right: 69%;
}

.dissub {
    margin-top: -10%;
    font-size: 40px;
    margin-left: 28%;
    cursor: no-drop;
    margin-right: 69%;
}
```
## 3 discount calculator
