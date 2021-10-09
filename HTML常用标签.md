# HTML常用标签
## a标签的用法：\<a href="" target="">XXXX\</a>
    1. href的取值：
        1. 网址
            https://google.com
            http://google.com
            //google.com
            建议是用//google.com，因为html会自动判别是用https还是http合适
        2. 路径
            /a/b/c及a/b/b
            index.html及./index.html
        3. 伪协议
            javascript:(代码);
            javascript:;  ————啥都不做
            mailto:邮箱
            tel:手机号
        4. ID
            href=#xxx  ————定位到xxx这个标记的位置处
    2. target的取值：
        _blank  新建标签页
        _self   当前页面
        _top    顶层窗口
        _parent 上层窗口
        "target="xxx""  如果没有叫xxx的窗口，则创建新窗口，窗口名为xxx
                        如果有叫xxx的窗口，则在xxx窗口打开
                        
## img标签的用法：
        alt  代替用文字
        height/width  只写一个都会自动适应大小，但是注意:永远别让图片变形!!!
        src  图片地址
        onload/onerror  监听图片是否加载成功

## table标签的用法：
        tr == table row ————table中的一行
        th 表头
        td 表数据
        记得要有tbody
        thead、tbody、tfoot的使用顺序无关，但是在页面中的显示顺序是固定的
        table-layout:auto 根据内容设置列宽
        table-layout:fixed 尽量平均列宽
        关于table的border：
        border-collapse  合并表格(去隙实力派)
        border-spacing   设置表格单元格之间的间距

## form标签的用法：
        action  目的地，只写action的话默认是请求目的地
        method  对action的方法
        autocomplete  自动填充
        target  把指定的页面变成action中的目的地
        
        form里面input要有name
        form里面要放一个type=submit才能触发submit
        
        input和button的区别
        input type="submit" 不能再添加内容
        button type="submit" 可以添加内容，如：添加一个img
