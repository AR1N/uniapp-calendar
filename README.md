# ren-calendar

### 简介
> 一款可收缩，可标记日期的日历，目前只在uni-app项目中使用，其他平台适配兼容未知，如有帮助到你不胜荣幸，欢迎Star！


### 调用示例

```
<view class="content">
    <ren-calendar ref='ren' :markDays='markDays' :headerBar='false' @onDayClick='onDayClick'></ren-calendar>
    <view class="change">选中日期：{{curDate}}</view>
</view>
```

```
 import RenCalendar from '@/components/ren-calendar/ren-calendar.vue'
	export default {
        components:{
            RenCalendar
        },
		data() {
			return {
				curDate:'',
                markDays:[]
			}
		},
		onReady() {
            let today = this.$refs.ren.getToday().date;
            this.curDate = today;
            this.markDays.push(today);
		},
		methods: {
            onDayClick(data){
                this.curDate = data.date;
            }
		}
	}
```

### 属性说明

| 属性名 | 类型   | 默认值 | 说明   |
| :----- | :----- | :----- | :----- |
| weekstart | Number | 0 （即周日为第一天）| 以周几为第一天|
| markDays | Array | - | 标记的日期集合 |
| headerBar | Boolean | true | 是否展示月份切换按钮 |
| open | Boolean | true | 是否展开日历 |
| collapsible | Boolean | true | 是否可收缩 |
| disabledAfter | Boolean | false | 未来日期是否不可点击 |


### 事件说明

| 事件名 | 说明   | 
| :----- | :----- | 
| onDayClick | 点击日期时触发，返回当前选中日期, 如：{date: "2020-07-18", week: "星期六"}  |



### 方法说明

| 方法名 | 说明   | 
| :----- | :----- | 
| changYearMonth | 改变年月，初始化时需在onReady后通过$refs调用  |

### Tips

* 如果不能满足场景需求可自行更改组件源代码来满足需求

### 预览

![ren-calendar](https://i.loli.net/2020/07/16/rN5sGIofx7FJz8Y.png)
![ren-calendar](https://i.loli.net/2020/07/16/a14rGY8JgIpimqv.png)
![ren-calendar](https://i.loli.net/2020/07/16/ejMgK3EqLIdhPRO.png)
![ren-calendar](https://i.loli.net/2020/07/16/LKZIRAgDweESxWl.png)
