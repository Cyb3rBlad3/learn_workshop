# Git 简介与安装

> 学习日期: 2026-05-12

## 概述
本节介绍 Git 的基本概念、为什么需要版本控制，以及如何安装和配置 Git。

## 核心知识点
- Git 是分布式版本控制系统
- 每个开发者拥有完整的仓库副本
- Git 通过快照（snapshot）而非差异（diff）来记录文件变化

## 详细讲解

### 什么是版本控制？
版本控制是一种记录文件内容变化的系统，便于将来查阅特定版本的修订情况。

### 为什么选择 Git？
- **分布式**：不依赖中央服务器，本地即可完成大部分操作
- **高效**：快照机制使得分支、合并操作非常快速
- **安全**：所有数据使用 SHA-1 哈希校验

### 安装 Git
```bash
# Ubuntu/Debian
sudo apt-get install git

# macOS (通过 Homebrew)
brew install git

# 验证安装
git --version
```

### 初始配置
```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"
```

## 小结
- Git 是目前最流行的分布式版本控制系统
- 安装后需要配置用户名和邮箱
- Git 使用快照机制，性能优于传统 VCS

## 练习
1. 在你的电脑上安装 Git 并验证版本号
2. 配置你的用户名和邮箱
3. 运行 `git config --list` 查看当前配置
