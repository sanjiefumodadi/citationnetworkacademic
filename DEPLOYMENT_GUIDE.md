# Streamlit应用部署指南

## 部署到Streamlit Cloud

### 步骤1: 准备GitHub仓库

1. **创建GitHub仓库**
   - 访问 [GitHub](https://github.com/) 并登录
   - 点击 "New repository"
   - 输入仓库名称（例如：academic-citation-network）
   - 选择 "Public" 或 "Private"
   - 点击 "Create repository"

2. **上传项目文件**
   - 克隆仓库到本地：
     ```bash
     git clone https://github.com/your-username/academic-citation-network.git
     ```
   - 将以下文件复制到仓库目录：
     - app.py
     - requirements.txt
     - .streamlit/config.toml
   - 提交并推送代码：
     ```bash
     git add .
     git commit -m "Initial commit"
     git push origin main
     ```

### 步骤2: 部署到Streamlit Cloud

1. **访问Streamlit Cloud**
   - 访问 [Streamlit Cloud](https://streamlit.io/cloud)
   - 点击 "Get started for free"
   - 使用GitHub账号登录

2. **部署应用**
   - 点击 "New app"
   - 在 "Repository" 下拉菜单中选择你的GitHub仓库
   - 在 "Branch" 中选择 "main"
   - 在 "Main file path" 中输入 "app.py"
   - 点击 "Deploy!"

3. **等待部署完成**
   - Streamlit Cloud会自动安装依赖并部署应用
   - 部署完成后，你会获得一个公共URL（例如：https://your-app.streamlit.app）

### 步骤3: 验证部署

1. **访问应用**
   - 打开部署后的URL
   - 测试应用功能，确保一切正常运行

2. **分享应用**
   - 将URL分享给其他人，他们现在可以访问和使用你的应用了

## 故障排除

### 常见问题

1. **依赖安装失败**
   - 确保requirements.txt文件包含所有必要的依赖
   - 检查依赖版本是否兼容

2. **应用无法启动**
   - 检查app.py文件是否有语法错误
   - 查看Streamlit Cloud的日志输出

3. **PubMed API访问限制**
   - 应用可能会遇到PubMed API的访问限制
   - 考虑添加缓存机制或减少API调用频率

4. **内存限制**
   - Streamlit Cloud的免费计划有内存限制
   - 对于大型网络，可能需要优化代码或使用付费计划

## 优化建议

1. **添加缓存**
   - 使用Streamlit的缓存装饰器缓存API调用结果
   - 减少重复的网络请求

2. **优化性能**
   - 限制最大结果数
   - 优化网络构建算法

3. **添加错误处理**
   - 增加API调用的错误处理
   - 提供友好的错误信息给用户

4. **添加使用说明**
   - 在应用中添加使用指南
   - 提供示例关键词

## 部署状态

- ✅ 应用文件：app.py
- ✅ 依赖文件：requirements.txt
- ✅ 配置文件：.streamlit/config.toml
- ✅ 部署就绪

按照上述步骤操作后，你的学术文献引用网络分析应用将可以被其他人访问和使用。