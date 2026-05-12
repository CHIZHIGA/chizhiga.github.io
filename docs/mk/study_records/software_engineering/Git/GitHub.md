# GitHub

## 1. Git vs GitHub

### Git

👉 version control system

负责：

* tracking history
* commits
* branches
* merges

本地也能用。

---

### GitHub

👉 online hosting platform for Git repositories

负责：

* collaboration
* pull requests
* issue tracking
* code review
* CI workflows

> Git is the version control system itself, whereas GitHub is a cloud platform for hosting and collaborating on Git repositories.

---

## 2. GitHub 项目结构

```
src/
tests/
docs/
.github/
README.md
LICENSE
CITATION.cff
.gitignore
pyproject.toml
```

---

### src/

源码。

---

### tests/

pytest tests。

---

### docs/

documentation source。

---

### .github/

GitHub workflows/config。

通常：

```
.github/workflows/
```

里面是 CI。

---

### CITATION.cff

> To ensure credit is easily given to the developers, or to provide a DOI / objective reference to the software version used in an analysis.

### .gitignore

What is the purpose of the `.gitignore` file?

To prevent unwanted files from being tracked by the repository.

Besides auxiliary and artefact Python files, and folders containing IDE settings, are there any other file types or patterns that you recommend developer add to the `.gitignore` file?

• Recommending the project-specific data file types(.mpth and .mfmt) to be ignored (with the possible exception of the
test data files). since these may bloat the repository with large files / might not be appropriate for sharing if they are research-specific.

• Recommending the output directory for the build HTML documentation to be ignored. since the docs can be regenerated from the sourcefiles anyway.

---

## 3. README

README 是：

> newcomer first entry point

---

### README 应该包含什么

至少：

* project overview
* installation
* usage
* examples
* dependencies
* how to run tests

> 为什么 README 很重要？

* helps onboarding
* explains project purpose
* improves usability
* assists contributors

---

## 4. LICENSE

定义：

> legal permissions/restrictions

---

### 为什么重要

没有 LICENSE：

默认：

```
all rights reserved
```

别人理论上不能合法使用。

> To ensure users know what rights they have to use the software, or to prevent

---

## 5. CITATION 文件

### 作用

告诉别人：

* 如何引用项目
* 如何 credit authors

特别：

* research software
* academic software

---

## 6. Fork

### fork 是什么

GitHub 上：

* 复制一个 repo
* 到你自己的账户

---

### 为什么 external contributors 用 fork

因为：

* maintainers 不会给陌生人 write access
* protects main repository
* contributors can work independently
* changes reviewed via PR

---

### workflow

```
fork
↓
clone fork
↓
branch
↓
commit
↓
push
↓
pull request
```

---

## 7. Pull Request（PR）

### 本质

> request to merge changes

不是 merge 本身。

---

### PR 的作用

* code review
* discussion
* testing
* quality control

> 为什么 PR review 重要？

标准：

* catches bugs
* improves code quality
* ensures consistency
* knowledge sharing

---

## 8. Issues

GitHub issue 用于：

* bug reports
* feature requests
* task tracking
* discussion

---

### 为什么重要

* organization
* prioritization
* transparency

---

## 9. Continuous Integration（CI）

### 本质

自动：

* run tests
* check formatting
* build docs

通常：

```
GitHub Actions
```

• Changes to a codebase should be frequent and incremental.

• Appropriate builds and tests should be run (normally automatically) before allowing changes to be approved and implemented, to ensure the project is always in a workable state.

---

### 为什么重要

* catches problems early
* prevents broken code entering main
* automates quality checks

---

### workflow

```
PR opened
↓
CI runs tests
↓
review
↓
merge
```

---

## 10. Development Lifecycle

### 标准流程

```
Issue
↓
Branch
↓
Development
↓
Testing
↓
Pull Request
↓
Code Review
↓
CI checks
↓
Merge
```

---

## 11. Agile vs Waterfall

Choosing between Agile and Waterfall is less about finding the "better" method and more about matching the right tool to the job. It’s the difference between building a bridge (Waterfall) and building a startup (Agile).

---

### **The Waterfall Methodology**

Waterfall is the traditional, linear approach to project management. It moves in a logical, sequential flow: Requirements → Design → Implementation → Verification → Maintenance. Like a real waterfall, the water only flows one way—you can’t easily jump back up to the "Requirements" phase once you’re already testing the product.

* **Mindset:** "Measure twice, cut once."
* **Structure:** Heavily documented and disciplined.
* **Best For:** Projects with a fixed scope, clear requirements, and a hard deadline.

---

### **The Agile Methodology**

Agile is an iterative, incremental approach. Instead of one massive "Big Bang" release at the end, the project is broken into small, consumable chunks called **Sprints** (usually 1–4 weeks). After every sprint, you have a working product that you can test and improve.

* **Mindset:** "Fail fast, learn faster."
* **Structure:** Flexible, collaborative, and highly responsive to change.
* **Best For:** Projects where the end goal is a bit fuzzy or where market conditions change rapidly.

---

### **Side-by-Side Comparison**

| Feature | Waterfall | Agile |
| --- | --- | --- |
| **Project Flow** | Linear & Sequential | Iterative & Cyclical |
| **Requirements** | Defined upfront; hard to change. | Evolves throughout the project. |
| **Customer Involvement** | High at the start and end. | Constant throughout the process. |
| **Delivery** | One single "Big Bang" release. | Frequent, small releases. |
| **Risk** | High (errors found late are costly). | Low (errors found and fixed early). |

---

### **Which One Should You Choose?**

#### **Choose Waterfall if...**

* The project is **simple and predictable**.
* The requirements are **fixed** and unlikely to change (e.g., a regulatory compliance project).
* You are working in a highly regulated industry where **extensive documentation** is legally required.
* The client prefers a hands-off approach until the final reveal.

#### **Choose Agile if...**

* The project is **complex** or the final product isn't fully defined.
* You need to get a **Minimum Viable Product (MVP)** to market quickly.
* You have a dedicated team and a client who wants to be **heavily involved**.
* The industry is fast-moving (like software or app development).

---

Most modern tech companies actually land somewhere in the middle—often called "Agile-fall"—where they plan the big picture with a Waterfall mindset but execute the daily work using Agile Sprints.

## 12. Explain

### Why use branches?

```
Branches isolate development work and protect the stable main branch.
```

---

### Why use PR review?

```
PR review improves code quality and helps catch bugs before merging.
```

---

### Why use CI?

```
CI automatically checks code quality and prevents broken changes from entering the main branch.
```

---

### Why use forks?

```
Forks allow external contributors to work safely without direct write access to the main repository.
```

---