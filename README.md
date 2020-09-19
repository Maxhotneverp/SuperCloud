# SuperCloud
<pre>
##基础准备资料
	网站
		白皮书
		Twitter
		tegegram
		Github
	基础准备资料-进阶
		项目视频介绍
		三方媒文介绍
			币乎
			Steemit
			区块律动
			金色财经
		商学院资料
			每日制造热点
			玩法操作说明（视频）
			制度优势解析（视频）
		海报图片制作
			项目主题
			项目优势
			项目预期

制度框架
	基本介绍
		一：基本信息
初始总量：3000万（交易及转账代币总量持续减少)
参与者买入扣除10%，卖出亦扣除10% *其中，买入扣除的10%由买入者买入时直接扣除，卖出扣除的10%不为交易者承担计入大盘总流通筹码的定向数据通缩 *其中5%永久销毁，5%进入奖金池

进入奖金池的5%将放大为100%，分为三个奖金池
        1.尾单博弈奖金池：35%
        2.团队持续开发和运营：5%
        3.持币分红奖金池：60% （持币分红奖金池里50%每天分给持币24小时的用户，如遇交易量萎缩，不足每日交易代币数量不足当前流通额5%则将剩余50%回馈至持币分红池子）
	⚠️：此处通缩筹码可选两种方案（ 1、恒量通缩撤池填入2、外围数据填充，直接由生态筹码部分扣除）
        利弊 ：如此处采用方案1，则会形成市场预期价格期许期权，叠加买入，增强市场跟买力度，同时加速⏩筹码销毁力度。暴漏项目方操控资金池的隐患如此处采用方案2，则会给予市场开源层面更多的信心，使其更依赖于智能合约的公信力度，但不会与实际价格数据形成密切关关联

⚠️：此处用SWAP - AMM乘积订单捏合更容易凸显产品的价值
此处最大问题是供给问题，是否弹性供给，如不弹性供给，容易很快进入天花板瓶颈期

##通缩燃烧规则说明
		
每交易一笔将燃烧10%代币
例：某某购买1000枚代币，实际到账900枚代币（其中5%代币=50枚永久销毁，另外5%代币=50枚进入奖金池）
⚠️：其中买入扣除的10%买入者买入时直接扣除，卖出扣除的10%不为交易者承担计入大盘总流通筹码的定向数据通缩 
 
2.每转账一笔也将燃烧10%（其中5%永久销毁，5%进入奖金池）
例：（地址A）尝试转账1000枚代币给 （地址B）
其中5%代币=50 枚代币将被彻底销毁，
另外5%代币=50 枚代币将被转入奖金池;
最后（地址B）将收到900 枚代币。
⚠️：此处有争议，涉及分账户会大幅缩减持币人主动操作信心
			由操作者买单通缩部分
				转账
				买入
			大盘整体通缩部分
				卖出
	代币供给体系说明
		币量供给说明：
SWAP底仓：30000000  
弹性供给仓：无上限！   
		弹性供给仓：
（Z为持币基准持仓数值，P为价格，T为结算时间）
T1 = Z
T2 = Z* {（P2-P1）/ P1} / 10 /30
⚠️：{（P2-P1）/ P1} 部分只取值《=10%部分，溢出部分不计算
			解决预言机问题！
	               尾单博弈
		1. 若当前时间与上次尾单博弈时间的间隔超过 60 分钟，则进行派奖:
当前奖励名单中，最后 1 人可获得奖池中 10% 的代币，除最后 1 人外，其余9位每人可获得
奖池中 2% 的代币
2. 如果此时奖励名单人 数>10 人，则剔除最后10人以外所有地址。

• 初始为 （30000000-  burn）*1/5000 + 3√Supply*1/10
• 任意用户参与尾单博弈时，要求数额增加  :
{（30000000-  burn）*1/5000 + 3√Supply*1/10}*(1+0.02)^X
• 该要求数额的上限是
{（30000000-  burn）*1/5000 + 3√Supply*1/10}*(1+0.02)^X 代币 
<=  
{（30000000-  burn）*1/1000 + 3√Supply*1/10}
• 每次派奖时结束后，要求数额将还原到:
 （30000000-  burn）*1/5000 + 3√Supply*1/10
			此处需灵活折算百分比，数量百分比等于市值百分比？
	              分红要求
		销毁分红
			（30000000-  burn）*1/1500 + 3√Supply*1/10
		弹性供给仓
			单个账户大于（30000000-  burn）*1/1500 + 3√Supply*1/10
部分不享受供给仓供应

项目板块划分与技术实现要求
	其余前端可视化数据参访REV
	代币发行机制
		提供前端可视化数据（弹性供给仓，手动分发，波场无本地预言机）目前共计释放数额、当日发放数额，224小时更新一次
	代币经济模型
		买入销毁
			提供前端可视化数据用户买入销毁筹码，打入可控公钥地址
		卖出销毁
			提供前端可视化数据，手动撤池销毁拉盘
	模式制度玩法
		FOMO博弈单
			提供前端可视化数据（当前博弈单要求最低数量与递增有效数量与最高数量）24小时计算一次
			提供前端可视化数据，当前奖池金额
		持仓分红
			提供前端可视化数据要求最低持仓分红数量，24小时计算一次
	交易载体
		Justswap
	数据清算与数据量化
		根据具体情况实时定论

运营框架体系
	运营载体
		微信
			活跃气氛
			利好解释宣发
			水军打CALL
		telegram
			活跃气氛
			利好解释宣发
			水军打CALL
</pre>
