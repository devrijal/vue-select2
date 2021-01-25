# Vue Select2


# Requirements

- [Vue.js](https://github.com/yyx990803/vue) `^1.0.24`
- [JQuery](https://github.com/jquery/jquery) `^2.2.4`
- [Select2](https://github.com/select2/select2) `^4.0.3`

# Properties
- *options* [`Array`]
	- Option [`Object`] 
	 	- `{id: Number, text: String}`
- *modal-id* [`String`]
	- if the component used within bootstrap modal.


# Usage

```html

<div id="app">
  <div class="row">
      <div class="col-md-12">
          <div class="form-group">
          
              <select2 
              	:options="options" 
                v-model="selected" 
                :modal-id="myModal">
              </select2>
              
          </div>
      </div>
  </div>
</div>
```

```javascript
new Vue({
	el: "#app",
	components: {
		'select2' : httpVueLoader('./select2.vue')
	},
	data: {
	  selected: 2,
	  options: [{ id: 1, text: "Hello" }, { id: 2, text: "World" }]
	}
});
```



