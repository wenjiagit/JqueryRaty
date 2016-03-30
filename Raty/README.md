# jQuery Raty
A Star Rating Plugin

插件描述：jQuery Raty这是一个星级评分插件。可以自定义图标，创建各种评级组合，星星数量，每一颗星星的注释，可以在当一个星星被点击时的加回调函数。

## 使用方法
 + 你只需要拥有一个的div来构建Raty
 
```html
  <div></div>
```
```html
 $('div').raty();
``` 

## 得分
 + 使用时我们要开始使用已保存的评级。下例显示当前为3星
 
```html 
 $('div').raty({ score: 3 });
``` 
## 得分回调
 + 如果你需要启动你的分数取决于一个动态值，你可以使用回调。
 + 你可以传递任何值，因为他们，不一定是数据值。你可以使用一个字段的值，例如。

```html
 <div id="star" data-score="1"></div>
``` 
 
```html
$('#star').raty({
      score: function() {
        return $(this).attr('data-score');
      }
   });
``` 

## 分数名称
 + 更改隐藏的名称得分
 
```html
$('div').raty({ scoreName: 'entity[score]' });
```

## 数量
 + 改变星星数量
 + $('#star').raty({ number: 10 });

## 数字回调
 + 您可以收到多少分动态使用回调来设置它

```html
  <div id="star" data-number="3"></div>
```  
```html
  $('#star').raty({
     number: function() {
        return $(this).attr('data-number');
     }
   });
 ```

## 回调 鼠标移出时获取当前选择的星级
```html
 $('#star').raty({
     mouseout: function(score, evt) {
       alert('ID: ' + $(this).attr('id') + "\nscore: " + score + "\nevent: " + evt);
     }
   });
 ```

## Required Files
+ jquery.raty.min.js
+ star-on.png
+ star-off.png

## Options

```js
cancel      : false                                          // Creates a cancel button to cancel the rating.
cancelHint  : 'Cancel this rating!'                          // The cancel's button hint.
cancelOff   : 'cancel-off.png'                               // Icon used on active cancel.
cancelOn    : 'cancel-on.png'                                // Icon used inactive cancel.
cancelPlace : 'left'                                         // Cancel's button position.
click       : undefined                                      // Callback executed on rating click.
half        : false                                          // Enables half star selection.
halfShow    : true                                           // Enables half star display.
hints       : ['bad', 'poor', 'regular', 'good', 'gorgeous'] // Hints used on each star.
iconRange   : undefined                                      // Object list with position and icon on and off to do a mixed icons.
mouseout    : undefined                                      // Callback executed on mouseout.
mouseover   : undefined                                      // Callback executed on mouseover.
noRatedMsg  : 'Not rated yet!'                               // Hint for no rated elements when it's readOnly.
number      : 5                                              // Number of stars that will be presented.
numberMax   : 20                                             // Max of star the option number can creates.
path        : ''                                             // A global locate where the icon will be looked.
precision   : false                                          // Enables the selection of a precision score.
readOnly    : false                                          // Turns the rating read-only.
round       : { down: .25, full: .6, up: .76 }               // Included values attributes to do the score round math.
score       : undefined                                      // Initial rating.
scoreName   : 'score'                                        // Name of the hidden field that holds the score value.
single      : false                                          // Enables just a single star selection.
size        : 16                                             // The size of the icons that will be used.
space       : true                                           // Puts space between the icons.
starHalf    : 'star-half.png'                                // The name of the half star image.
starOff     : 'star-off.png'                                 // Name of the star image off.
starOn      : 'star-on.png'                                  // Name of the star image on.
target      : undefined                                      // Element selector where the score will be displayed.
targetFormat: '{score}'                                      // Template to interpolate the score in.
targetKeep  : false                                          // If the last rating value will be keeped after mouseout.
targetText  : ''                                             // Default text setted on target.
targetType  : 'hint'                                         // Option to choose if target will receive hint o 'score' type.
width       : undefined                                      // Manually adjust the width for the project.
```

## Usage

```html
<div id="star"></div>
```

```js
$('#star').raty();
```

```html
<div class="star"></div>
<div class="star"></div>
<div class="star"></div>
```

```js
$('.star').raty();
```

## Functions

```js
$('#star').raty('score');                   // Get the current score.

$('#star').raty('score', number);           // Set the score.

$('#star').raty('click', number);           // Click on some star.

$('.star').raty('readOnly', boolean);       // Change the read-only state.

$('#star').raty('cancel', boolean);         // Cancel the rating. The last param force the click callback.

$('#star').raty('reload');                  // Reload the rating with the current configuration.

$('#star').raty('set', { option: value });  // Reset the rating with new configurations.

$('#star').raty('reload');                  // Destroy the bind and give you the raw element.
```

