# mixin.less
mixin.less, which can be imported into mobile projects, compatible to major mobile environment, including Android's and iOS's core of webview as well as X5 core.



## Usage

You can ```@import "mixin"``` into a less file.



## Doc

1. border-radius

   ``` less
   .rounded(@radius: 9999px)
   .border-radius(@topleft: 0, @topright: 0, @bottomright: 0, @bottomleft: 0)
   ```

2. flexbox 

   ``` less
   // horizontally center and vertically middle
   .flex-center-middle();

   /* Although, we provide the flex compatible code snippet, we still recommand you 
    * to use Postcss to deal with this case, and the recommanded gulp plugin:
    * https://github.com/targetkiller/postcss-flexadapter
    */

   // display: flex
   .flex-wrapper();

   // reverse the order of boxes, defaultly the orientation is horizontal
   .flex-reverse(@orient: horizontal);

   // make the boxes' order be veritcal
   .flex-col();

   // space between child ele-s
   .flex-justify-content(space-between | space-around | center | flex-start | flex-end);

   // align relationships between child ele-s
   .flex-align-items(flex-start | flex-end | center | baseline | stretch);

   // ratio of flexed child ele, default, it's 1
   .flex-item(@num:1);

   /*
    * end flex compatible code snippet
    */
   ```

3. position
   ```less
   // pos:abs, tblr:0
   // fill in the closest pos:rel parent ele
   .fill-in-box(@zindex: 0)

   // using position to make perfectly center | just center | just middle | using wh to cal
   .pos-center-middle(cm | c | m | @w, @h)
   ```

4. text
   ```less
   // text overflow using ellipsis
   .text-ellipsis(@w: 100%)

   // forcing word to break
   .word-break()

   // forcing word not to break
   .no-wrap()
   ```

5. transform
   ```less
   // transform for all availiable argv
   .transform()

   // divide the specific tranform effects into diff 
   .rotation(@deg: 5deg)
   .scale(@ratio: 1.5)
   .translate(@x:0, @y:0)
   .translate3d(@x:0, @y:0, @z:0)
   ```

6. animation
   ```less
   // animation for all availiable argv
   .animation(@anim)
   .animation-duration(@animation-duration)
   .animation-delay(@animation-delay)
   .// when cb timing function is used, need to be compatible to Andriod 4.2-
   .animation-timing-function(@af)
   ```

7. transition
   ```less
   // transition for all availiable argv
   .transition(@transition)
   .transition-duration(@transition-duration)
   .transition-delay(@transition-delay)
   // when cb timing function is used, need to be compatible to Andriod 4.2-
   .transition-timing-function(@tf)
   ```

8. box-sizing
   ```less
   // box-sizing, default value is 'border-box' 
   .box-sizing(@bs: border-box)
   ```

9. background-size
   ```less
   // background-size, default value is 'cover'
   .background-size(@bs: cover)
   ```

10. gradient
    ```less
    // e.g .gradient(linear, rgba(231,195,122,1), rgba(211,175,104,1));
    // must input @type and @colors 
    .gradient(@type; @colors; @dir: 0deg)
    ```

11. triangle
    ```less
    // little triangle, usually used in bubble tip or dropdown
    // 4 directions need to be picked
    .triangle('down'|'left'|'up'|'right', @size:10px, @color:#000)
    ```

12. box-shadow
    ```less
    // no input restriction
    .box-shadow(@argv)

    // default box-shadow
    .normal-shadow(@horizontal: 0, @vertical: 1px, @blur: 2px, @alpha: 0.1)
    // using box-shadow to build inner border
    .inner-border(@border-width: 1px, @color: #000)
    // inset box-shadow
    .inner-shadow(@horizontal: 0, @vertical: 1px, @blur: 2px, @alpha: 0.4)
    ```



Thanks to [mixinsless](http://mixinsless.com/ ) and [compass-flexbox](https://github.com/stevenbenisek/compass-flexbox). Without them, we would have waste some time to find proper snippet.