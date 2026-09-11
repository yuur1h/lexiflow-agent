# LexiFlow Agent

**法律领域工具调用与多步推理 · 从问题规划到执行反馈**

以 APIWeaver 为主要学习与扩展入口，研究实体识别、任务分解、接口调用、代码执行和错误反馈如何组成可追踪的问答流程。

> 基于 [MetaGLM/LawGLM](https://github.com/MetaGLM/LawGLM) 的个人复现与扩展分支。保留原始竞赛方案合集；当前完成项目命名、首页与导航整理，尚未完成端到端复现。[来源记录](UPSTREAM.md) · [原始项目说明](README.upstream.md)

## 主要流程：APIWeaver

```text
用户问题 → 实体识别与规范化 → 连续查询 / 结构化规划
                                         ↓
                                API 调用与代码执行
                                         ↓
                                报错反馈与修正
                                         ↓
                                  执行历史汇总 → 答案
```

## 方案导航

| 入口 | 主要学习内容 |
| --- | --- |
| [APIWeaver](APIWeaver-lawGLM/README.md) | 主入口：规划、接口文档利用、执行反馈与纠错 |
| [Vinlic](Vinlic-lawGLM/README.md) | Function Calling 与 Planner / CodeAct 方案比较 |
| [LegalHi](LegalHi-LawGLM/README.md) | 意图分类、问题改写、结果判断与反思 |
| [其他竞赛方案](README.upstream.md) | 完整团队列表、原作者与赛事背景 |

## 复现入口

```bash
git clone https://github.com/yuur1h/lexiflow-agent.git
cd lexiflow-agent/APIWeaver-lawGLM
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

后续按照 [APIWeaver 运行说明](APIWeaver-lawGLM/README.md) 配置 IPython kernel、模型密钥及比赛数据接口，再运行 `app/run_with_process.py`。可以先阅读 [演示 Notebook](APIWeaver-lawGLM/app/simple_demo.ipynb)。

旧比赛接口权限和可用性尚未核验；安装依赖不代表能够完整运行。不要把真实密钥写入版本控制。该方案包含生成代码执行，联网复现前需检查执行环境与接口配置。

## 后续开发计划

以下均为待办：

- [ ] 核验模型和数据接口，记录可复现的环境配置
- [ ] 用本地样例 API 替代不可用的比赛服务
- [ ] 增加工具参数校验和调用次数预算
- [ ] 记录工具成功率、任务完成率、延迟与费用
- [ ] 建立错误类型与恢复策略的对比评测

## 来源与许可

原始项目由 MetaGLM 汇总，具体方案属于相应团队；APIWeaver 由 [MeiPixel](https://github.com/MeiPixel) 贡献。原作者署名、历史及子目录文档保持保留。

默认使用 [Apache 2.0](LICENSE)，子目录另有声明时按其声明执行。原竞赛排名仅描述上游团队成果，不代表本分支维护者的参赛或获奖经历。[完整来源记录](UPSTREAM.md)。
