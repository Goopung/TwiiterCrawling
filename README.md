# 开袋即食的推特小工具(mac-arm64)

## 适用范围
本仓库 **仅适用于 mac-arm64** 设备，其他系统用户需自行替换对应版本的 **ChromeDriver**。

---

## 使用步骤

### 1. 适配 ChromeDriver
首先，点击仓库内的 **“Google Chrome”** 链接，以确保 **ChromeDriver** 版本与本地 Chrome 浏览器匹配。

### 2. 运行 `app.ipynb`
**建议使用 Python 3.10，并安装必要依赖**：
  ```bash
  pip install -r requirements.txt
  ```
按照 **`app.ipynb`** 的步骤执行代码，进入：
```python
driver.get("https://x.com")
```
后，手动完成 **X（Twitter）** 的登录。

### 3. 保存 Cookies
登录后，运行此单元格获取 **Cookies** 并保存，下次直接使用cookies即可跳过登录界面：
```python
cookies = driver.get_cookies()
with open("twitter_cookies.pkl", "wb") as file:
    pickle.dump(cookies, file)
```
这样，下次运行时可以直接加载 **Cookies**，无需重复登录。

### 4. 配置爬取参数
更改以下参数，即可启动爬取：
- **网址**
- **滚动轮数 (`scroll_times`)**
- **最大爬取轮数 (`max_batches`)**

然后运行代码开爬
