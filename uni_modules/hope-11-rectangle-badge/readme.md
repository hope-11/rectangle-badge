# rectangle-badge

### 引入
```vue
import RectangleBadge from '@/uni_modules/hope-11-rectangle-badge/components/hope-11-rectangle-badge/rectangle-badge.vue'
```

### 使用
```vue
<RectangleBadge  value="已完成" type="success" @click="onBadgeClick">
	<view class="content"></view>
</RectangleBadge>
```

### 事件
```vue
const onBadgeClick = (e) => {
	console.log(e)
}
```

### 属性
参数|说明|类型|默认值
---|:--|:--|:---:
value|绑定值，Object时格式：{label: '已完成', value: 1}|String, Object|''
type|类型，可选值：default, primary, success, warning, error|String|'default'
position|位置，可选值：右上：tr，左上：tl，左下：bl，右下：br|String|'tr'
size|尺寸, 可选值：mini, default, middle, large|String|'default'
plain|朴素样式|String|false
border|边框|Boolean|false
color|自定颜色，格式：[主色，辅助色]|Array|[]
minWidth|最小宽度|String|''

### 事件
事件名称|说明|回调参数
---|:--|:---:
click|标签的点击事件|value

### 说明
该组件还未进行多平台详尽测试，可自行尝试使用，如有问题请在评论区指出或联系作者，多谢支持！