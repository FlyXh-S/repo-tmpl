你是一个资深 Go 后端架构师。

请为一个 微服务生成一个「空项目骨架」，要求：

1. 不生成任何业务逻辑
2. 只生成目录结构、AGENT.md、main.go、wire.go, go.mod, config.go
3. 所有代码必须是最小可用骨架（scaffold）
4. 不要解释，不要总结
5. 不要生成repo 目录， 直接在当前目录下生成

【目录结构（必须严格一致）】

目录结构必须严格如下：

repo/
├── cmd/
│   ├── server/
│         ├── main.go      
├── internal/ 
│   ├── app/
│   │   ├── AGENT.md
│   │   └── wire.go    
│   ├── config/
│   │   ├── config.go
│   │   ├── AGENT.md
│   │   └── wire.go   
│   ├── handler/
│   │   ├── AGENT.md
│   │   └── wire.go
│   ├── models/
│   │   ├── AGENT.md
│   ├── service/
│   │   ├── AGENT.md
│   │   └── wire.go
│   ├── infra/
│   │   ├── AGENT.md
│   │   └── wire.go
│   ├── repository
│   │   ├── AGENT.md
│   │   └── wire.go
├── pkg/ 
│   ├── AGENT.md
│   └── wire.go
├── go.mod
└── docs/

【AGENT.md 模板（必须严格使用）】

# Agent Role

## Responsibility
<一句话说明该目录负责什么>

## Allowed
- <允许的行为或依赖>

## Forbidden
- <明确禁止的行为>

## Design Principles
- <2~4 条原则>

## Output Contract
- <该 agent 应产出的代码类型>

【main.go 要求】
- 作为程序入口
- 仅负责调用 bootstrap / init 函数
- 不包含任何业务逻辑
- 文件内容参考 templates/main_tmpl

【wire.go 要求】
- 每个 wire.go 只定义当前 package 的 ProviderSet
- 不做真正的依赖注入构建
- 文件内容参考 templates/wire_tmpl
- 文件内的package name 必须与当前目录名对齐

【go.mod 要求】
- 必须通过go mod init 生成

【config.go 要求】
- 文件内容严格符合 templates/config_tmpl

【internal/config/wire.go 要求】
- ProviderSet 中注入 config

【输出格式】
1. 不要附加任何解释文字