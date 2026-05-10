# 面试官：你知道 MCP、Skill、Function Call 这三个的区别吗？

原文链接：<https://xiaolincoding.com>

![](2面试官：你知道%20MCP、Skill、Function%20Call%20这三个的区别吗？/cover.jpg)

面试刷题网站：[xiaolincoding.com](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247507000&idx=1&sn=c045101b45dd70ec37f9b81361b09f14&scene=21#wechat_redirect)

大家好，我是小林。

最近翻后台留言，发现好多朋友都在吐槽：现在后端面试，AI 相关的题目已经成了高频必考点，没提前准备很容易被问懵。

所以我后面计划陆续更新 AI 大模型开发相关的面试题系列，帮大家提前攒好干货、做好储备，面试的时候能从容跟面试官对线。

那么这次就来学习这一题面试真题！

「**你知道 MCP、Skill、Function Call 这三个的区别吗？**」

### 简要回答

这三个概念其实分别处在不同的层次上。

Function Call是大模型调用外部工具的底层技术实现，让模型能够主动发起函数调用。

Skill可以理解为对一组相关Function的业务封装，比如"邮件处理技能"里可能包含发送、查询、删除等多个函数。

而MCP是Anthropic最近推出的模型上下文协议，它本质上是想建立一套标准化的通信规范，让不同的模型、工具和数据源之间能够更顺畅地互通互联。

简单来说，Function Call解决"怎么调"，Skill解决"调什么"，MCP解决"按什么规矩调"。

### 详细回答

> Function Call

我先从最底层的**Function Call**说起吧。Function Call其实是OpenAI在GPT-3.5和GPT-4时代引入的核心能力，它让大模型不再只是一个"聊天机器人"，而是可以主动识别用户意图并调用外部工具的智能体。

![](2面试官：你知道%20MCP、Skill、Function%20Call%20这三个的区别吗？/cover%201.jpg)

具体来说，当我们在调用API时，会在请求里传入一个functions参数，告诉模型现在有哪些可用的工具以及每个工具需要什么参数。

模型理解用户输入后，如果判断需要调用工具，就会返回一个结构化的JSON对象，里面包含函数名和参数值，然后我们的代码再根据这个返回去真正执行那个函数。举个简单的例子：

```text
response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[{"role": "user", "content": "北京今天天气怎么样？"}],
    functions=[{
        "name": "get_weather",
        "description": "获取指定城市的天气信息",
        "parameters": {
            "type": "object",
            "properties": {
                "city": {"type": "string", "description": "城市名称"}
            }
        }
    }]
)
```

这段代码里，模型会意识到用户在问天气，然后返回一个调用`get_weather`函数的指令，参数是`{"city": "北京"}`，接下来我们的后端代码再真正去调天气API拿数据回填给模型。

所以Function Call本质上就是一种"模型输出结构化调用指令"的技术能力。

> Skill

然后我们再往上看**Skill**这个概念。Skill其实是对Function Call做了一层业务化的封装和组织。因为在实际项目中，单个函数的能力太零散了，比如我们要做一个"智能邮件助手"，可能需要"发送邮件"、"查询邮件"、"标记已读"、"删除邮件"等好几个函数配合使用，这时候我们就会**把这些相关的Function打包成一个"邮件处理Skill"**。

![](2面试官：你知道%20MCP、Skill、Function%20Call%20这三个的区别吗？/cover%202.jpg)

这样做的好处是代码组织更清晰，复用性也更强，团队协作的时候也能按Skill来分工。我之前在项目里就是这么干的，会专门建一个skills目录，每个Skill对应一个独立的模块，里面包含这个领域的所有函数定义和实现逻辑。从架构角度看，Skill是Function Call在工程实践中自然演化出来的一种组织形式。

> MCP

最后说说**MCP**，这个概念可能相对新一点。MCP的全称是Model Context Protocol，是Anthropic在2024年底正式推出的一套开放协议标准。

它想解决的核心问题是，现在市面上各家大模型、各种工具、各类数据源之间的对接都是"各自为政"的，开发者要对接不同的系统就得写不同的适配代码，特别麻烦。

![](2面试官：你知道%20MCP、Skill、Function%20Call%20这三个的区别吗？/cover%203.jpg)

MCP就是想通过制定统一的通信协议，让模型和外部资源之间有一套标准化的"握手方式"。打个比方，就像以前每个手机品牌都用自己的充电接口，后来统一成了Type-C接口一样，MCP希望成为AI应用领域的"Type-C"。

具体来说，MCP定义了服务端和客户端之间如何传递上下文、如何声明可用工具、如何返回执行结果等一整套规范。

如果未来MCP真的被广泛采纳，理论上我们用任何支持MCP的模型去对接任何支持MCP的工具或数据库，都不需要再写一堆胶水代码了，直接按协议标准对接就行。

从这个角度看，MCP是站在更高的生态层面去思考问题，它不是要替代Function Call或者Skill，而是要给它们提供一套统一的"交流语言"。

> 三者的关系

总结一下三者的关系：

- Function Call是最基础的技术实现层，解决的是"模型怎么调工具"；
- Skill是工程实践层，解决的是"把哪些工具组合起来对外提供能力"；
- MCP是协议标准层，解决的是"不同系统之间按什么规范来通信"。

它们不是替代关系，而是各自在不同维度上发挥作用，共同支撑起现代AI Agent的架构体系。

💪面试突击资源推荐 ：\
✅Java/Go/C++ 面试刷题： [xiaolincoding.com](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247539587&idx=1&sn=aeba78d225c15a25cb00a7da6b79a201&scene=21#wechat_redirect)\
✅程序员 1 对 1 AI 模拟面试：[niumianoffer.com](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247551748&idx=1&sn=3696af1b110931fa8d6e22390e2a62b4&scene=21#wechat_redirect)\
✅后端训练营：[Java/Go 后端训练营，出大成果了！](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247553487&idx=2&sn=dbb10ac564a5c9c7abcfcfc845ed37fe&scene=21#wechat_redirect)\
✅大模型训练营：[转行去做大模型开发了！](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247553560&idx=2&sn=1766aec675f13c9841fb265d69ab40b0&scene=21#wechat_redirect)\
✅做项目：[AI Agent 项目](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247553574&idx=2&sn=4f2529fafb96f6111792f5257733d49d&scene=21#wechat_redirect)


---

Original 小林coding 小林coding