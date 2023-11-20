<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<button class="mt-30 mb-15" @tap="simpleImport">一键导入</button>

		<uni-link class="mb-30" href="./static/课表日历文件（请用系统自带日历软件导入）.ics" text="只下载课表文件"></uni-link>

		<uni-card title="使用须知" extra="" note="Tips">
			请点击右上角使用默认浏览器打开进行导入，
			如果还是没反应，请换苹果手机。
			<br>
			安卓手机请勿关闭自动更新订阅，否则可能导致课程表和别人不一样！（调课、错峰、补课、夏冬令时变更）
		</uni-card>

		<uni-card title="其他课表工具" extra="" note="Tips">
			1. 可以等开学自行进入教务系统查询自己课表<br>
			2. 可以用第三方公众号“泉师助手”查看课表<br>
			3. 可以看下面学长发的图片（长按保存）<br>
			<image src="../../static/课表.jpg" mode="scaleToFill"></image><br>
			4. 用我自己写的课表凑合用（也就是上面的一键导入），如有问题找我反馈（卢昂）<br>
		</uni-card>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '23软件工程2班课表日历导入工具'
			}
		},
		onLoad() {

		},
		methods: {
			simpleImport() {
				window.location.href =
					"webcal://p206-caldav.icloud.com.cn/published/2/MTAwNTk3MTQyNTkxMDA1OSQUlL5LjR23OBQlLqTENeJQ5Av-qSEx8KA4AnfJ8Bjr_Nj68RRY_j970HnpTzTN9R3dJVURLqaUA3Lyg5CMvmM"
			}
		}
	}
</script>

<style scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>