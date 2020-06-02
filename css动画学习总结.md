# css动画学习总结
## 动画定义
* 以一定的速度（影视：每秒24帧；游戏每秒30帧）连续播放图片，肉眼因视觉残象产生的错觉画面。
## 浏览器渲染过程
1. 根据HTML构建HTML树
2. 根据CSS构建CSS树
3. 合并HTML和CSS成一颗渲染树（render tree）
4. Layout布局（文档流、盒模型、计算大小和位置）
5. Paint绘制（边框颜色、文字颜色、阴影等）
6. Composite合成（根据层叠关系展示页面）

## transition
* 一般在实现比较简单的动画效果（只有开始和结束两种状态）使用，可以补充中间帧。
* transition：属性名 时长 过渡方式 延迟  
  例：transition：left 200ms linear 2s  
  也可以控制两个不同属性，用逗号隔开就行  
  例：transition：left 1s， top 2s
  可以用all代表所有属性
  例：transition：all 2s
  过渡方式有很多可以MDN查看
* 注意点：display: none => block 没办法过度，一般改成visibility: hidden => visible

## animation
* 先定义@keyframes  
  ~~~html
    @keyframes 动画名 {
        from {
            transform: scale(1);
        }

        to {
            transform: scale(1.5);
        }
    }
  ~~~
  或者
  ~~~html
    @keyframes 动画名 {
        0% {top: 0; left: 0;}
        50% {top: 50px; left: 100px;}
        100% {top: 25px; left: 120px;}
    }
  ~~~
* 在要添加动画的元素style里面加上animation
animation: 动画名 时长 过渡方式 延迟 次数 方向 填充模式 是否暂停;
例animation: heart 1.5s ease-in 1s infinite alternate-reverse;
填充模式animation-fill-mode: forwards; 停在最后一帧  