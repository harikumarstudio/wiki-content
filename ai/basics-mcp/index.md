---
title: "Model Context Protocol (MCP)"
description: "What is an MCP?"
authors:
  - harikumarstudio
related:
  - houdini/ai-fxhoudinimcp
tags:
  - article
---

## 1 - What is it?

An _MCP_ server is a lightweight program that acts as a universal adapter, allowing AI models to securely connect to external tools, data sources and APIs. MCP stands for __Model Context Protocol__ and was created by _Anthropic_ in late 2024. It solves the problem of having to write custom, messy integration code for every single AI model and application. MCP standardises this layer and sits above APIs (which was mainly designed for programs written by humans), whereas, an MCP, is designed for models that reason like humans.

## 2 - How to use it?

Link program with MCP client.
