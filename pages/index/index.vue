<template>
	<view class="content">
		<ren-calendar ref='ren' :markDays='markDays' :open="true" :disabledAfter='true'  @onDayClick='onDayClick'></ren-calendar>
        <view class="change">选中日期：{{curDate}}</view>
	</view>
</template>

<script>
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
</script>

<style lang="scss">
    page{
        background-color: #f2f2f2;
    }
	.content {
        padding-top: 50rpx;
		.change{
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto;
            margin-top: 100rpx;
            height: 100rpx;
            color: #b89249;
            background-color: #21191b;
        }
	}
</style>
