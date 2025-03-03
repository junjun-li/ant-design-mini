---
nav:
  path: /components
group:
  title: 导航
  order: 6
toc: false
---
# Tabs 标签页
内容组之间进行导航切换
## 何时使用
- 内容组之间进行导航切换
- 当前内容需要分成同层级结构的组，进行内容切换展示，用在表单或者标准列表界面的顶部

## 注意事项

- 目前仅支持一个页面中使用一次 **Tabs** 组件；
- 在基础库 2.x 版本下，内嵌 scroll-view 产生 scroll-view 无法滚动的情况，建议scroll-view 阻止 touch 事件冒泡：catchTouchStart、catchTouchMove。详见[官方文档](https://opendocs.alipay.com/mini/component/scroll-view)
- Tabs 内部使用 transform 样式以进行轮播，会导致内嵌弹层显示问题，建议内部不嵌套包含弹层的组件或者使用 fallback 属性，以自己实现简单版的“轮播”，详见下方 fallback 的 demo。

## 代码示例
### 基本使用
<code src='../../demo/pages/Tabs'></code>

### fallback
<code src='../../demo/pages/TabsFallback'></code>

## 属性

#### Tabs
| 属性 | 类型 | 必填 | 默认值 | 说明 |
| -----|-----|-----|-----|----- |
| type | 'basis' &verbar; 'capsule' &verbar; 'mixin' &verbar; 'title' | 否 | 'basis' | 类型，basis(基础)，capsule(胶囊)，mixin(混合) |
| index | number | 否 | 0 | 当前激活的索引 |
| animation | boolean | 否 | false | 是否有过渡动画 |
| swipeable | boolean | 否 | false | 是否支持手势切换 |
| sticky | boolean | 否 | false | 是否支持吸顶 |
| touchAngle | number | 否 | 45 | 用户左右滑动手势生效的滑动角度。角度根据 touchstart 事件和首次 touchmove 事件的坐标计算得出。数值越小越对用户的滑动方向准确度要求越高 |
| swipeRatio | number | 否 | 0.2 | 用户左右滑动手势触发切换的阈值，当滑动距离超过阈值时进行 `swiper-item` 切换 |
| swipeSpeed | number | 否 | 0.05 | 用户左右滑动手势对应的滑动距离，数值越小则需要用户手势相同位移下 `swiper-item` 位移越小 |
| plus | string &verbar; slot | 否 | - | 右上角操作按钮，自定义节点 |
| title | slot-scope | 否 | - | 自定义 tab 标题样式，仅在 type 为 basis 时可用 |
| className | string | 否 | - | 类名 |

#### TabItem
| 属性 | 类型 | 必填 | 默认值 | 说明 |
| -----|-----|-----|-----|----- |
| tab | {title: string; subTitle?: string; badge?: number; disabled?: boolean}[]| 是 | - | 每一项 tab 内容 |
| className | string | 否 | - | 类名 |

## 事件

#### Tabs
| 事件名 | 说明 | 类型 |
| -----|-----|-----|
| onChange | 面板切换时候，触发回调 |(index: number) => void|

## 插槽
#### Tabs
| 名称 | 说明 |
| ----|----|
| plus | 表单项额外内容 |

## 作用域插槽
#### Tabs
| 名称 | 说明 |
| ----|----|
| title | 自定义 tab 标题样式 |

## 样式类
#### Tabs
| 类名 | 说明 |
| -----|-----|
| amd-tabs | 整体样式 |
| amd-tabs-bar | 上方标题区域样式 |
| `amd-tabs-bar-active` |  `上方标题区域激活时样式` |
| `amd-tabs-bar-active:after` | `上方标题区域激活时 indicator 样式` |
| amd-tabs-bar | 上方标题区域样式 |
| amd-tabs-bar-sticky | 吸顶状态样式 |
| amd-tabs-bar-plus | 右上角标签样式 |
| amd-tabs-bar-fade | 两侧渐淡效果样式 |
| amd-tabs-bar-fade-left | 左侧渐淡效果样式 |
| amd-tabs-bar-fade-right | 左侧渐淡效果样式 |
| amd-tabs-bar-scroll-view | 内部ScrollView组件样式 |
| amd-tabs-bar-wrap| 每个标题的样式 |
| amd-tabs-bar-item | 每个标题的样式 |
| amd-tabs-bar-basis | type 为 basis 时，每个标题的样式 |
| amd-tabs-bar-capsule | type 为 capsule 时，每个标题的样式 |
| amd-tabs-bar-capsule-title | type 为 capsule 时，每个标题内部文字的样式 |
| amd-tabs-bar-capsule-badge | type 为 capsule 时，每个标题内部 badge 的样式 |
| amd-tabs-bar-mixin| 内type 为 mixin 时，每个标题的样式 |
| amd-tabs-bar-mixin-title| 内type 为 mixin 时，每个标题的文字样式 |
| amd-tabs-bar-mixin-subtitle| 内type 为 mixin 时，每个标题的副标题样式 |
| amd-tabs-bar-disabled | 禁用态选项卡样式 |

#### TabItem
| 类名 | 说明 |
| -----|-----|
| amd-tabs-item | 整体样式 |
| amd-tabs-item-pane | 整体样式 |


<style> 
table th:first-of-type { width: 180px; } 
.__dumi-default-layout-content article table:first-of-type th:nth-of-type(2)  {
    width: 140px
} 
.__dumi-default-layout-content article table:first-of-type th:nth-of-type(3)  {
    width: 30px
} 
.__dumi-default-layout-content article table:first-of-type th:nth-of-type(4)  {
    width: 50px
} 
.__dumi-default-layout-content article table:nth-of-type(2) th:nth-of-type(2)  {
    width: 140px
} 
.__dumi-default-layout-content article table:nth-of-type(2) th:nth-of-type(3)  {
    width: 30px
} 
.__dumi-default-layout-content article table:nth-of-type(2) th:nth-of-type(4)  {
    width: 50px
} 
.__dumi-default-layout-content article table:nth-of-type(6) th:nth-of-type(2)  {
    width: 300px
} 
.__dumi-default-mobile-previewer:nth-of-type(2)::after {
    border-bottom: none!important;
}
</style> 
