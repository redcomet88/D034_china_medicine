# D034 vue+django 中医知识图谱推荐问答系统 【 推荐算法+知识图谱+检索式中医问答 】vue+python前后端分离架构，neo4j图数据，界面美观大

>完整项目收费，可联系QQ: 81040295 微信: mmdsj186011 注明从github来的，谢谢！
也可以关注我的B站： 麦麦大数据 https://space.bilibili.com/1583208775
>关注B站，有好处！

## 🗣简单介绍
编号: D034
核心功能：
🌿 推荐算法+知识图谱+检索式中医问答
🌿 vue+python前后端分离架构，neo4j图数据，界面美观大方，适合展示
🌿  多种可视化图形分析、textrank+tfidf+主题词分析
## 📺视频
[video(video-AHHicrkO-1745713853156)(type-bilibili)(url-https://player.bilibili.com/player.html?aid=114402024035709)(image-https://i-blog.csdnimg.cn/img_convert/5d11394443703bd23fc10e388313e4b4.jpeg)(title-vue+django知识图谱中医推荐问答系统+推荐+可视化+neo4j图谱)]
## 🧬实现思路
技术架构：Vue+Django+neo4j+mysql
数据来源：从百度文库购买了一些方剂的文件，我们自己整理成了一个excel，数据整理比较花时间的，因为我们需要通过导入的方式来快速对方剂和药材关系进行存储。
药材数据可以通过爬取中药相关网站
## 1 技术选择
语言与框架: Vue、Python3.8、Django 等
数据库: MySQL5.7、Neo4j3.5   (双数据库，neo4j主要存储中医知识图谱并且为可视化和问答提供数据)
关键技术: d3js（图谱）、echarts、pandas（数据处理）等
问答: 基于LTP模型+图谱检索
本系统是一个基于Vue+Django构建的中医知识图谱推荐问答系统，旨在为用户提供专业的中医知识查询与推荐服务。系统核心功能包括中医问答、推荐算法、知识图谱可视化以及数据管理等模块。主要功能有：中医问答模块，支持检索式问答，为用户提供准确的中医知识；推荐算法模块，结合TextRank、TF-IDF和主题词分析，向用户推荐相关的药材、方剂和医疗知识；知识图谱模块，通过可视化图形展示药材与方剂之间的关系；数据管理模块，负责药材、小类、中药材等数据的存储与管理，确保系统功能的全面性和准确性。
## 2 功能架构
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/d12bce476f41417eb7544f75d2e7e53e.png)
该系统采用Vue+Django的前后端分离架构模式，前端通过Vue.js进行界面开发，结合ECharts等可视化组件展示知识图谱和数据分析结果；后端基于Django框架，利用Python的强大生态系统处理业务逻辑，并通过RESTful API为前端提供数据支持。系统采用Neo4j图数据库存储复杂的中医知识关系，结合MySQL关系型数据库进行补充数据存储。系统还具备数据爬虫模块，负责从中药相关网站抓取药材数据，并通过数据处理模块将其导入到数据库中，为系统提供数据支撑。此外，系统通过推荐算法与知识图谱相结合，为用户提供更加智能化和个性化的问答服务。
功能模块图如下：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/b479c5f01078472f88abbb34eac6eb87.png)
## 3 功能截图
- 知识图谱可视化控件(d3.js)集成
- Python开发的Django端与neo4j的交互，并且给前端提供封装好的数据（模糊搜索查询接口、这里两种知识图谱可视化要求的json数据不同，需要分开开发）默认一次显示50个药方，已实现模糊搜索接口，d3js 力导向图方式的可视化
- Neo4j 按照某个属性来搜索, 后台对应不同的方法即可
- 中药数据爬虫
1. 读取 http://www.zhongyoo.com/name/ 网中药药材信息;
2. 爬取图片;
3. 选择需要存入数据库的列，然后进行数据清洗，重新设置列名称，存入数据库中。
- 中药数据可视化与知识图谱
- 登录与注册
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/a356d364f16948f0b61a0d767ef9d390.png)

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/09051e5540b44a32a32cf9cfea69d3ac.png)
- 主页： 轮播图、中药方剂信息卡片展示、两种协同过滤推荐算法的中药方剂推荐
- 上方是一个轮播图，展示中医中药相关的图片
- 轮播图的下方是中医中药方剂的推荐卡片
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/d340a1cab1ca4b0e833d624034e7300d.png)最新方剂展示卡片，卡片展示方剂图片、名称、来源的典籍、类型、功用、主治症候，还有药方的构成![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/78a5833ea8d542c5a4e6f78e98d4cc48.png) 
推荐效果，利用协同过滤算法
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/1f7838a8070c4e71883bd3f3f3d3e328.png)
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/4f6ba539f2474d5ba356394bab9ed78c.png)
- 搜索方剂：模糊搜索方剂，展示信息卡片
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/7ce3aefa57134cd7b565114a7199d39f.png)
- 搜索药材：模糊搜索药材，展示信息卡片
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/c57e160f51a74ecf8bd66a00654095b9.png)
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/34fdc7d0d9d046d48a9317db09a5ff4c.png)
- 数据可视化大屏：中药方剂、药材的可视化分析，主要用echarts、d3.js的技术实现多维度分析
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/2904c64e272b41d9a7299c213bc2b5fb.png)
- 关键词分析、主题词+textrank+tfidf方法
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/baa0c619324d42f287f7bd468791f822.png)
- 词云分析：实现一个中药方剂的【主治症候】的词云
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/442d9c495f9a4364ae90ce5d6e4c4ace.png)
- 基于dj.js的知识图谱： 支持方剂名称、来源典籍、主治症候 三种类型的模糊查询与可视化
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/52dbdb5f6d954d76bb3899909e504018.png)
- 中医问答：基于LTP+检索式问答，实现方剂的配伍、治疗问题的回答。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/770195bb32bb4c8bae89c55e301a9d8e.png)
- 设置功能（修改用户信息、修改密码）
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/7d6a201eeed744f48425f67c5beaa9c0.png)
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/df16a83d655143d6832bb794a7625710.png)

## 代码
```python
lass NeoViewSet(CustomModelViewSet):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.driver = None
        self.session = None


    def dispatch(self, request, *args, **kwargs):
        # 创建数据库连接和会话
        self.driver = driver
        self.session = self.driver.session()

        # 处理请求
        response = super().dispatch(request, *args, **kwargs)

        # 关闭会话和数据库连接
        self.session.close()
        self.driver.close()

        return response

    # 知识图谱的查询接口
    @action(methods=['get'], detail=False, url_path="getMKG")
    def query_by_name(self, request):
        name = self.request.query_params.get('name')
        stype = self.request.query_params.get('stype')

        # 测试模糊搜索
        nodes, relationships = self.session.read_transaction(read_medicine, name, stype)
        graph = dict(graph=dict(nodes=nodes, relationships=relationships))
        data = []
        data.append(graph)
        result = dict(data=data)
        results = []
        results.append(result)

        driver.session().close()

        return APIResponse(data=dict(results=results))
```
