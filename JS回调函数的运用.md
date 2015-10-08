##JS回调函数的运用（多页面驱动加载）

@[javascript] @[代码] @[巧妙]

很多时候需要通过ajax获取一些值，当且仅当这些值获取后，才能够执行后面的代码。我们可以利用ajax的success。但是如果有多个页面，都需要这些值来驱动，却不知道哪个页面会被先加载，哪段函数会被先加载。这个时候，我们可以写这样两个函数。

##如果这些值是 globalData

```javascript
    function getInfo（callback） {
    
         if(!globalData) {
              //get globalData 
         }
         callback();
    }

    function refreshInfo(callback) {
        //get globalData 
        callback();
    }

```

使用的时候,在需要的页面调用:

```javascript
    getInfo(function() {
         //执行后面的代码
    })；


```

在需要的时候，refreshInfo即可

