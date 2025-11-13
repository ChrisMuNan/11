---
name: playwright
type: repo
version: 1.0.0
agent: CodeActAgent
keywords: ["playwright", "webpage", "screenshot", "load test", "MCP server"]
triggers:
- playwright
- MCP server
- 网页截图
- 加载测试
---

# Playwright Task Execution Guide

## 1. MCP Server Configuration (Mandatory)
A local Playwright MCP server is already running. Use the following connection details:
{
  "mcpServers": {
    "playwright": {
      "url": "http://host.docker.internal:8931/mcp"
    }
  }
}
All Playwright operations must be executed via this MCP server. No additional browser installation is required.

## 2. Task Execution Steps
### Access Webpage and Verify Status Code
- Use Playwright Python script to connect to the Chromium browser through the MCP server.
- Visit the target URL: https://view-dev.tkelevator.com.cn
- Verify the webpage returns a 200 status code (indicating successful loading).

### Screenshot Capture and Saving
- Take a full-page screenshot after the webpage is fully loaded.
- Save path: `/workspace/webpage_screenshot.png` (root directory of the repository for easy access).

## 3. Code Specifications
- Script filename: `test_playwright_webpage.py`
- Must import: `from playwright.sync_api import sync_playwright`
- Include error handling (e.g., prompts for webpage load timeouts or non-200 status codes).

## 4. Output Requirements
- Generate a complete, runnable Python script that requires no modifications to execute.
- Add runtime instructions at the end of the script (how to run it, output file location).