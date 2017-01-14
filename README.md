# table-jqueryplugins
This is a jQuery plugins!
>js
``` javascript
(function ($) {
    $.fn.table = function (options) {
        var defaults = {
            //各种参数,各种属性
            oddRow:'oddRow',   //奇数行的样式
            evenRow:'evenRow',  //偶数行的样式
            currentRow:'currentRow', //当前的样式
            mouseType:'mouseover',
        }
        var options = $.extend(defaults, options);

        this.each(function () {
            //实现功能的代码
            $(this).find('tr:odd').addClass(options.oddRow)     //奇数行变颜色
            $(this).find('tr:even').addClass(options.evenRow)   // 偶数行变颜色

            $(this).find('tr').bind(options.mouseType,function () {    
                $(this).addClass(options.currentRow)
            })
            $(this).find('tr').bind('mouseout',function () {
                $(this).removeClass(options.currentRow)
            })

        })
    }
})(jQuery)
```
