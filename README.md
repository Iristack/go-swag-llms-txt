# go-swag-llms-txt

Swag 注释生成智能体指引（Agent Guide for Swag Annotation）
🤖 一份专为 AI 智能体设计的 Swag 注释生成规范文档。将此文件交给智能体，它即可准确、可靠地为 Go 项目中的 API 函数生成符合 swaggo/swag 要求的注释，确保生成的 Swagger 文档路径正确、结构完整、开箱即用。
为什么需要它？

在使用 AI 辅助生成 Swag 注释时，常见问题包括：
路由路径缺失基础前缀（如漏掉 /api/v1）
参数类型或位置推断错误
引用了不存在或未导出的结构体
HTTP 方法与实际注册不一致

本指引通过明确的规则、可验证的步骤和禁止项清单，约束智能体行为，从根本上避免上述问题。
如何使用？

1. 将本仓库中的 llms.txt/llms_en.txt 作为上下文提供给您的 AI 智能体
2. 智能体在分析 Go 代码时，严格遵循指引中的五步流程
3. 输出的注释可直接插入代码，运行 swag init 即可生成正确文档
特点 ✨
✅ 强制包含路由前缀（如 /api/v1）
✅ 基于代码逻辑推断参数来源
✅ 结构体引用需真实存在
✅ 支持 Gin、Echo 等主流框架
✅ 输出即合规，无需人工修正

-----


Agent Guide for Swag Annotation Generation
🤖 A precise, actionable specification designed specifically for AI agents to generate correct and production-ready Swag (Swagger 2.0) comments for Go APIs. Feed this guide to your agent, and it will reliably produce annotations that work seamlessly with swaggo/swag.
Why This Exists

When AI assists in generating Swag comments, common failures include:
Missing base path prefixes (e.g., omitting /api/v1)
Incorrect parameter types or locations (query vs path)
Referencing non-existent or unexported structs
Mismatched HTTP methods (e.g., [post] when route is GET)

This guide eliminates those issues by providing clear rules, verifiable steps, and explicit prohibitions—ensuring agent output is trustworthy.
How to Use

1. Provide the llms.txt/llms_en.txt as context to your AI agent
2. The agent follows the 5-step workflow while analyzing Go code
3. Generated comments can be inserted directly into source files—run swag init and get a working Swagger UI
Key Features ✨
✅ Enforces full route paths (e.g., /api/v1/users/{id})
✅ Infers parameters from actual code usage (c.Param, c.Query, etc.)
✅ Validates struct existence and export status
✅ Compatible with Gin, Echo, and other routers
✅ Zero manual fixes needed after generation
