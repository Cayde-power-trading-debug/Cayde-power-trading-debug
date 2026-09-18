# Chronos-2 Local Weather Prompts

用于指导编程助手部署 **Chronos-2 本地 GPU 预测系统**的中文提示词，覆盖模型下载、HTML 页面、地理范围天气获取及辅助变量自动接入。

**这是提示词与需求文档仓库，不是已经实现的预测软件。** 仓库不包含模型权重、业务数据、天气数据或已验证的部署代码。

## 使用方法

1. 打开 [完整中文提示词](prompts/chronos-2-local-weather.zh-CN.md)。
2. 将“提示词正文”交给能够操作本地文件和终端的编程助手。
3. 由助手检测目标电脑的系统、NVIDIA GPU、显存和 Python 环境，完成实现与验证。
4. 按文档验收真实 CUDA 推理、日期范围、天气对齐和结果导出。

## 提示词覆盖范围

- 下载 `amazon/chronos-2` 完整权重，固定版本并验证离线加载。
- Python/FastAPI 后端与中文 HTML/CSS/JavaScript 页面。
- CSV/XLSX 上传、字段识别、人工修正及多序列映射。
- 自定义日期范围，正确计算完整预测步数。
- 城市、坐标、矩形范围与 GeoJSON 地理输入。
- 获取历史天气与未来天气预报，进行时空对齐和辅助变量合并。
- GPU 推理、分位数展示、CSV/XLSX 导出及验收要求。

## 适用边界

模型下载和最新天气获取需要联网；离线预测需要本地模型及完整的输入和天气缓存。天气预报不能覆盖任意未来日期，添加天气也不保证提高预测精度。回测须遵守天气发布时间约束，避免使用事后信息。

提示词中的 API 和版本应在实际实施时重新核对。文档中的功能与测试属于实现要求，不代表已实现或已通过验证。

## 上游与参考

- [Amazon Chronos 官方仓库](https://github.com/amazon-science/chronos-forecasting)
- [Chronos-2 模型](https://huggingface.co/amazon/chronos-2)
- [PyTorch 安装指南](https://pytorch.org/get-started/locally/)
- [Open-Meteo 天气接口](https://open-meteo.com/en/docs)

本项目为独立社区提示词项目，与 Amazon、Hugging Face、Open-Meteo 无隶属或背书关系。

## 贡献

欢迎通过 Issue 或 Pull Request 改进提示词、纠正 API 说明或补充验收条件。请注明参考来源，并区分建议与真实执行结果。请勿提交密钥、个人业务数据、天气服务凭证或模型权重。

## 许可证

本仓库原创提示词与文档采用 [MIT License](LICENSE)。上游模型、软件依赖和天气数据分别遵循各自许可证与服务条款；本仓库许可证不改变这些条款。
