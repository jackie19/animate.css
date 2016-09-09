## usage width angular


```javascript
var commonServices = angular.module('commonServices', []);
commonServices.constant('props',{"Default":["none"],"Attention Seekers":["bounce","flash","pulse","rubberBand","shake","swing","tada","wobble","heartbeat","slideUp","slideDown","scaleUp","scaleDown"],"Bouncing Entrances":["bounceIn","bounceInDown","bounceInLeft","bounceInRight","bounceInUp"],"Bouncing Exits":["bounceOut","bounceOutDown","bounceOutLeft","bounceOutRight","bounceOutUp"],"Fading Entrances":["fadeIn","fadeInDown","fadeInDownBig","fadeInLeft","fadeInLeftBig","fadeInRight","fadeInRightBig","fadeInUp","fadeInUpBig"],"Fading Exits":["fadeOut","fadeOutDown","fadeOutDownBig","fadeOutLeft","fadeOutLeftBig","fadeOutRight","fadeOutRightBig","fadeOutUp","fadeOutUpBig"],"Flippers":["flip","flipInX","flipInY","flipOutX","flipOutY"],"Lightspeed":["lightSpeedIn","lightSpeedOut"],"Rotating Entrances":["rotateIn","rotateInDownLeft","rotateInDownRight","rotateInUpLeft","rotateInUpRight"],"Rotating Exits":["rotateOut","rotateOutDownLeft","rotateOutDownRight","rotateOutUpLeft","rotateOutUpRight"],"Sliding Entrances":["slideInUp","slideInDown","slideInLeft","slideInRight"],"Sliding Exits":["slideOutUp","slideOutDown","slideOutLeft","slideOutRight"],"Zoom Entrances":["zoomIn","zoomInDown","zoomInLeft","zoomInRight","zoomInUp"],"Zoom Exits":["exZoomSmallIn","zoomOut","zoomOutDown","zoomOutLeft","zoomOutRight","zoomOutUp"],"Specials":["hinge","rollIn","rollOut"],"Extends":["exBounce","exMicroRight","exMicroDown","exMicroLeft","exMicroUp","exUpLeftIn","exUpRightIn","exDownLeftIn","exDownRightIn","exClockwise","exAnticlockwise","twisterInUp","twisterInDown"]})

commonServices.constant('dict', { "Default": "默认", "none": "无", "Attention Seekers": "强调", "bounce": "弹跳", "flash": "闪烁", "pulse": "脉动", "rubberBand": "橡皮圈", "shake": "摇动", "swing": "摆动", "tada": "波动", "wobble": "晃动", "heartbeat": "心跳", "slideUp": "上移", "slideDown": "下移", "scaleUp": "扩张", "scaleDown": "收缩", "Bouncing Entrances": "弹现", "bounceIn": "弹动出现", "bounceInDown": "向下弹入", "bounceInLeft": "从左弹入", "bounceInRight": "从右弹入", "bounceInUp": "向上弹入", "Bouncing Exits": "弹出", "bounceOut": "弹动离开", "bounceOutDown": "向下弹出", "bounceOutLeft": "向左弹出", "bounceOutRight": "向右弹出", "bounceOutUp": "向上弹出", "Fading Entrances": "渐现", "fadeIn": "渐现", "fadeInDown": "向下渐现", "fadeInDownBig": "大幅向下渐现", "fadeInLeft": "从左渐现", "fadeInLeftBig": "大幅从左渐现", "fadeInRight": "从右渐现", "fadeInRightBig": "大幅从右渐现", "fadeInUp": "向上渐现", "fadeInUpBig": "大幅向上渐现", "Fading Exits": "渐隐", "fadeOut": "渐隐", "fadeOutDown": "向下渐隐", "fadeOutDownBig": "大幅向下渐隐", "fadeOutLeft": "向左渐隐", "fadeOutLeftBig": "大幅向左渐隐", "fadeOutRight": "向右渐隐", "fadeOutRightBig": "大幅向右渐隐", "fadeOutUp": "向上渐隐", "fadeOutUpBig": "大幅向上渐隐", "Flippers": "翻转", "flip": "翻转", "flipInX": "横向翻入", "flipInY": "纵向翻入", "flipOutX": "横向翻出", "flipOutY": "纵向翻出", "Lightspeed": "快速", "lightSpeedIn": "快速进入", "lightSpeedOut": "快速移出", "Rotating Entrances": "旋入", "rotateIn": "旋转进入", "rotateInDownLeft": "从左往下旋入", "rotateInDownRight": "从右往下旋入", "rotateInUpLeft": "从左往上旋入", "rotateInUpRight": "从右往上旋入", "Rotating Exits": "旋出", "rotateOut": "旋转离开", "rotateOutDownLeft": "向左下旋出", "rotateOutDownRight": "向右下旋出", "rotateOutUpLeft": "向左上旋出", "rotateOutUpRight": "向右上旋出", "Sliding Entrances": "滑入", "slideInUp": "向上滑入", "slideInDown": "向下滑入", "slideInLeft": "从左滑入", "slideInRight": "从右滑入", "Sliding Exits": "滑出", "slideOutUp": "向上滑出", "slideOutDown": "向下滑出", "slideOutLeft": "向左滑出", "slideOutRight": "向右滑出", "Zoom Entrances": "放大", "zoomIn": "放大进入", "exZoomSmallIn": "缩小进入", "zoomInDown": "向下放大", "zoomInLeft": "从左放大", "zoomInRight": "从右放大", "zoomInUp": "向上放大", "Zoom Exits": "缩小", "zoomOut": "缩小离开", "zoomOutDown": "向下缩小", "zoomOutLeft": "向左缩小", "zoomOutRight": "向右缩小", "zoomOutUp": "向上缩小", "Specials": "特效", "hinge": "剥落", "rollIn": "翻滚进入", "rollOut": "翻滚离开", "Extends": "扩展动画", "exBounce": "Q弹", "exMicroRight": "向右微移", "exMicroDown": "向下微移", "exMicroUp": "向上微移", "exMicroLeft": "向左微移", "exUpLeftIn": "来自右下", "exUpRightIn": "来自左下", "exDownLeftIn": "来自右上", "exDownRightIn": "来自左上", "exClockwise": "顺时针旋转", "exAnticlockwise": "逆时针旋转", "twisterInUp": "右侧旋风进入", "twisterInDown": "左侧旋风进入"})

commonServices.factory('animationsOptions', ['props','dict', function (props, dict) {
    var options = {}
    var groupItems = []
    var groupMapping = {}

    angular.forEach(props, function (item, key) {

        angular.forEach(item, function (value) {
            groupItems.push(value)
            groupMapping[value] = dict[key] || key
        });
    });

    options.groupMapping = groupMapping
    options.groupItems = groupItems
    options.dict = dict

    return options
}])
```

```javascript
$scope.options = animationsOptions
```

```html
  <select class="form-control input-sm" ng-model="valOf" ng-options="(options.dict[value] || value) group by options.groupMapping[value] for value in options.groupItems">
```
