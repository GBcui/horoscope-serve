# Horoscope MCP Server | 星座运势 MCP 服务器

[English](#english) | [中文](#chinese)

## English

A Model Context Protocol (MCP) server that provides daily horoscope readings and fortune telling. This server integrates with a horoscope API to provide detailed fortune readings for all zodiac signs.
[![smithery badge](https://smithery.ai/badge/@GBcui/horoscope-serve)](https://smithery.ai/server/@GBcui/horoscope-serve)
![Horoscope MCP Server](./test.png)

## Features

- Get horoscope readings for all 12 zodiac signs
- Multiple time ranges (today, tomorrow, week, month)
- Detailed fortune readings including:
  - Overall fortune
  - Love life
  - Career
  - Wealth
  - Health
- Lucky numbers, colors, and compatible signs
- Things to do and avoid
- Clean error handling and validation

## Installation

### Installing via Smithery

To install Horoscope MCP Server for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@GBcui/horoscope-serve):

```bash
npx -y @smithery/cli install @GBcui/horoscope-serve --client claude
```

### Manual Installation
1. Clone the repository:

```bash
git clone https://github.com/GBcui/horoscope-serve.git
cd horoscope-serve
```

2. Install dependencies:

```bash
npm install
```

3. Build the server:

```bash
npm run build
```

4. Add to your MCP settings configuration file (location depends on your system):

For VSCode Claude extension:

```json
{
  "mcpServers": {
    "horoscope": {
      "command": "node",
      "args": ["/path/to/horoscope-serve/build/index.js"]
    }
  }
}
```

## Usage

The server provides a tool called `get-horoscope` that can be used to fetch horoscope readings.

### Tool: get-horoscope

Parameters:

- `type` (string): Zodiac sign
  - Options: 'aries', 'taurus', 'gemini', 'cancer', 'leo', 'virgo', 'libra', 'scorpio', 'sagittarius', 'capricorn', 'aquarius', 'pisces'
- `time` (string): Time range for the reading
  - Options: 'today', 'nextday', 'week', 'month'

Example usage:

```typescript
use_mcp_tool with:
server_name: "horoscope"
tool_name: "get-horoscope"
arguments: {
  "type": "aries",
  "time": "today"
}
```

Sample output:

```txt
白羊座 2024年3月27日运势

▎ 整体运势 ★★★★☆
今天的运势相当不错，工作上会有意外收获...

▎ 爱情运势 ★★★★
单身的你可能会遇到心仪的对象...

[Additional sections...]
```

## Chinese

## 星座运势 MCP 服务器

一个提供星座运势和运程预测的 Model Context Protocol (MCP) 服务器。该服务器集成了星座运势 API，为全部十二星座提供详细的运势解读。
[![smithery badge](https://smithery.ai/badge/@GBcui/horoscope-serve)](https://smithery.ai/server/@GBcui/horoscope-serve)
![Horoscope MCP Server](./test.png)


## 功能特点

- 支持全部十二星座运势查询
- 多个时间范围（今日、明日、本周、本月）
- 详细的运势解读包括：
  - 整体运势
  - 爱情运势
  - 事业运势
  - 财运运势
  - 健康运势
- 幸运数字、幸运颜色和速配星座
- 今日宜忌指南
- 完善的错误处理和数据验证

## 安装步骤

### 通过 Smithery 安装

通过 [Smithery](https://smithery.ai/protocol-tools/@GBcui/horoscope-serve) 为 Claude Desktop 安装 Horoscope MCP Server：

```bash
npx -y @smithery/cli install @GBcui/horoscope-serve
```

### 手动安装
1. 克隆仓库：

```bash
git clone https://github.com/GBcui/horoscope-serve.git
cd horoscope-serve
```

2. 安装依赖：

```bash
npm install
```

3. 构建服务器：

```bash
npm run build
```

4. 在 MCP 设置配置文件中添加（具体位置取决于您的系统）：

VSCode Claude / Cursor 扩展配置：

```json
{
  "mcpServers": {
    "horoscope": {
      "command": "node",
      "args": ["/path/to/horoscope-serve/build/index.js"] // 替换为实际路径
    }
  }
}
```

## 使用方法

服务器提供了 `get-horoscope` 工具用于获取星座运势。

### 工具：get-horoscope

参数说明：

- `type` (字符串)：星座类型
  - 可选值：'aries'（白羊座）, 'taurus'（金牛座）, 'gemini'（双子座）, 'cancer'（巨蟹座）, 'leo'（狮子座）, 'virgo'（处女座）, 'libra'（天秤座）, 'scorpio'（天蝎座）, 'sagittarius'（射手座）, 'capricorn'（摩羯座）, 'aquarius'（水瓶座）, 'pisces'（双鱼座）
- `time` (字符串)：运势时间范围
  - 可选值：'today'（今日）, 'nextday'（明日）, 'week'（本周）, 'month'（本月）

使用示例：

```typescript
use_mcp_tool with:
server_name: "horoscope"
tool_name: "get-horoscope"
arguments: {
  "type": "aries",
  "time": "today"
}
```

返回数据示例：

```txt
白羊座 2024年3月27日运势

▎ 整体运势 ★★★★☆
今天的运势相当不错，工作上会有意外收获...

▎ 爱情运势 ★★★★
单身的你可能会遇到心仪的对象...

[更多运势内容...]
```

## 技术实现

使用以下技术构建：

- TypeScript
- Model Context Protocol SDK
- Node.js Fetch API
- Zod 用于参数验证

## 错误处理

服务器包含完善的错误处理机制，涵盖：

- 无效的星座类型
- 无效的时间范围
- API 请求失败
- 数据解析错误

错误返回时会包含适当的错误代码和描述性消息。

## 贡献指南

欢迎提交贡献！请随时提交 Pull Request。

## 许可证

MIT 许可证 - 您可以在自己的项目中自由使用。
