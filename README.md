# fullpage
Some fullpage.js application sites and summary

Fullpage.js是一个基于jQuery的插件，他可以非常方便、很轻松的制作一个全屏网站：
1.支持鼠标滚动
2.多个回调函数
3.支持手机、平板等触摸事件
4.支持CSS3动画
5.支持窗口缩放
6.窗口缩放时自动调整
7.可设置滚动宽度、背景颜色、滚动速度、循环选项、回调、文本对齐方式等

Git.hub上的fullpage主页：
https://github.com/alvarotrigo/fullPage.js

引入fullpage：
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/fullPage.js/2.6.7/jquery.fullPage.css">
        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.0/jquery.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/fullPage.js/2.6.7/vendors/jquery.easings.min.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/fullPage.js/2.6.7/jquery.fullPage.js"></script>

基本的页面结构：

<div id="fullpage">
                <div class="section">something</div>
                <div class="section">something</div>
                <div class="section">something</div>
                <div class="section">something</div>
</div>

激活fullpage效果：
        <script>
                $(document).ready(function(){
                        $('#fullpage').fullpage();
                })
        </script>

Fullpage的配置项：

- 1.sectionsColor:
  可以为每一个section设置background-color属性
['red','green','blue','gray']
- 2.controlArrows：
控制slide幻灯片箭头的显隐，当为flase时箭头隐藏，默认箭头显示
- 3.verticalCentered:
控制每一页的内容是否垂直居中显示，默认为true，一般我们都使用默认值
- 4.resize：
控制字体是否随窗口缩放而缩放，默认为false
- 5.scrollingSpeed:
控制页面滚动速度，默认为700
- 6.anchors：
定义锚链接，默认值为[]，有了锚链接，用户可以迅速定位到某一页面。需要注意的是，锚链接的命名不能与页面中的name和id名重复，尤其是ie浏览器下。而且定义时不需要加#
定位到页面的话，需要在section的div上面加上active的类名
- 7.lockAnchors:
是否锁定锚链接，默认为flase，也就是不锁定锚链接，当设置为true时，定义的锚链接就没有效果了，这个配置项很少使用
- 8.easing:
定义页面section滚动的动画方式，默认为easeInOutCubic,如果修改此项，需要引入jquery.easings的动画插件，或者是jquery.ui
- 9.css3:
是否使用css3 transforms来实现滚动效果，默认为true。这个配置项可以提高支持css3的浏览器或者是移动端的效果和速度，如果浏览器不支持css3，则会使用jquery来替代css3实现滚动效果（优雅降级）。
- 10.loopTop：
滚动到最顶部后是否连续滚动到底部，默认为false
- 11.loopBottom
滚动到最底部后是否连续滚回到最顶部，默认为false
- 12.loopHorizontal  
横向slider幻灯片是否循环滚动，默认为true
- 13.autoScrolling
是否使用插件的滚动方式，默认为true，如果选择false，则会出现浏览器自带的滚动条，将不会按页滚动，而是按照滚动条的默认行为来进行滚动。
- 14.scrollBar：
是否包含滚动条，默认为false，如果设置为true，则浏览器自带的滚动条会出现，页面的滚动还是按页滚动，但是滚动条的默认行为也有效。
- 15.paddingTop/paddingBottom:
设置每一个section页面顶部和底部的padding值，默认为0，但是当页面上有固定在顶部或者底部的菜单或者导航栏的时候，可以使用这两项进行配置。（paddingTop:"200px"）
- 16.fixedElements
固定的元素，默认为null，需要配置一个jquery选择器。在页面滚动的时候，fixedElements设置的元素固定不变。
- 17.keyboardScrolling
是否可以使用键盘方向键导航，默认值为true
- 18.tochuSensitivity
在移动端设备上滑动页面的敏感性，默认为5，是按百分比来衡量的，最高为100，越大则越难滑动
- 19.continuousVertical：
页面是否循环滚动，默认为false。如果设置为true，则页面会循环滚动，这样页面滚动起来不像loopTop和loopBottom一样会出现跳动，注意：此属性和loopTop/loopBottom不兼容，不能同时设置
- 20.animateAnchor
锚链接是否可以控制页面滚动动画，默认为true。如果设置为false，则通过锚链接定位到页面某个点不会有动画效果
- 21.recordHistory
是否记录历史记录，默认为true可以记录页面的滚动历史，通过浏览器的前进后退按钮来进行导航。注意：如果设置了autoScrolling：false，那么这个配置项也会被关闭，即设置为false
- 22.Menu
绑定菜单，设定相关属性与anchors的值对应后，菜单可以控制滚动，默认为false。可以设置为jquery的选择器
<ul id="fullpageMenu">
                    <li date-menuanchor='page1'><a href="#page1">1 section</a></li>
                    <li date-menuanchor='page2'><a href="#page2">2 section</a></li>
                    <li date-menuanchor='page3'><a href="#page3">3 section</a></li>
                    <li date-menuanchor='page4'><a href="#page4">4 section</a></li>
            </ul>
anchors:['page1','page2','page3','page4'],
                menu:"#fullpageMenu"
- 23.Navigation
是否显示导航，默认为false，如果设置为true会显示小圆点儿，作为导航
- 24.navigationPosition
设置导航小圆点的位置 可以是left或者right 默认为right
- 25.navigationTooltips
  导航小圆点的tooltips设置，默认为[]，注意按照顺序设置
- 26.showActiveTooltip
是否显示当前导航的tooltip信息，默认是不显示（false）
- 27.slidesNavigation
是否显示横向幻灯片的导航，默认是false
- 28.SlidesNavPosition
横向幻灯片导航的位置，默认为bottom，可以设置为top或者bottom
- 29.scrollOverflow
内容超过满屏后是否显示滚动条，默认为false。如果设置为true，则会显示滚动条，如果要滚动查看内容，还需要jquery.slimscroll插件的配合。Slimscroll插件的主要是用于模拟传统浏览器的滚动条样式
- 30.sectionSelector
section的选择器 默认为.section
- 31.slideSelector
slide的选择器默认为.slide
Fullpage的方法：
$.fn.fullpage.xxx()
1.moveSectionUp()
向上滚动一页
2.moveSectionDown()
向下滚动一页
3.moveTo(section,slide)
滚动到第几页第几张幻灯片 注意：页面是从1开始，幻灯片是从0开始
4.silentMoveTo(section,slide)
与moveTo(section,slide)一样，但是没有动画效果
5.moveSlideRight()
幻灯片向右滚动
6.moveSlideLeft()
幻灯片向左滚动
7.setAutoScrolling(boolean)
8.setLockAnchors(boolean)
9.setRecordHistory(boolean)
10.setScrollingSpeed(millinsecond)
11.setAllowScrolling(boolean,[directions])
添加或者删除鼠标滚轮或者滑动控制，第一个参数为true时启用，false时禁用，后面的参数为方向，取值为all，left，right，up，down，可以使用多个，使用多个时用逗号隔开
12.destroy(type)
销毁fullpage特效，type可以不写，或者使用all，不写type，fullpage给页面添加的样式和html元素还在，如果使用all，则样式、html全部销毁，页面恢复和不使用fullpage相同的效果。
13.reBuild（）
重新更新页面和尺寸，用于通过ajax请求改变了页面结构之后，重建效果。
Lazy loading
