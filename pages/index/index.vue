<template>
	<view>
		<view class="card">
			<uni-section class="mb-10" title="固定的应用" sub-title="固定住的应用将会显示在这里" type="line"></uni-section>
			<uni-grid :column="4" :highlight="true" @change="change" :showBorder="false">
				<uni-grid-item v-for="(item, index) in gridItems" :index="index" :key="index"
					v-show="item.state=='active'">
					<view class="grid-item-box" style="background-color: #fff;">
						<uni-icons :type="item.icon" :size="30" color="#777" />
						<text class="grid-item-box-text">{{item.name}}</text>
					</view>
				</uni-grid-item>
			</uni-grid>
		</view>
		<view class="card">
			<uni-section class="mb-10" title="归档的应用" sub-title="即将下线的功能" type="line"></uni-section>
			<uni-grid :column="4" :highlight="true" @change="change" :showBorder="false">
				<uni-grid-item v-for="(item, index) in gridItems" :index="index" :key="index"
					v-show="item.state=='archive'">
					<view class="grid-item-box" style="background-color: #fff;">
						<uni-icons :type="item.icon" :size="30" color="#777" />
						<text class="grid-item-box-text">{{item.name}}</text>
					</view>
				</uni-grid-item>
			</uni-grid>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				gridItems: [{
					id: 1,
					name: '课表导入',
					state: 'active',
					icon: 'calendar',
					url: '/pages/calendarSubscription/index'
				}, {
					id: 2,
					name: '在线课表',
					state: 'active',
					icon: 'calendar-filled',
					url: '/pages/calendarPreview/index'
				}, {
					id: 3,
					name: '学生信息',
					state: 'active',
					icon: 'contact',
					url: '/pages/classStuInfo/index'
				}, {
					id: 4,
					name: '实验室题库',
					state: 'archive',
					icon: 'list',
					url: '/pages/labExam/index'
				}, {
					id: 5,
					name: '万能题库',
					state: 'active',
					icon: 'search',
					url: '/pages/generalQuestionQuery/index'
				}, {
					id: 6,
					name: '更新日志',
					state: 'active',
					icon: 'info',
					url: '/pages/updateLog/index'
				}]
			}
		},
		methods: {
			change(e) {
				let index = e.detail

				uni.navigateTo({
					url: this.gridItems[index.index].url,
					success: res => {},
					fail: () => {
						uni.showModal({
							content: '尚未开发完成，敬请期待',
							showCancel: false
						});
					},
					complete: () => {}
				});
			}
		}
	}
</script>

<style scoped>
	.grid-item-box {
		flex: 1;
		// position: relative;
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 15px 0;
	}

	.grid-item-box-text {
		font-size: 14px;
		margin-top: 5px;
	}
</style>