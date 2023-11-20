<template>
	<view>
		<uni-card :title="i18N.cardTitle" thumbnail="" extra="beta" note="Tips">
			<uni-easyinput :maxlength="1000" type="textarea" autoHeight v-model="title"
				:placeholder="i18N.cardPlaceholder"></uni-easyinput>
			<button class="mt-10" type="primary" @tap="query">{{i18N.cardQueryButton}}</button>
			<view class="mt-10 flex flex-column " style="">
				<view class="flex flex-row" style="align-items: center;">
					<switch :checked="automaticQuery" @change="switchAutomaticQueryChange"></switch>
					<text>{{i18N.cardSwitchAutomaticQuery}}</text>
				</view>
				<view class="flex flex-row mt-10" style="align-items: center;">
					<switch :checked="camouflageMode" @change="switchCamouflageModeChange"></switch>
					<text>{{i18N.cardSwitchCamouflageMode}}</text>
				</view>
			</view>
		</uni-card>
		<view>
			<view :class="resultsClass" v-for="(item,index) in results" :key="index" class="answer-card">
				<text>{{i18N.resultsQuestion}}</text>{{item.question}}<br>
				<text>{{i18N.resultsAnswer}}</text>{{item.answer}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				preloadParm: {
					"enncy_query_token": '8483051e0e8b434293f793e7975d6243',
					"icodef_query_api_key": 'CNDf8XFIjro8AD2t'
				},

				title: '',
				i18N: {
					"cardTitle": "在线搜索题目",
					"cardPlaceholder": "请输入题目进行搜索，不要缺失题目部分，暂不支持使用拍照搜索。",
					"cardQueryButton": "搜索上方题目",
					"cardSwitchAutomaticQuery": "自动粘贴并查询",
					"cardSwitchCamouflageMode": "伪装模式",
					"resultsQuestion": "题目：",
					"resultsAnswer": "答案："
				},

				results: [{
					"question": "",
					"answer": ""
				}],
				resultsClass: "",
				automaticQuery: false,
				camouflageMode: false
			}
		},
		onLoad() {
			this.checkHttps()
		},
		methods: {
			switchAutomaticQueryChange(e) {
				this.automaticQuery = e.detail.value
			},
			switchCamouflageModeChange(e) {
				this.camouflageMode = e.detail.value
				if (this.camouflageMode) {
					uni.showModal({
						title: '提示',
						content: '伪装模式会隐藏所有UI界面与与题库相关的字眼，适用于现场考试，该功能目前用于测试和学习使用。',
						showCancel: false,
						complete() {}
					});
				}

				this.i18N = {
					"cardTitle": "",
					"cardPlaceholder": "",
					"cardQueryButton": "——",
					"cardSwitchAutomaticQuery": "",
					"cardSwitchCamouflageMode": "",
					"resultsQuestion": "",
					"resultsAnswer": ""
				}

				this.resultsClass = "results-camouflage"
			},
			getClipboard() {
				let that = this;
				navigator.clipboard.readText()
					.then(text => {
						console.log('剪贴板内容:', text);
						this.title = text
						uni.showToast({
							title: '粘贴成功！',
							success() {
								that.query_enncy_api();
							}
						});
					})
					.catch(err => {
						console.error('无法读取剪贴板内容:', err);
						uni.showModal({
							title: '无法读取剪贴板内容',
							content: err,
							showCancel: false,
							cancelText: 'CANCEL',
							confirmText: 'OK'
						});
					});
				uni.getClipboard({
					complete: e => {
						console.log(e)
					}
				})
			},
			checkHttps() {
				// 获取当前协议
				const currentProtocol = window.location.protocol;
				// 获取当前主机名
				const currentHostname = window.location.hostname;

				// 判断是否为非localhost并且不是HTTPS
				if (currentHostname !== 'localhost' && currentProtocol !== 'https:') {
					uni.showLoading({
						title: '重定向中，请稍等。',
						mask: true
					});
					setTimeout(e => {
						// 重定向到HTTPS
						window.location.href = `https:${window.location.href.substring(currentProtocol.length)}`;
					}, 2000);
				}
			},
			query() {
				if (this.automaticQuery) {
					this.getClipboard()
				} else {
					this.query_enncy_api()
				}
			},
			query_enncy_api() {
				const encodedTitle = encodeURIComponent(this.title)
				uni.request({
					url: "https://tk.enncy.cn/query?title=" + encodedTitle +
						"&token=" + this.preloadParm.enncy_query_token + "&more=true",
					method: 'GET',
					data: {},
					success: res => {
						this.results = res.data.data.results
						if (res.data.code === 0) {
							uni.showModal({
								title: '题库1',
								content: res.data.message,
								showCancel: false
							});
						}
					},
					fail: () => {
						uni.showModal({
							content: '很抱歉，维护中，请过段时间再使用。',
							showCancel: false
						});
					},
					complete: (e) => {
						console.group("enncy querying...")
						console.log(e.data)
						if (e.data.code === 0 && e.data.message == "非常抱歉，题目搜索不到。") {
							console.log("Try using the next question api...")
							// this.query_icodef_api()
							this.query_jszkk_api();
						}
						console.groupEnd()
					}
				});
			},
			query_icodef_api() {
				// uni.request({
				// 	url: '/api' + this.title + "?token=" + this.preloadParm
				// 		.icodef_query_api_key,
				// 	method: 'GET',
				// 	data: {},
				// 	success: res => {
				// 		if (res.data.code == "-1") {
				// 			uni.showModal({
				// 				title: "题库2",
				// 				content: res.data.msg,
				// 				showCancel: false
				// 			});
				// 		}
				// 		if (res.data.code === 0 && res.data.msg === "success") {
				// 			res.data.correct.forEach(item => {
				// 				const resultItem = {
				// 					"question": res.data.question,
				// 					"answer": item.content
				// 				};
				// 				this.results.push(resultItem);
				// 			});
				// 		}
				// 	},
				// 	fail: () => {
				// 		uni.showModal({
				// 			content: '很抱歉，维护中，请过段时间再使用。',
				// 			showCancel: false
				// 		});
				// 	},
				// 	complete: (e) => {
				// 		console.group("icodef querying...")
				// 		console.log(e)
				// 		console.groupEnd()
				// 	}
				// });
			},
			query_jszkk_api() {
				uni.request({
					url: "https://study.jszkk.com/api/open/seek?q=" + this.title,
					method: 'GET',
					data: {},
					success: res => {
						if (res.data.code === 200) {
							this.results = [{
								"question": res.data.data.content,
								"answer": res.data.data.answer
							}]
							console.log(this.results)
						}
						if (res.data.code === 201 && res.data.msg === "没找到到答案，登陆后可以提交该题的答案嗷。") {
							uni.showModal({
								title: '题库3',
								content: res.data.msg,
								showCancel: false
							});
						}
					},
					fail: () => {
						uni.showModal({
							content: '很抱歉，维护中，请过段时间再使用。',
							showCancel: false
						});
					},
					complete: (e) => {
						console.group("enncy querying...")
						console.log(e.data)
						if (e.data.code === 0 && e.data.message == "非常抱歉，题目搜索不到。") {
							console.log("Try using the next question api...")
							this.query_jszkk_api();
						}
						console.groupEnd()
					}
				});
			}
		}
	}
</script>

<style scoped>
	.answer-card {
		box-shadow: rgba(0, 0, 0, 0.08) 0px 0px 3px 1px;
		padding: 20px;
		margin: 15px;
		line-height: 35px;
	}

	.results-camouflage {
		color: rgba(0, 0, 0, 0.05);
		transition: .5s all;
	}

	.results-camouflage:hover {
		transition: .5s all;
		color: rgba(0, 0, 0, 0.5);
	}
</style>