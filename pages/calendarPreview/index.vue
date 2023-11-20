<template>
	<view>
		<center>
			<table cellpadding="0" cellspacing="0" class="logo_tab">
				<tr>
					<td class="logo"></td>
				</tr>
			</table>
			<table cellpadding="0" cellspacing="0" class="content_tab">
				<tr>
					<td class="content">
						<div id="title">
							<table cellpadding="0" cellspacing="0">
								<tr>
									<td nowrap="nowrap">
										<div>
											<uni-section class="mb-10" title="2023 秋" sub-title="行政班课表:
												23级软工（专升本）2班" type="line"></uni-section>
										</div>
									</td>
								</tr>
							</table>
						</div>

						<table width="92%" border="0" cellspacing="0" cellpadding="0">
							<tr>
								<td align="right"> 班级人数：56</td>
							</tr>
						</table>

						<table id="timetable" cellspacing="0" cellpadding="0" class="infolist_hr">
							<tr class="infolist_hr_week">
								<th>&nbsp;</th>
								<th nowrap>周一</th>
								<th nowrap>周二</th>
								<th nowrap>周三</th>
								<th nowrap>周四</th>
								<th nowrap>周五</th>
								<th nowrap>周六</th>
								<th nowrap>周日</th>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第1节
									<br>
									08:20
									<br>
									┆
									<br>
									09:05
								</th>
								<td id="1-1" class="center">&nbsp;</td>
								<td id="2-1" class="center">
									&lt;&lt;数据库系统原理&gt;&gt;;7
									<br>
									科学院(东)202
									<br>
									辛勤芳
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="3-1" class="center">&nbsp;</td>
								<td id="4-1" class="center">&nbsp;</td>
								<td id="5-1" class="center">
									&lt;&lt;Java程序设计&gt;&gt;;6
									<br>
									科学院(西)207
									<br>
									吴淑梅
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="6-1" class="center">&nbsp;</td>
								<td id="7-1" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第2节
									<br>
									09:15
									<br>
									┆
									<br>
									10:00
								</th>
								<td id="1-2" class="center">&nbsp;</td>
								<td id="2-2" class="center">
									&lt;&lt;数据库系统原理&gt;&gt;;7
									<br>
									科学院(东)202
									<br>
									辛勤芳
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="3-2" class="center">&nbsp;</td>
								<td id="4-2" class="center">&nbsp;</td>
								<td id="5-2" class="center">
									&lt;&lt;Java程序设计&gt;&gt;;6
									<br>
									科学院(西)207
									<br>
									吴淑梅
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="6-2" class="center">&nbsp;</td>
								<td id="7-2" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第3节
									<br>
									10:20
									<br>
									┆
									<br>
									11:05
								</th>
								<td id="1-3" class="center">
									&lt;&lt;原型设计&gt;&gt;;6
									<br>
									科学院(东)202
									<br>
									薛芳
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="2-3" class="center">&nbsp;</td>
								<td id="3-3" class="center">
									&lt;&lt;计算机组成原理&gt;&gt;;8
									<br>
									高盖教学楼302
									<br>
									周宓
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="4-3" class="center">&nbsp;</td>
								<td id="5-3" class="center">&nbsp;</td>
								<td id="6-3" class="center">&nbsp;</td>
								<td id="7-3" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第4节
									<br>
									11:15
									<br>
									┆
									<br>
									12:00
								</th>
								<td id="1-4" class="center">
									&lt;&lt;原型设计&gt;&gt;;6
									<br>
									科学院(东)202
									<br>
									薛芳
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="2-4" class="center">&nbsp;</td>
								<td id="3-4" class="center">
									&lt;&lt;计算机组成原理&gt;&gt;;8
									<br>
									高盖教学楼302
									<br>
									周宓
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="4-4" class="center">&nbsp;</td>
								<td id="5-4" class="center">&nbsp;</td>
								<td id="6-4" class="center">&nbsp;</td>
								<td id="7-4" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									午间1节
									<br>
									12:20
									<br>
									┆
									<br>
									13:05
								</th>
								<td id="1-5" class="center">&nbsp;</td>
								<td id="2-5" class="center">&nbsp;</td>
								<td id="3-5" class="center">&nbsp;</td>
								<td id="4-5" class="center">&nbsp;</td>
								<td id="5-5" class="center">&nbsp;</td>
								<td id="6-5" class="center">&nbsp;</td>
								<td id="7-5" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									午间2节
									<br>
									13:15
									<br>
									┆
									<br>
									14:00
								</th>
								<td id="1-6" class="center">&nbsp;</td>
								<td id="2-6" class="center">&nbsp;</td>
								<td id="3-6" class="center">&nbsp;</td>
								<td id="4-6" class="center">&nbsp;</td>
								<td id="5-6" class="center">&nbsp;</td>
								<td id="6-6" class="center">&nbsp;</td>
								<td id="7-6" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第5节
									<br>
									14:30
									<br>
									┆
									<br>
									15:15
								</th>
								<td id="1-7" class="center">
									&lt;&lt;原型设计&gt;&gt;;6
									<br>
									科学院(东)202
									<br>
									薛芳
									<br>
									3-18双
									<br>
									讲课学时
								</td>
								<td id="2-7" class="center">
									&lt;&lt;数据库系统原理&gt;&gt;;7
									<br>
									科学院(东)202
									<br>
									辛勤芳
									<br>
									3-18双
									<br>
									讲课学时
								</td>
								<td id="3-7" class="center">
									&lt;&lt;计算机组成原理&gt;&gt;;8
									<br>
									科学院(东)202
									<br>
									周宓
									<br>
									3-17周单
									<br>
									讲课学时
								</td>
								<td id="4-7" class="center">&nbsp;</td>
								<td id="5-7" class="center">
									&lt;&lt;Java程序设计&gt;&gt;;6
									<br>
									科学院(西)207
									<br>
									吴淑梅
									<br>
									3-17周单
									<br>
									讲课学时
								</td>
								<td id="6-7" class="center">&nbsp;</td>
								<td id="7-7" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第6节
									<br>
									15:25
									<br>
									┆
									<br>
									16:10
								</th>
								<td id="1-8" class="center">
									&lt;&lt;原型设计&gt;&gt;;6
									<br>
									科学院(东)202
									<br>
									薛芳
									<br>
									3-18双
									<br>
									讲课学时
								</td>
								<td id="2-8" class="center">
									&lt;&lt;数据库系统原理&gt;&gt;;7
									<br>
									科学院(东)202
									<br>
									辛勤芳
									<br>
									3-18双
									<br>
									讲课学时
								</td>
								<td id="3-8" class="center">
									&lt;&lt;计算机组成原理&gt;&gt;;8
									<br>
									科学院(东)202
									<br>
									周宓
									<br>
									3-17周单
									<br>
									讲课学时
								</td>
								<td id="4-8" class="center">&nbsp;</td>
								<td id="5-8" class="center">
									&lt;&lt;Java程序设计&gt;&gt;;6
									<br>
									科学院(西)207
									<br>
									吴淑梅
									<br>
									3-17周单
									<br>
									讲课学时
								</td>
								<td id="6-8" class="center">&nbsp;</td>
								<td id="7-8" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第7节
									<br>
									16:30
									<br>
									┆
									<br>
									17:15
								</th>
								<td id="1-9" class="center">&nbsp;</td>
								<td id="2-9" class="center">
									&lt;&lt;大学生职业生涯规划&gt;&gt;;8
									<br>
									外文院401-402
									<br>
									王文福
									<br>
									9-16周
									<br>
									讲课学时
								</td>
								<td id="3-9" class="center">
									&lt;&lt;形势与政策(1)&gt;&gt;;23
									<br>
									俊秀文艺122
									<br>
									洪少春
									<br>
									第11周
									<br>
									讲课学时
								</td>
								<td id="4-9" class="center">&nbsp;</td>
								<td id="5-9" class="center">&nbsp;</td>
								<td id="6-9" class="center">&nbsp;</td>
								<td id="7-9" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第8节
									<br>
									17:25
									<br>
									┆
									<br>
									18:10
								</th>
								<td id="1-10" class="center">&nbsp;</td>
								<td id="2-10" class="center">
									&lt;&lt;大学生职业生涯规划&gt;&gt;;8
									<br>
									外文院401-402
									<br>
									王文福
									<br>
									9-16周
									<br>
									讲课学时
								</td>
								<td id="3-10" class="center">
									&lt;&lt;形势与政策(1)&gt;&gt;;23
									<br>
									俊秀文艺122
									<br>
									洪少春
									<br>
									第11周
									<br>
									讲课学时
								</td>
								<td id="4-10" class="center">&nbsp;</td>
								<td id="5-10" class="center">&nbsp;</td>
								<td id="6-10" class="center">&nbsp;</td>
								<td id="7-10" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第9节
									<br>
									19:00
									<br>
									┆
									<br>
									19:45
								</th>
								<td id="1-11" class="center">&nbsp;</td>
								<td id="2-11" class="center">
									&lt;&lt;线性代数&gt;&gt;;1
									<br>
									高盖教学楼302
									<br>
									林让起
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="3-11" class="center">
									&lt;&lt;形势与政策(1)&gt;&gt;;23
									<br>
									俊秀文艺122
									<br>
									洪少春
									<br>
									第6周
									<br>
									讲课学时
								</td>
								<td id="4-11" class="center">&nbsp;</td>
								<td id="5-11" class="center">&nbsp;</td>
								<td id="6-11" class="center">&nbsp;</td>
								<td id="7-11" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第10节
									<br>
									19:55
									<br>
									┆
									<br>
									20:40
								</th>
								<td id="1-12" class="center">&nbsp;</td>
								<td id="2-12" class="center">
									&lt;&lt;线性代数&gt;&gt;;1
									<br>
									高盖教学楼302
									<br>
									林让起
									<br>
									3-18周
									<br>
									讲课学时
								</td>
								<td id="3-12" class="center">
									&lt;&lt;形势与政策(1)&gt;&gt;;23
									<br>
									俊秀文艺122
									<br>
									洪少春
									<br>
									第6周
									<br>
									讲课学时
								</td>
								<td id="4-12" class="center">&nbsp;</td>
								<td id="5-12" class="center">&nbsp;</td>
								<td id="6-12" class="center">&nbsp;</td>
								<td id="7-12" class="center">&nbsp;</td>
							</tr>
							<tr class="infolist_hr_common" onMouseOver="javascript:this.className='infolist_hr_current'"
								onMouseOut="javascript:this.className='infolist_hr_common'">
								<th nowrap>
									第11节
									<br>
									20:50
									<br>
									┆
									<br>
									21:35
								</th>
								<td id="1-13" class="center">&nbsp;</td>
								<td id="2-13" class="center">&nbsp;</td>
								<td id="3-13" class="center">&nbsp;</td>
								<td id="4-13" class="center">&nbsp;</td>
								<td id="5-13" class="center">&nbsp;</td>
								<td id="6-13" class="center">&nbsp;</td>
								<td id="7-13" class="center">&nbsp;</td>
							</tr>
						</table>
					</td>
				</tr>
			</table>

			<table cellpadding="0" cellspacing="0" class="foot_tab">
				<tr>
					<td class="foot_left"></td>
					<td class="foot_right"></td>
				</tr>
			</table>
		</center>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style scoped>
	.infolist_hr * {
		border: 1px solid black;
	}

	.infolist_hr_week * {
		transition: 1s all;
		min-width: 5px !important;
	}

	.infolist_hr_week *:hover {
		transition: 1s all;
		min-width: 200px !important;
		min-height: 200px !important;
	}
</style>