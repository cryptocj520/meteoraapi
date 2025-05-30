# �� Meteora监控平台 V2.0

高性能Solana生态Meteora协议数据监控平台，提供实时数据分析、智能筛选和报警提醒功能。

## ✨ 核心功能

### 📊 实时数据监控
- **多维数据展示：** TVL、APY、交易量、手续费等核心指标
- **趋势分析：** 实时计算数据变化趋势（上升/下降/持平）
- **变化幅度：** 精确显示各指标的变化百分比
- **历史追踪：** 支持查看池子历史数据变化

### 🔍 智能筛选系统
- **快速筛选：** 预设大池子、高收益、活跃交易等筛选方案
- **高级筛选：** 支持TVL、APY、交易量等多维度范围筛选
- **搜索功能：** 支持池子名称和地址模糊搜索
- **排序功能：** 支持多字段自定义排序

### 🚨 智能报警系统
- **实时监控：** 24/7监控池子数据变化
- **智能分析：** 基于趋势变化的报警逻辑
- **多指标支持：** 监控流动性、交易量、手续费等4个关键指标
- **灵活配置：** 用户可自定义各指标的变化阈值
- **多种提醒：** 支持可视化通知和声音提醒
- **历史记录：** 完整的报警历史记录和查询
- **预设方案：** 提供保守型、平衡型、敏感型三种预设配置

#### 报警功能使用方法

**方法一：系统设置（推荐）**
1. 点击页面右上角设置按钮（⚙️）
2. 切换到"警报设置"标签页
3. 启用报警系统并配置阈值
4. 支持测试声音和预设方案

**方法二：独立报警管理器**
1. 点击页面右上角红色"报警记录"按钮（🔔）
2. 在报警管理器中配置设置
3. 查看历史报警记录

**监控指标：**
- 流动性(TVL)变化
- 24小时交易量变化
- 24小时手续费变化
- 1小时手续费变化

### 🎨 个性化配置
- **字段管理：** 自定义显示字段和列顺序
- **视图配置：** 多种预设视图（交易员、投资者、技术分析）
- **主题设置：** 支持多种界面主题
- **配置保存：** 自动保存用户个性化设置

### 📈 数据可视化
- **表格视图：** 清晰的数据表格展示
- **图表视图：** 支持数据图表分析
- **趋势指示：** 直观的趋势变化图标
- **颜色编码：** 根据变化幅度的颜色提示

### 🔄 自动更新
- **后台更新：** 独立的数据更新服务
- **增量同步：** 智能的数据同步策略
- **故障恢复：** 自动重试和错误恢复机制
- **性能优化：** 高效的数据处理和缓存

## ✨ 核心特性

- **🌟 验证成功的API技术**：基于65秒获取88,300个池子数据的成功技术
- **⚡ 高性能数据存储**：SQLite + 性能优化索引
- **🎯 智能筛选系统**：多维度数据筛选和排序
- **🔔 实时警报系统**：新池子提醒、数值变化检测
- **⚙️ 双层配置管理**：系统级固定配置 + 用户级实时配置
- **🎨 Meteora风格UI**：暗色调、紧凑布局、适合大量数据展示

## 🛠️ 技术架构

### 后端技术栈
- **Python Flask：** 轻量级Web框架
- **SQLite：** 高性能本地数据库
- **RESTful API：** 标准化API接口
- **多线程处理：** 独立的数据更新线程

### 前端技术栈
- **原生JavaScript：** 模块化开发架构
- **Bootstrap 5：** 响应式UI框架
- **Chart.js：** 数据可视化图表
- **Font Awesome：** 图标字体库

### 数据源
- **Meteora官方API：** 获取实时池子数据
- **DLMM协议：** 支持最新的动态流动性协议
- **数据验证：** 多重数据校验和过滤机制

## 📦 快速开始

### 环境要求
- Python 3.8+
- 稳定的网络连接
- 现代浏览器（Chrome、Firefox、Safari）

### 安装部署
```bash
# 克隆项目
git clone [项目地址]
cd meteora-monitor

# 安装依赖
pip install -r requirements.txt

# 启动应用
python main.py
```

### 访问应用
```
http://localhost:5000
```

## 📊 API接口

### 报警系统API
- `GET /api/alerts/config` - 获取报警配置
- `POST /api/alerts/config` - 保存报警配置
- `GET /api/alerts/records` - 获取报警记录
- `POST /api/alerts/test-sound` - 测试报警声音

### 数据查询API
- `GET /api/health` - 系统健康检查
- `GET /api/pools` - 获取池子列表（支持筛选、排序、分页）
- `GET /api/pools/{address}` - 获取单个池子详情
- `POST /api/system/update` - 手动触发数据更新

### 查询参数示例

```bash
# 获取报警配置
curl "http://localhost:5000/api/alerts/config"

# 保存报警配置
curl -X POST "http://localhost:5000/api/alerts/config" \
  -H "Content-Type: application/json" \
  -d '{"enabled": true, "liquidity_threshold": 20}'

# 筛选高APY池子
curl "http://localhost:5000/api/pools?min_apy=50&sort=apy&dir=DESC&limit=20"
```

## 🎯 使用指南

### 基础使用
1. **查看数据：** 启动后自动加载最新池子数据
2. **应用筛选：** 使用左侧筛选面板过滤数据
3. **自定义显示：** 配置显示字段和排序方式
4. **启用报警：** 在设置中配置报警阈值

### 报警功能详细使用
请参考：[报警系统使用指南](docs/alert_system_usage.md)

### 高级功能
1. **趋势分析：** 关注数据变化趋势指示
2. **报警监控：** 设置合适的阈值进行实时监控
3. **数据导出：** 支持CSV和JSON格式导出
4. **配置管理：** 保存和复用个人配置方案

## 🔧 配置说明

### 报警系统配置
```json
{
  "enabled": true,
  "liquidity_threshold": 20.0,
  "volume_threshold": 20.0,
  "fees_24h_threshold": 20.0,
  "fees_1h_threshold": 20.0,
  "sound_enabled": true
}
```

### 更新频率设置
- **增量更新：** 5分钟间隔
- **全量更新：** 30分钟间隔
- **可自定义：** 支持用户调整更新频率

## 📈 数据指标说明

### 核心指标
- **TVL (Total Value Locked)：** 池子总锁定价值
- **APY (Annual Percentage Yield)：** 年化复合收益率
- **24H Volume：** 24小时交易量
- **24H Fees：** 24小时手续费收入
- **1H Fees：** 1小时手续费收入

### 计算指标
- **Fee/TVL Ratio：** 24小时手续费与TVL的比率
- **Estimated Daily Fee Rate：** 基于1小时数据估算的日收益率
- **Change Percentage：** 各指标的变化幅度百分比

## 📁 项目结构

```
meteora-monitor-v2/
├── 📁 core/                    # 核心业务模块
│   ├── api_client.py          # API数据获取客户端
│   ├── database.py            # 数据库操作层
│   ├── models.py              # 数据模型定义
│   ├── config_manager.py      # 配置管理器
│   └── data_updater.py        # 数据更新服务
├── 📁 web/                     # Web服务层
│   ├── app.py                 # Flask主应用
│   ├── templates/             # HTML模板
│   └── static/                # 静态资源
├── 📁 test/                    # 测试文件
│   ├── test_alert_system.py   # 报警系统测试
│   └── test_complete_alert_system.py # 完整系统测试
├── 📁 docs/                    # 文档
│   ├── alert_system_usage.md  # 报警系统使用指南
│   └── alert_system_implementation.md # 实现说明
├── 📁 data/                    # 数据存储
├── main.py                    # 应用入口
└── requirements.txt           # 依赖列表
```

## 🔧 故障排除

### 报警系统相关

#### Q: 报警没有触发？
**解决方案：**
1. 检查是否启用了报警系统
2. 确认阈值设置是否合理
3. 验证池子是否有数据变化
4. 查看浏览器控制台是否有错误

#### Q: 声音无法播放？
**解决方案：**
1. 检查浏览器是否允许音频播放
2. 确认音量设置不为0
3. 点击"测试声音"验证功能
4. 尝试用户交互后再测试

### 系统相关

1. **端口占用**
   ```bash
   # 检查端口占用
   lsof -i :5000
   ```

2. **数据库权限**
   ```bash
   # 确保data目录有写权限
   chmod 755 data/
   ```

3. **API连接失败**
   - 检查网络连接
   - 查看日志文件：logs/app.log

## 🧪 测试

### 运行测试
```bash
# 测试报警系统核心功能
python test/test_alert_system.py

# 测试完整系统集成
python test/test_complete_alert_system.py
```

### 测试内容
- 数据库结构和索引
- API接口功能
- 报警触发逻辑
- 前端集成
- 配置管理

## 🚀 未来规划

### 近期功能
- [ ] 更多数据可视化图表
- [ ] 池子对比分析功能
- [ ] 高级筛选条件组合
- [ ] 报警记录导出功能

### 长期规划
- [ ] 移动端适配
- [ ] 用户账户系统
- [ ] 社区功能集成
- [ ] AI智能分析

## 🤝 贡献指南

欢迎提交Issue和Pull Request来帮助改进项目！

### 开发环境
```bash
# 开发模式启动
python main.py --debug

# 运行测试
python -m pytest test/

# 代码格式化
black . && isort .
```

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏 致谢

- Meteora Protocol 团队提供的优秀协议
- Solana 生态系统的技术支持
- 开源社区的贡献和反馈

---

**⭐ 如果这个项目对您有帮助，请给我们一个Star！** 