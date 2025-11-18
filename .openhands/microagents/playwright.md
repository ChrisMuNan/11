playwright.md
---
name: playwright
type: repo
version: 1.0.0
agent: CodeActAgent
keywords: ["playwright", "webpage", "screenshot", "load test", "MCP server"]
triggers:
  - playwright
  - MCP server
  - webpage screenshot
  - load test
---
# Core Constraints
- **Prohibition of Local Browser Operations**: Do not execute any local browser installation commands (e.g., `python -m playwright install` and its variants), and do not launch local Chromium instances.
- **Mandatory MCP Dependency**: All browser operations must be completed through the local MCP server (using the configured URL) and rely on the Chromium environment provided by MCP.

# Playwright Task Execution Guide

Connect exclusively to the local MCP server using the configured URL (do not launch a local Chromium instance).  
Access the webpage `https://view-dev.tkelevator.com.cn` through the MCP-connected Chromium browser.  
Verify the webpage returns a 200 status code (successful load) via the MCP session.  
Take a full-page screenshot within the MCP-managed browser session and save it as `webpage_screenshot.png` in the repository root.  
Include error handling for timeouts, failed MCP connections, or unsuccessful webpage loads (with clear messages for MCP-specific failures).