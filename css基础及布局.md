# css基础及布局（2020.6.1）
学习总结：  
1. border调试法（没加border别写css）；
2. 盒模型
   * content-box（width表示内容区域宽度不含padding和border）
   * border-box（width表示content+padding+border）
3. margin合并问题及解决办法
   * 兄弟合并问题可用inline-block消除
   * 父子合并问题解决办法（都是加在父元素上）：1.padding或border挡住；2.overflow:hidden；3.display:flex
4. float布局注意的问题
   * 父元素别忘了清浮动（.clearfix::after{ content:""; display: block; clear: both;}）
   * IE6/7存在双倍margin bug解决办法：1.margin值减半；2.display: inline-block
   * margin: 0 auto写成{margin-left: auto; margin-right: auto}要好些，目的是居中上下边距没有必要设置避免重叠问题。
5. float布局和flex布局解决平均布局右边空隙问题（设置负margin-right）
   * 给内容部分加一个div，给div一个负margin-right，值就是隙宽度。

### flex布局和grid布局完成了FLEXBOX FROGGY和GRID GARDEN