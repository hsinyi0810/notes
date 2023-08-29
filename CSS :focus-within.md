# CSS :focus-within

```html
<fieldset>
    <div class="input grid grid-flow-col auto-cols-fixed-last gap-x-3 items-center rounded-xl border px-4 h-16 focus-within:border-indigo-600 focus-within:shadow-xl border-solid border-1">
      <label class="input-with-title">
        <legend class="truncate hidden">
         姓名
        </legend>
        <input type="text" placeholder="請輸入姓名" class="w-full bg-transparent placeholder-app-tertiary focus:outline-none disabled:text-app-secondary">
      </label>
    </div>
</fieldset>
```

```css
.input-row:focus-within {
  border-color: red;
}
****


```

```js
const inputTitles = document.querySelectorAll('.input-with-title');

if(inputTitles) {
  inputTitles.forEach(ele => {
    let input = ele.querySelector('input');
    let title = ele.querySelector('legend');
    
    input.addEventListener('focus', function() {
      this.classList.add('placeholder-transparent');
      title.classList.remove('hidden');
    })
    input.addEventListener('blur', function(){
      this.classList.remove('placeholder-transparent');
      check(input);
    })
  });
  
  function check(ele) {
    if(ele.value) {
      ele.parentNode.querySelector('legend').classList.remove('hidden');
      ele.parentNode.querySelector('legend').classList.add('block');
    } else {
      ele.parentNode.querySelector('legend').classList.add('hidden');
      ele.parentNode.querySelector('legend').classList.remove('block');
    };
  };
}
```

***
### 區域變數