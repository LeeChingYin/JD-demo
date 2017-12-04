1.npm install 安装

2.npm run start 运行

3.npm run build 打包生成

3.优雅降级：页面中在banner，商品hover时使用了animate等属性，在IE8,9中无法正常显示，但是基本布局不破裂，还是会有适当的hover效果。而banner则会正常显示，省略动画效果。

4.切图时存在偏差，如进度条中有一小块蓝色的图片，未能切割，暂且只使用红色，有待补上。


优化部分

1.删除css中过多的base64，减少css文件大小。

2.使用UglifyJsPlugin压缩js。

3.defer加载js，在空闲时间加载js。

4.tinypng.com压缩图片（但是压缩后，头图部分的图片依旧有点大）。

5.懒加载图片。头图以下的部分均实现懒加载（“优惠券”，“整点秒杀”，“爆款必备”，“下单实时赢大奖”）。滚动事件添加防抖动、防节流函数。

6.“整点秒杀”点击后异步加载该时间段数据。

7.补充：在服务器使用gzip压缩可以大大减少文件的体积。但是demo没有实现。


以上的优化完成后，Chrome设置限速200Kb/s情况下的结果：
![](https://github.com/LeeChingYin/JD-demo/blob/master/app/images/optimizeResult.jpg)

优化结果仍然有待改善，主要就是图片方面有点大...

另外限速200Kb/s, 因为加载速度比较慢，头图的有2个部分使用了css3 animate会受到影响，但是不影响整体的演示，对于限速用户能展示整体页面为主要目的，对于较快网速用户能展示较好的交互（含动画）。








