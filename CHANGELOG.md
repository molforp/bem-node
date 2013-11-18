0.7.0
---------------

method ```beforeOut``` now deprecated. I you need make something before rendering you shold make it in ```init``` method.

Лучше всего сделать на проекте страницу, от которой все будут наследоваться

```i-some-page.common.js```
```js
BEM.decl({block: 'i-some-page', baseBlock: 'i-page'});
```

```i-some-page.priv.js```:
```js
BEM.decl('i-some-page', null, {
    init: function () {
        var _this = this;
        return BEM.blocks['some-block'].someCheck().then(function () {
            return _this.out({block: 'some-block'})
        });
    }
});
```
