### How to enable Vuejs Dev Tools in Android/iOS 📱 mobile phone.

following this code:

```js
javascript:(function () {
    var script = document.createElement("script");
    var vue = document.createElement("script");
    script.src = "https://cdn.jsdelivr.net/npm/eruda";
    vue.src = "https://cdn.jsdelivr.net/npm/eruda-vue@1.1.1/eruda-vue.js";
    document.body.append(script);
    document.body.append(vue);
    script.onload = function () {
        eruda.init();
    };
    vue.onload = function () {
        // eruda.init();
        eruda.add(erudaVue);
    };
})();
```
