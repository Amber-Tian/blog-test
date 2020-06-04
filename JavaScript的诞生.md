# JavaScript的诞生
1. 1994年，网景公司（Netscape）发布了Navigator浏览器0.9版。这是历史上第一个比较成熟的网络浏览器，轰动一时。但是，这个版本的浏览器只能用来浏览，不具备与访问者互动的能力。**......网景公司急需一种网页脚本语言，使得浏览器可以与网页互动。**
2. 1995年Sun公司将Oak语言改名为Java，正式向市场推出。Sun公司大肆宣传，许诺这种语言可以"一次编写，到处运行"(Write Once, Run Anywhere)，它看上去很可能成为未来的主宰。  
   <img src="https://bkimg.cdn.bcebos.com/pic/b03533fa828ba61ef518ba0d4c34970a304e5919?x-bce-process=image/watermark,g_7,image_d2F0ZXIvYmFpa2U5Mg==,xp_5,yp_5" alt="Java" width="200px">  
网景公司动了心，决定与Sun公司结成联盟。它不仅允许Java程序以applet(小程序)的形式，直接在浏览器中运行;甚至还考虑直接将Java作为脚本语言嵌入网页，只是因为这样会使HTML网页过于复杂，后来才不得不放弃。  
**总之，当时的形势就是，网景公司的整个管理层，都是Java语言的信徒，Sun公司完全介入网页脚本语言的决策。**因此，Javascript后来就是网景和Sun两家公司一起携手推向市场的，这种语言被命名为"Java+script"并不是偶然的。
1. 此时，34岁的系统程序员Brendan Eich登场了。1995年4月，网景公司录用了他。  
   <img src="https://bkimg.cdn.bcebos.com/pic/838ba61ea8d3fd1f84237b7f324e251f95ca5f49?x-bce-process=image/watermark,g_7,image_d2F0ZXIvYmFpa2U3Mg==,xp_5,yp_5" alt="Brendan Eich" width="200px">  
   **1995年5月，网景公司做出决策，未来的网页脚本语言必须"看上去与Java足够相似"，但是比Java简单，使得非专业的网页作者也能很快上手。**Brendan Eich被指定为这种"简化版Java语言"的设计师。但是，他对Java一点兴趣也没有。为了应付公司安排的任务，他只用10天时间就把Javascript设计出来了。由于设计时间太短，语言的一些细节考虑得不够严谨，导致后来很长一段时间，Javascript写出来的程序混乱不堪。所以，**Javascript语言实际上是两种语言风格的混合产物----（简化的）函数式编程+（简化的）面向对象编程。**这是由Brendan Eich（函数式编程）与网景公司（面向对象编程）共同决定的。
2. 如果不是公司的决策，Brendan Eich绝不可能把Java作为Javascript设计的原型。作为设计者，他一点也不喜欢自己的这个作品：
>"与其说我爱Javascript，不如说我恨它。它是C语言和Self语言一夜情的产物。十八世纪英国文学家约翰逊博士说得好：'它的优秀之 处并非原创，它的原创之处并不优秀。' (the part that is good is not original, and the part that is original is not good.)"
