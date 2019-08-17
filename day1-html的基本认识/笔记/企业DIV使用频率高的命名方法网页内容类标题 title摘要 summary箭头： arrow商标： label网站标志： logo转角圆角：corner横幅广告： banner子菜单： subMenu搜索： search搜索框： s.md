- 企业`DIV`使用频率高的命名方法

- **网页内容类**

  - 标题: `title`

    - 摘要: `summary`
    - 箭头： `arrow`
    - 商标： `label`
    - 网站标志： `logo`
    - 转角/圆角：`corner`
    - 横幅广告： `banner`
    - 子菜单： `subMenu`
    - 搜索： `search`
    - 搜索框： `searchBox`
    - 登录： `login`
    - 登录条：`loginbar`
    - 工具条： `toolbar`
    - 下拉： `drop`
    - 标签页： `tab`
    - 当前的： `current`
    - 列表： `list`
    - 滚动： `scroll`
    - 服务： `service`
    - 提示信息： `msg`
    - 热点：`hot`
    - 新闻： `news`
    - 小技巧： `tips`
    - 下载： `download`
    - 栏目标题： `title`
    - 热点： `hot`
    - 加入：`joinus`
    - 注册： `regsiter`
    - 指南： `guide`
    - 友情链接： `friendlink`
    - 状态： `status`
    - 版权： `copyright`
    - 按钮： `btn`
    - 合作伙伴： `partner`
    - 投票： `vote`
    - 左右中：`left` `right` `center`

    ------

  - 注释的写法: `/* Footer */` 内容区`/* End Footer */`

- **id的命名:**

  - 页面结构
    - 容器: `container`
    - 页头：`header`
    - 内容：`content`/`container`
    - 页面主体：`main`
    - 页尾：`footer`
    - 导航：`nav`
    - 侧栏：`sidebar`
    - 栏目：`column`
    - 页面外围控制整体布局宽度：`wrapper`
    - 左右中：`left` `right` `center`

  ------

  - 导航
    - 导航：`nav`
    - 主导航：`mainbav`
    - 子导航：`subnav`
    - 顶导航：`topnav`
    - 边导航：`sidebar`
    - 左导航：`leftsidebar`
    - 右导航：`rightsidebar`
    - 菜单：`menu`
    - 子菜单：`submenu`
    - 标题: `title`
    - 摘要: `summary`

  ------

  - 功能
    - 标志：`logo`
    - 广告：`banner`
    - 登陆：`login`
    - 登录条：`loginbar`
    - 注册：`regsiter`
    - 搜索：`search`
    - 功能区：`shop`
    - 标题：`title`
    - 加入：`joinus`
    - 状态：`status`
    - 按钮：`btn`
    - 滚动：`scroll`
    - 标签页：`tab`
    - 文章列表：`list`
    - 提示信息：`msg`
    - 当前的:`current`
    - 小技巧：`tips`
    - 图标: `icon`
    - 注释：`note`
    - 指南：`guild`
    - 服务：`service`
    - 热点：`hot`
    - 新闻：`news`
    - 下载：`download`
    - 投票：`vote`
    - 合作伙伴：`partner`
    - 友情链接：`link`
    - 版权：`copyright`

  ------

  - **class的命名:**
  - 颜色:使用颜色的名称或者16进制代码,如
    - `.red { color: red; }`
    - `.f60 { color: #f60; }`
    - `.ff8600 { color: #ff8600; }`
  - 字体大小,直接使用"font+字体大小"作为名称,如
    - `.font12px { font-size: 12px; }`
    - `.font9px {font-size: 9pt; }`
  - 对齐样式,使用对齐目标的英文名称,如
    - `.left { float:left; }`
    - `.bottom { float:bottom; }`
  - 标题栏样式,使用"类别+功能"的方式命名,如
    - `.barnews { }`
    - `.barproduct { }

- 清除浮动的几种方法
  - 方法一：`投机取巧法` -- 不推荐
  - 直接一个放到当作最后一个子标签放到父标签那儿，此方法屡试不爽，兼容性强
- 方法二：`overflow + zoom`方法 --不推荐
  `.fix{overflow:hidden; zoom:1;}`
  - 此方法优点在于代码简洁，涵盖所有浏览器
- 方法三：`after + zoom`方法 -推荐--此方法可以说是综合起来最好的方法了
  - `clearfix`只应用在包含浮动子元素的父级元素上

```css
.clearfix{zoom:1;}
.clearfix:after{
     display:block; 
     content:'clear'; 
     clear:both;
     line-height:0; 
     visibility:hidden;
}
```

- 方法四 在方法三的基础上的最优雅的做法【推荐】

```css
.clearfix:after,
.clearfix:before {/*before 是为了防止浏览器顶部空白的崩溃*/   
     content: " ";   
     display: table;
}
.clearfix:after {    
    clear: both;
}
```

清除浮动的原理是触发`BFC`，这里只有`clear:both`起清除浮动作用，其他的`line-height:0; visibility:hidden;`都是为了隐藏生的内容需要的

##### 一些总结

------

- 自动继承属性：
  - `color`
  - `font`
  - `text-align`
  - `list-style`
    ...
- 非继承属性：
  - `background`
  - `border`
  - `position`
    ...
- 具有破坏性的元素：
  - `float`
  - `display:none;`
  - `position:absoblute/fixed/sticky;`
- 具有包裹性的元素：
  - `display:inline-block/table-cell`
  - `position:absolute/fixed/sticky`
  - `overflow:hidden/scroll`
- 消除图片底部间隙的方法
  - 图片块状化-无基线对齐
    `img{display:block;}`
  - 图片底线对齐
    `img{vertical-align:bottom;}`
  - 行高足够小 - 基线位置上移
    `.box{line-height:0;}