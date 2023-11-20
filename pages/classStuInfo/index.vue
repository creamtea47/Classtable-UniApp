<template>
	<view class="">
		<uni-notice-bar showIcon single="" text="提示:您的用户身份组非admin用户组,可访问表数据已受限。"></uni-notice-bar>
		<uni-search-bar placeholder="输入你想要搜索的名字" @input="handleSearch"></uni-search-bar>

		<uni-card :title="item.name" thumbnail="/static/icon/yonghu.svg" :extra="item.student_id" note="Tips"
			v-for="(item,index) in classStuInfo" :key="item.student_id">
			电话：不可查看<br>
			家庭地址：不可查看<br>
			性别：不可查看<br>
			证件号码：不可查看<br>
			政治面貌：不可查看<br>
			原学校：不可查看<br>

			<view slot="actions" class="card-actions">
				<!-- 				<view class="card-actions-item" @click="actionsClick('分享')">
					<uni-icons type="pengyouquan" size="18" color="#999"></uni-icons>
					<text class="card-actions-item-text">分享</text>
				</view>
				<view class="card-actions-item" @click="actionsClick('点赞')">
					<uni-icons type="heart" size="18" color="#999"></uni-icons>
					<text class="card-actions-item-text">点赞</text>
				</view> -->
				<view class="card-actions-item" @click="actionsClick('复制学号',index)">
					<uni-icons type="download" size="18" color="#999"></uni-icons>
					<text class="card-actions-item-text">复制学号</text>
				</view>
			</view>
		</uni-card>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				classStuInfo: [{
						"student_id": "231307054",
						"name": "陈磊"
					},
					{
						"student_id": "231307055",
						"name": "林涛"
					},
					{
						"student_id": "231307056",
						"name": "蓝添荣"
					},
					{
						"student_id": "231307057",
						"name": "叶思阳"
					},
					{
						"student_id": "231307058",
						"name": "史宇豪"
					},
					{
						"student_id": "231307059",
						"name": "杨彬"
					},
					{
						"student_id": "231307060",
						"name": "李欣怡"
					},
					{
						"student_id": "231307061",
						"name": "陈梓毅"
					},
					{
						"student_id": "231307062",
						"name": "吴勇斌"
					},
					{
						"student_id": "231307063",
						"name": "冯德云"
					},
					{
						"student_id": "231307064",
						"name": "朱峰"
					},
					{
						"student_id": "231307066",
						"name": "黄顺铭"
					},
					{
						"student_id": "231307068",
						"name": "谢万龙"
					},
					{
						"student_id": "231307069",
						"name": "林怡超"
					},
					{
						"student_id": "231307070",
						"name": "黄相伟"
					},
					{
						"student_id": "231307071",
						"name": "林恩锦"
					},
					{
						"student_id": "231307072",
						"name": "王民康"
					},
					{
						"student_id": "231307073",
						"name": "王宏佳"
					},
					{
						"student_id": "231307074",
						"name": "卢燕华"
					},
					{
						"student_id": "231307075",
						"name": "蓝卫松"
					},
					{
						"student_id": "231307076",
						"name": "黄亮"
					},
					{
						"student_id": "231307077",
						"name": "黄新烨"
					},
					{
						"student_id": "231307078",
						"name": "张鹏枫"
					},
					{
						"student_id": "231307079",
						"name": "陈颖豪"
					},
					{
						"student_id": "231307080",
						"name": "孙嘉悦"
					},
					{
						"student_id": "231307081",
						"name": "肖朝庆"
					},
					{
						"student_id": "231307082",
						"name": "田镇焜"
					},
					{
						"student_id": "231307083",
						"name": "苏瑜莹"
					},
					{
						"student_id": "231307084",
						"name": "张国卿"
					},
					{
						"student_id": "231307085",
						"name": "高鹏程"
					},
					{
						"student_id": "231307086",
						"name": "林鑫安"
					},
					{
						"student_id": "231307087",
						"name": "王梓昊"
					},
					{
						"student_id": "231307088",
						"name": "周义凯"
					},
					{
						"student_id": "231307089",
						"name": "邢岑溪"
					},
					{
						"student_id": "231307091",
						"name": "陈健健"
					},
					{
						"student_id": "231307092",
						"name": "徐锦涛"
					},
					{
						"student_id": "231307093",
						"name": "黎典"
					},
					{
						"student_id": "231307094",
						"name": "钟诚"
					},
					{
						"student_id": "231307095",
						"name": "刘立华"
					},
					{
						"student_id": "231307096",
						"name": "郑浩"
					},
					{
						"student_id": "231307097",
						"name": "林东平"
					},
					{
						"student_id": "231307098",
						"name": "陈美琴"
					},
					{
						"student_id": "231307099",
						"name": "李志桓"
					},
					{
						"student_id": "231307100",
						"name": "邓嘉伟"
					},
					{
						"student_id": "231307101",
						"name": "张颖萍"
					},
					{
						"student_id": "231307102",
						"name": "林锴炫"
					},
					{
						"student_id": "231307103",
						"name": "李德明"
					},
					{
						"student_id": "231307104",
						"name": "韦丽江"
					},
					{
						"student_id": "231307105",
						"name": "徐露"
					},
					{
						"student_id": "231307106",
						"name": "刘王伟"
					},
					{
						"student_id": "231307107",
						"name": "陈俊杰"
					},
					{
						"student_id": "231307113",
						"name": "徐景辉"
					},
					{
						"student_id": "231307114",
						"name": "赵霖"
					},
					{
						"student_id": "231307115",
						"name": "刘建辉"
					},
					{
						"student_id": "231307116",
						"name": "卢昂"
					},
					{
						"student_id": "231307117",
						"name": "林文涛"
					}
				],
				searchKeyword: '',
				originalClassStuInfo: [{
						"student_id": "231307054",
						"name": "陈磊"
					},
					{
						"student_id": "231307055",
						"name": "林涛"
					},
					{
						"student_id": "231307056",
						"name": "蓝添荣"
					},
					{
						"student_id": "231307057",
						"name": "叶思阳"
					},
					{
						"student_id": "231307058",
						"name": "史宇豪"
					},
					{
						"student_id": "231307059",
						"name": "杨彬"
					},
					{
						"student_id": "231307060",
						"name": "李欣怡"
					},
					{
						"student_id": "231307061",
						"name": "陈梓毅"
					},
					{
						"student_id": "231307062",
						"name": "吴勇斌"
					},
					{
						"student_id": "231307063",
						"name": "冯德云"
					},
					{
						"student_id": "231307064",
						"name": "朱峰"
					},
					{
						"student_id": "231307066",
						"name": "黄顺铭"
					},
					{
						"student_id": "231307068",
						"name": "谢万龙"
					},
					{
						"student_id": "231307069",
						"name": "林怡超"
					},
					{
						"student_id": "231307070",
						"name": "黄相伟"
					},
					{
						"student_id": "231307071",
						"name": "林恩锦"
					},
					{
						"student_id": "231307072",
						"name": "王民康"
					},
					{
						"student_id": "231307073",
						"name": "王宏佳"
					},
					{
						"student_id": "231307074",
						"name": "卢燕华"
					},
					{
						"student_id": "231307075",
						"name": "蓝卫松"
					},
					{
						"student_id": "231307076",
						"name": "黄亮"
					},
					{
						"student_id": "231307077",
						"name": "黄新烨"
					},
					{
						"student_id": "231307078",
						"name": "张鹏枫"
					},
					{
						"student_id": "231307079",
						"name": "陈颖豪"
					},
					{
						"student_id": "231307080",
						"name": "孙嘉悦"
					},
					{
						"student_id": "231307081",
						"name": "肖朝庆"
					},
					{
						"student_id": "231307082",
						"name": "田镇焜"
					},
					{
						"student_id": "231307083",
						"name": "苏瑜莹"
					},
					{
						"student_id": "231307084",
						"name": "张国卿"
					},
					{
						"student_id": "231307085",
						"name": "高鹏程"
					},
					{
						"student_id": "231307086",
						"name": "林鑫安"
					},
					{
						"student_id": "231307087",
						"name": "王梓昊"
					},
					{
						"student_id": "231307088",
						"name": "周义凯"
					},
					{
						"student_id": "231307089",
						"name": "邢岑溪"
					},
					{
						"student_id": "231307091",
						"name": "陈健健"
					},
					{
						"student_id": "231307092",
						"name": "徐锦涛"
					},
					{
						"student_id": "231307093",
						"name": "黎典"
					},
					{
						"student_id": "231307094",
						"name": "钟诚"
					},
					{
						"student_id": "231307095",
						"name": "刘立华"
					},
					{
						"student_id": "231307096",
						"name": "郑浩"
					},
					{
						"student_id": "231307097",
						"name": "林东平"
					},
					{
						"student_id": "231307098",
						"name": "陈美琴"
					},
					{
						"student_id": "231307099",
						"name": "李志桓"
					},
					{
						"student_id": "231307100",
						"name": "邓嘉伟"
					},
					{
						"student_id": "231307101",
						"name": "张颖萍"
					},
					{
						"student_id": "231307102",
						"name": "林锴炫"
					},
					{
						"student_id": "231307103",
						"name": "李德明"
					},
					{
						"student_id": "231307104",
						"name": "韦丽江"
					},
					{
						"student_id": "231307105",
						"name": "徐露"
					},
					{
						"student_id": "231307106",
						"name": "刘王伟"
					},
					{
						"student_id": "231307107",
						"name": "陈俊杰"
					},
					{
						"student_id": "231307113",
						"name": "徐景辉"
					},
					{
						"student_id": "231307114",
						"name": "赵霖"
					},
					{
						"student_id": "231307115",
						"name": "刘建辉"
					},
					{
						"student_id": "231307116",
						"name": "卢昂"
					},
					{
						"student_id": "231307117",
						"name": "林文涛"
					}
				]
			}
		},
		methods: {
			handleSearch(value) {
				this.searchKeyword = value;

				if (value) {
					// 使用filter方法过滤学生信息
					this.classStuInfo = this.originalClassStuInfo.filter(item => {
						return item.name.includes(value);
					});
				} else {
					// 如果搜索关键字为空，则显示所有学生信息
					this.classStuInfo = [...this.originalClassStuInfo];
				}
			},
			actionsClick(e, index) {
				switch (e) {
					case "复制学号":
						uni.setClipboardData({
							data: this.originalClassStuInfo[index].student_id
						});
						break;
				}
			}
		}
	}
</script>

<style scoped>
	.card-actions {
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items: center;
		height: 45px;
		border-top: 1px #eee solid;
	}

	.card-actions-item {
		display: flex;
		align-items: center;
	}
</style>