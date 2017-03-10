# table-jqueryplugins
This is a jQuery plugins!
##js
``` javascript
(function ($) {
    $.fn.table = function (options) {
        var defaults = {
            //各种参数,各种属性
            oddRow:'oddRow',   //奇数行的样式
            evenRow:'evenRow',  //偶数行的样式
            currentRow:'currentRow', //当前的样式
            mouseType:'mouseover',   //当前鼠标触发的类型
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
            return this;     
        })
    }
})(jQuery)
```
# getNowFormatDate 获取当前的日期时间 格式“yyyy-MM-dd HH:MM:SS”
``` javascript
function getNowFormatDate() {
    var date = new Date();
    var seperator1 = "-";
    var seperator2 = ":";
    var month = date.getMonth() + 1;
    var strDate = date.getDate();
    if (month >= 1 && month <= 9) {
        month = "0" + month;
    }
    if (strDate >= 0 && strDate <= 9) {
        strDate = "0" + strDate;
    }
    var currentdate = date.getFullYear() + seperator1 + month + seperator1 + strDate
            + " " + date.getHours() + seperator2 + date.getMinutes()
            + seperator2 + date.getSeconds();
    return currentdate;
}
```
