<template>
	<view>
		<uni-steps :options="updateLog" active-color="#007AFF" :active="active" direction="column" />
		<uni-notice-bar single text="Developed by Lu Ang"></uni-notice-bar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				updateLog: [{
					title: '万能题库新增粘贴并查询和伪装模式功能',
					desc: '2023-11-19'
				}, {
					title: '万能题库禁用icodef题库接口，新增jszkk查题接口',
					desc: '2023-11-05'
				}, {
					title: '修复了万能题库字数限制问题和对enncy接口查询时未能对所需查询的问题进行预URL编码而导致部分代码编程题无法查询到结果的问题',
					desc: '2023-11-05'
				}, {
					title: '万能题库优化和新增两个题库接口（enncy、icodef），提高了查询并发能力和搜题成功率，修复了本地部署icodef接口CORS跨域问题',
					desc: '2023-11-04'
				}, {
					title: '新增万能题库功能',
					desc: '2023-10-31'
				}, {
					title: '更新学生信息页面复制学号的功能，新增实验室安全准入教育题库页面',
					desc: '2023-10-07'
				}, {
					title: '更新了学生信息、更新日志页面功能',
					desc: '2023-09-27'
				}, {
					title: '更新了主页页面，课程预览等功能',
					desc: '2023-09-23'
				}, {
					title: '紧急修复课表错误问题',
					desc: '2023-09-20'
				}, {
					title: '正式上线班群',
					desc: '2023-09-15'
				}]
			}
		},
		methods: {

		}
	}
</script>

<style>

</style>