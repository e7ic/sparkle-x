# Sparkle X

## **项目简介**

一个高性能、跨端的低代码平台，旨在通过直观的页面生成器和强大的后端服务，实现多端统一发布。项目采用现代化技术栈，结合 **Rust** 和 **Next.js**，提供高效的用户体验和开发效率。

---

## **技术栈**

### **后端**
- **语言**: Rust
- **框架**: Axum
- **数据库**: Postgres
- **功能**: 提供 API 服务、处理用户配置、生成 AST。

### **前端**
- **框架**: Next.js (App Router 模式)
- **语言**: TypeScript
- **状态管理**: Zustand / Redux
- **功能**: 拖拽式页面生成、实时预览。

### **多端适配**
- **工具**: TaroJS
- **功能**: 将页面配置转化为小程序和网页代码。

### **辅助工具**
- **AST 生成器**: Rust 模块，用于解析和生成 AST。
- **测试框架**: Jest / Rust 自带测试。

---

## **目录结构**

```plaintext
low-code-platform/
├── backend/                   # 后端服务
├── database/                  # 数据库管理
├── frontend/                  # 前端项目 (App Router 模式)
├── ast-generator/             # AST 生成器模块
├── taro-adapter/              # 多端适配模块
├── deployment/                # 部署相关
├── tests/                     # 测试文件
├── scripts/                   # 脚本目录
├── README.md                  # 项目文档
└── LICENSE                    # 开源协议
```

---

## **快速开始**

### **环境准备**
1. 安装 **Rust** 和 **Cargo**:
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
2. 安装 **Node.js** 和 **pnpm**:
   ```bash
   npm install -g pnpm
   ```
3. 安装 **Postgres** 数据库。

### **项目启动**

#### 1. 克隆项目
```bash
git clone https://github.com/e7ic/sparkle-x.git
cd sparkle-x
```

#### 2. 启动后端服务
```bash
cd backend
cargo run
```

#### 3. 启动前端服务
```bash
cd frontend
pnpm install
pnpm dev
```

#### 4. 初始化数据库
```bash
cd database
psql -U <your_user> -d <your_database> -f seed.sql
```

#### 5. 运行多端适配器
```bash
cd taro-adapter
cargo run
```

---

## **主要功能**

1. **拖拽式页面生成器**  
   用户可以通过可视化界面快速创建页面，配置完成后自动生成代码。

2. **实时预览与发布**  
   提供页面实时预览功能，支持一键发布到小程序或网页。

3. **多端支持**  
   基于 **TaroJS**，实现统一的多端代码生成。

4. **高效后端服务**  
   使用 Rust 和 Axum 提供高性能 API 和数据处理能力。

---

## **测试**

### **单元测试**
- 后端测试：
  ```bash
  cd backend
  cargo test
  ```
- 前端测试：
  ```bash
  cd frontend
  pnpm test
  ```

### **集成测试**
- 在 `tests/` 文件夹中添加测试用例，执行：
  ```bash
  cd tests
  ./run-tests.sh
  ```

---

## **部署**

### **Docker 部署**
1. 构建镜像：
   ```bash
   docker-compose build
   ```
2. 启动服务：
   ```bash
   docker-compose up -d
   ```

### **Nginx 配置**
在 `deployment/nginx.conf` 中定义反向代理规则，确保前后端服务正确转发。

---

## **待办事项**
- [ ] 完成拖拽组件库的初版开发。
- [ ] 优化多端代码生成的转换规则。
- [ ] 提高复杂页面配置的数据库查询效率。

---

## **贡献**
欢迎任何形式的贡献！请提交 Pull Request 或报告问题。

