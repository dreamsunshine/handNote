适配iphone x
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">

viewport 可以设置的选项就是 viewport-fit,它有三个可选值：
* contain: The viewport should fully contain the web content. 可视窗口完全包含网页内容
* cover: The web content should fully cover the viewport. 网页内容完全覆盖可视窗口
* auto: The default value, 同contain的作用

样式适配
@media only screen and (device-width: 375px) and (device-height: 812px) and

(-webkit-device-pixel-ratio: 3) {

    /*增加头部适配层*/
    .has-topbar {
        height: 100%;
        box-sizing: border-box;
        padding-top: 44px;
        &:before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 44px;
            background-color: #000000;
            z-index: 9998;
        }
    }
    /*增加底部适配层*/
    .has-bottombar {
        height: 100%;
        box-sizing: border-box;
        padding-bottom: 34px;
        &:after {
            content: '';
            z-index: 9998;
            position: fixed;
            left: 0;
            bottom: 0;
            width: 100%;
            height: 34px;
            background: #f7f7f8;
        }
    }
    /*导航操作栏上移*/
    .bottom-menu-fixed {
        bottom: 34px;
    }
}


iOS 11.0 uses the constant() syntax, but future versions will only support env()!
The 4 layout guide constants are:
* env(safe-area-inset-top): The safe area inset amount (in CSS pixels) from the top of the viewport.
* env(safe-area-inset-bottom): The safe area inset amount (in CSS pixels) from the bottom of the viewport.
* env(safe-area-inset-left): The safe area inset amount (in CSS pixels) from the left of the viewport.
* env(safe-area-inset-right): The safe area inset amount (in CSS pixels) from the right of the viewport.

header {
    /* ... */

    /* Status bar height on iOS 10 */
    padding-top: 20px;

    /* Status bar height on iOS 11.0 */
    padding-top: constant(safe-area-inset-top);

    /* Status bar height on iOS 11+ */
    padding-top: env(safe-area-inset-top);
}

