---
title: "腾讯面试官怒怼：“连 MCP 协议都没玩过，还敢在简历上写精通 Agent 开发？”，只会调包的我懵了..."
author: "小林哥"
site: "Weixin Official Accounts Platform"
source: "https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247554551&idx=2&sn=804b1b7e5474cf41f77d0d572f876181&chksm=f98d515dcefad84bd54c73f874d1b357667e2c9389f172e8926535da1ba23b3a4eeb0227b49d&scene=178&cur_album_id=4404340926102421504&search_click_id="
domain: "mp.weixin.qq.com"
word_count: 1923
---

在小说阅读器读本章

去阅读

大家好，我是小林。

今天我们来学习这一题读者跟我反馈的腾讯的面试真题！

「 **你知道什么是 MCP 协议吗？** 」

### 简要回答

MCP是Anthropic在2024年底推出的Model Context Protocol，本质上是想为AI应用建立一套标准化的通信协议。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/zLRM1IicjS8jYp25b7a8bJB0WdTGZo4dqYR5KC8hHzqdeKdzwv0Upicicv3mB6xDZ4iaumqXshj6V2H2YtAchchY5Q3iaS74T6j8PYww2JSGBly4/640?wx_fmt=png&from=appmsg)

它要解决的核心问题是，现在大模型和各种外部工具、数据源之间的对接都是各自为政的，每对接一个新系统就得写一套适配代码，特别碎片化。

MCP就像是给AI生态定义了一套"USB接口标准"， **让模型、工具、数据库之间能够通过统一的协议来交互** ，这样开发者就不用重复造轮子，整个生态的互操作性也会大大提升。

### 详细回答

我先说说为什么会有MCP这个协议出现，这样能更好地理解它的价值。

咱们现在做AI应用，特别是Agent类的应用，经常需要让大模型去调用各种外部工具，比如搜索引擎、数据库、API接口等等。但问题是，每家大模型厂商、每个工具提供方都有自己的一套接口规范和数据格式。

比如OpenAI有自己的Function Calling格式，Claude有自己的Tool Use格式，Google的Gemini又是另一套。这就导致我们在对接不同系统时，要写大量的胶水代码和适配层，非常繁琐，而且维护成本也很高。

![](https://mmbiz.qpic.cn/mmbiz_png/zLRM1IicjS8gdZp5iaB9VLawV1wicbbyTrFEGXZ0twr7JoicP6PMRrAsSzOXlV7O7Ml1tW452pLibgS6Z8C0G1OtjWibqPDxARibRIwF0akmxPAg9M/640?wx_fmt=png&from=appmsg)

MCP就是在这个背景下被Anthropic提出来的。它的全称是Model Context Protocol，翻译过来就是"模型上下文协议"。

这个名字其实挺有讲究的，"上下文"这个词强调的是，MCP不仅仅关注单次的工具调用，更关注在整个对话或任务执行过程中，如何持续、稳定地在模型和外部资源之间传递信息。可以把它理解成AI领域的HTTP协议，或者说是给AI应用定义的一套"通信规范"。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/zLRM1IicjS8glTKopu9lMqKibdHiaNibsxW67icgxj9zuTMRaw4pZGkXECPdXwtlOyY2nNLaia5npSPmvG56zXlokjywd5bQSabavexoqCXUywDwU/640?wx_fmt=png&from=appmsg)

具体来说，MCP定义了几个核心的概念和通信流程。首先是Server和Client的架构：

![](https://mmbiz.qpic.cn/sz_mmbiz_png/zLRM1IicjS8jtibaJ3ryRgrpibuNJz6GW1PjY8ic5l0U6mpx9F2lGLf7tNpXXF4dXa5ZE5DPSEbv1MqBaCicnnISQRu5wnI59H7FnZjICqYEFeso/640?wx_fmt=png&from=appmsg)

- Server端可以是各种资源提供方，比如你的企业数据库、文件系统、API服务等等，它们通过实现MCP协议来暴露自己的能力。
- Client端通常就是AI应用或者模型本身，它通过MCP协议来发现和调用这些资源。这种设计的好处是解耦，资源提供方不需要关心具体是哪个模型在使用，模型也不需要为每种资源写专门的适配代码。

MCP协议里有几个重要的概念需要解释一下。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/zLRM1IicjS8jn7ETpmj5UM8H9FucRicaY2gWIHOZPdicdUnTFkSUEO9kNSMUrNWxibeibw3LEz0y7BU1lv1icZMoESg6M8qjYHRjPRJ6tRCBaxFXg/640?wx_fmt=png&from=appmsg)

- 第一个是Resources，也就是资源，比如文档、数据库记录、API端点等等，MCP通过统一的方式来描述这些资源的元信息和访问方式。
- 第二个是Tools，也就是工具，这个和我们之前说的Function Call里的函数是类似的概念，但MCP对工具的定义更加标准化，包括工具名称、描述、参数schema、返回值格式等等都有明确的规范。
- 第三个是Prompts，MCP甚至允许Server端提供预定义的提示词模板，这样Client可以直接使用这些模板来构造请求。

我举个实际的例子来说明MCP是怎么工作的。假设你有一个企业内部的数据库，里面存着客户信息、订单数据等等，你想让AI助手能够查询这些数据。

在没有MCP之前，你需要写一套专门的后端服务，定义API接口，然后在AI应用里写代码去调用这些接口，如果换一个模型或者换一个工具，可能又得重新适配。

![](https://mmbiz.qpic.cn/mmbiz_png/zLRM1IicjS8j9akkdciahnPsyAtBic0fnrUU7HUjs226eGxrxmhJM3KxeGTgx4MradcBceDUTK57icHokicUlpuAHicRBfMRn3mZGRkLdrpDsgpPY/640?wx_fmt=png&from=appmsg)

但如果用MCP，你只需要实现一个 **MCP Server** ，这个Server会声明自己提供了哪些资源和工具。代码实现起来大概是这样的逻辑：

```
# MCP Server端实现（伪代码示意）
class DatabaseMCPServer:
    def list_resources(self):
        # 声明这个Server提供的资源
        return [
            {
                "uri": "database://customers",
                "name": "客户数据库",
                "description": "包含所有客户的基本信息",
                "mimeType": "application/sql"
            }
        ]

    def list_tools(self):
        # 声明这个Server提供的工具
        return [
            {
                "name": "query_customers",
                "description": "查询客户信息",
                "inputSchema": {
                    "type": "object",
                    "properties": {
                        "customer_id": {"type": "string"},
                        "fields": {"type": "array"}
                    }
                }
            }
        ]

    def call_tool(self, tool_name, arguments):
        # 执行具体的工具调用
        if tool_name == "query_customers":
            return self.query_database(arguments)
```

然后在Client端，也就是你的AI应用里，你只需要连接到这个MCP Server，就可以自动发现它提供的所有能力，然后让模型去调用：

```
# MCP Client端使用（伪代码示意）
client = MCPClient("database-server")

# 自动发现Server提供的工具
available_tools = client.list_tools()

# 让AI模型知道有这些工具可用
response = model.generate(
    prompt="查询客户ID为12345的订单历史",
    tools=available_tools
)

# 如果模型决定调用工具
if response.tool_calls:
    for tool_call in response.tool_calls:
        result = client.call_tool(
            tool_call.name,
            tool_call.arguments
        )
```

这里最关键的价值在于标准化。因为所有实现了MCP协议的Server，它们暴露工具和资源的方式都是统一的，Client端不需要为每个Server写专门的适配代码。

而且如果未来你想换一个模型，比如从Claude换到GPT-4，只要这个模型支持MCP协议，你的整个后端基础设施都不需要改动，这就大大降低了系统的耦合度和维护成本。

MCP还有一个很重要的特性是它 **支持双向通信** 。不仅仅是Client可以主动请求Server，Server也可以主动推送信息给Client，比如数据更新通知、状态变化等等。这对于需要实时交互的场景特别有用。而且MCP设计了完善的错误处理机制、权限控制机制，甚至考虑了多轮对话中的状态管理，可以说是一个相对完整的协议体系。

从架构设计的角度看， **MCP体现的是一种面向协议编程的思想** 。它不是要替代现有的Function Call或者Tool Use这些具体实现，而是在它们之上定义了一层抽象，让不同的实现之间能够互通。

这种思路其实在软件工程里很常见，比如JDBC让Java程序可以用统一的方式访问不同的数据库，MCP也是想达到类似的效果。

💪面试突击资源推荐：  
✅小林图解网站： [xiaolincoding.com](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247539587&idx=1&sn=aeba78d225c15a25cb00a7da6b79a201&scene=21#wechat_redirect)  
✅刷题闯关+模拟面试： 牛面Offer面试刷题小程序

✅后端训练营： [Java/Go 后端训练营，出大成果了！](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247553487&idx=2&sn=dbb10ac564a5c9c7abcfcfc845ed37fe&scene=21&token=1176637830&lang=zh_CN#wechat_redirect)  
✅大模型训练营： [转行去做大模型开发了！](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247553560&idx=2&sn=1766aec675f13c9841fb265d69ab40b0&scene=21#wechat_redirect)  
✅做项目： [AI Agent 项目](https://mp.weixin.qq.com/s?__biz=MzUxODAzNDg4NQ==&mid=2247553574&idx=2&sn=4f2529fafb96f6111792f5257733d49d&scene=21#wechat_redirect)

Read more

继续滑动看下一个

小林coding

向上滑动看下一个

Got It

Scan with Weixin to  
use this Mini Program

: ， ， ， ， ， ， ， ， ， ， ， ，. Video Mini Program Like ，轻点两下取消赞 Wow ，轻点两下取消在看