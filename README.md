# MoonTV/LunaTV 配置编辑器（自用）
https://vodtv.github.io/api

--- 

##  MoonTV/LunaTV配置
订阅使用：复制下面链接  

👉 Base58编码订阅链接[精简版🎬源链接](https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/jin18.txt)    （推荐使用自己部署的代理）精简版禁18源

```bash
https://moontv.gyx.workers.dev/?url=https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/jin18.json&pretty=true
```
```bash
https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/jin18.txt
```
👉 Base58编码订阅链接[精简版🎬+🔞源链接](https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/jingjian.txt) （推荐使用自己部署的代理）精简版剔除无搜索结果和污染搜索结果源                             
```bash
https://moontv.gyx.workers.dev/?url=https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/jingjian.json&pretty=true
```
```bash
https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/jingjian.txt
```

--- 

# 🌐 CORSAPI（API 代理 & JSON 订阅器）

> 基于 Cloudflare Workers 的 API 中转与 JSON 前缀替换工具，支持代理任意 API、自动添加中转、生成 Base58 订阅格式。一键部署即可拥有自己的中转 API 与订阅链接！

<details>
<summary>🚀 部署方法</summary>
  
#   
  
**部署代码：**  
- [精简版代码](https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/CORSAPI/jingjian_worker.js)  
- [禁18版代码](https://raw.githubusercontent.com/fansiphone/tv-api/refs/heads/main/CORSAPI/jin18_worker.js)

### 🧭 部署步骤
1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)  
2. 新建 **Workers & Pages → Worker**  
3. 将上述 `worker.js` 代码粘贴到编辑器中  
4. 保存并部署  

部署完成后，你就拥有了自己的 API 代理与订阅转换服务！

---   

</details>

<details>
<summary>🔗 使用示例</summary>
  
#  

```bash
假设你的 Worker 部署在：

https://api.example.workers.dev

### ① 代理任意 API  
https://api.example.workers.dev/?url=https://ikunzyapi.com/api.php/provide/vod

### ② 获取原始 JSON 配置  
https://api.example.workers.dev/?config=0

### ③ 获取API 代理的 JSON 配置  
https://api.example.workers.dev/?config=1

### ④ 获取API 代理的 Base58 编码订阅  
https://api.example.workers.dev/?config=1&encode=base58
```
---   
  
</details>

<details>
<summary>🛠️ 参数说明</summary>
  
# 
  
| 参数 | 说明 | 示例 |
|------|------|------|
| `url` | 代理任意 API 请求 | `?url=https://...` |
| `config=0` | 返回原始 JSON 配置 | `?config=0` |
| `config=1` | 返回使用api代理的 JSON 配置 | `?config=1` |
| `encode=base58` | 将 JSON 配置编码为 Base58 | `?config=1&encode=base58` |
| `(可选) prefix` | 手动指定 API 代理前缀，默认使用当前域名 | `?config=1&prefix=https://api.example.com/?url=` |

🧩 **前缀替换逻辑**  
- 若 JSON 中的 `api` 字段已包含旧前缀（`?url=`），系统会自动去除旧前缀并替换为新的代理前缀。  
- 可自定义代理路径，方便接入私有 API 或多 Worker 配置。
  
---   
  
</details>

<details>
<summary>📌 注意事项</summary>
  
# 
  
- ☁️ **Workers 免费额度：**  
  每日 10 万次请求，适合轻量部署与个人订阅使用。  

- 🔄 **API代理逻辑：**  
  自动替换 JSON 中的 `api` 字段前缀，保证所有接口都经过中转代理。  

- 💾 **Base58 编码：**  
  生成的 Base58 结果可直接导入支持订阅的客户端。  

---   
  
</details>


## 🆕 更新内容

- 📄 **Luna-TV配置编辑器**：专业的 JSON 配置文件可视化编辑器。  
- 🔍 **自动检测API状态**：每 1 小时检测一次 API 可用性，并记录最近 100 次测试报告。  
- 🧩 **源名称前添加图标**：源名称前添加图标，方便区分。  
- 🌐 **被墙资源自动中转**：为受限 API 提供 CF Worker 中转能力。  
  
---   

## 🧪 测试与示例

### ✅ 使用中转API测试
- 通过 CORSAPI 转发后，大幅提升视频源可用率。  
- 可“复活”原本无法访问的资源。  

### ⚙️ 精简版源更新
- 去除污染源与无搜索结果源（如 🎬虎牙、🔞丝袜、🔞色猫）。  
- 精简后共 **66 个可用源**，在中转代理下全部可访问。  
<details>
<summary>示例</summary>
<img width="1025" height="486" alt="61" src="https://github.com/user-attachments/assets/81c80108-7c03-4583-87ab-b7b57cdfd3bd" />
  
  
</details>

---   
  
# API 健康报告（每日自动检测API状态）

## API 状态（最近更新：2026-04-22 02:00 CST）

- 总 API 数量：174
- 成功 API 数量：112
- 失败 API 数量：62
- 平均可用率：0.0%
- 完美可用率（100%）：0 个
- 高可用率（80%-99%）：0 个
- 中等可用率（50%-79%）：0 个
- 低可用率（<50%）：174 个

<div style="font-size: 11px;">

<!-- API_TABLE_START -->
| 状态 | 资源名称 | 地址 | API | 搜索功能 | 成功次数 | 失败次数 | 成功率 | 最近7天趋势 |
|------|---------|-----|-----|---------|---------:|--------:|-------:|--------------|
| ✅ | 360资源(XML) | - | [Link](https://360zy.com/api.php/seaxml/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 39影视 | - | [Link](https://www.39kan.com/api.php/provide/vod/) | ❌ | 1 | 29 | 3.3% | ❌❌❌❌❌❌❌ |
| 🚨 | 39影视(JSON) | - | [Link](https://www.39kan.com/api.php/provide/vod/at/json/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | AV-155资源 | [Link](https://155api.com) | [Link](https://155api.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | AV-91麻豆 | [Link](https://91md.me) | [Link](https://91md.me/api.php/provide/vod) | ❌ | 3 | 27 | 10.0% | ❌❌✅❌❌❌❌ |
| 🚨 | AV-AIvin | - | [Link](http://lbapiby.com/api.php/provide/vod) | ❌ | 3 | 27 | 10.0% | ❌❌✅❌❌❌❌ |
| ✅ | AV-JKUN资源 | [Link](https://jkunzyapi.com) | [Link](https://jkunzyapi.com/api.php/provide/vod) | ✅ | 24 | 6 | 80.0% | ✅✅✅✅✅✅✅ |
| 🚨 | AV-souav资源 | [Link](https://api.souavzy.vip) | [Link](https://api.souavzy.vip/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | AV-乐播资源 | - | [Link](https://lbapi9.com/api.php/provide/vod) | ✅ | 10 | 20 | 33.3% | ❌❌✅❌❌❌❌ |
| ❌ | AV-奥斯卡资源 | [Link](https://aosikazy.com) | [Link](https://aosikazy.com/api.php/provide/vod) | ✅ | 10 | 20 | 33.3% | ✅❌✅✅❌✅❌ |
| ❌ | AV-奶香香 | [Link](https://Naixxzy.com) | [Link](https://Naixxzy.com/api.php/provide/vod) | ✅ | 7 | 23 | 23.3% | ❌❌✅❌❌✅❌ |
| ✅ | AV-淫水机资源 | [Link](https://www.xrbsp.com) | [Link](https://www.xrbsp.com/api/json.php) | ✅ | 23 | 7 | 76.7% | ✅✅✅✅✅❌✅ |
| ✅ | AV-玉兔资源 | [Link](https://apiyutu.com) | [Link](https://apiyutu.com/api.php/provide/vod) | ✅ | 26 | 4 | 86.7% | ✅✅✅❌✅✅✅ |
| ✅ | AV-番号资源 | - | [Link](http://fhapi9.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | AV-白嫖资源 | [Link](https://www.kxgav.com) | [Link](https://www.kxgav.com/api/json.php) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | AV-百万资源 | [Link](https://api.bwzyz.com) | [Link](https://api.bwzyz.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | AV-精品资源 | [Link](https://www.jingpinx.com) | [Link](https://www.jingpinx.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | AV-美少女资源 | [Link](https://www.msnii.com) | [Link](https://www.msnii.com/api/json.php) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | AV-老色逼资源 | [Link](https://apilsbzy1.com) | [Link](https://apilsbzy1.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | AV-色南国 | [Link](https://api.sexnguon.com) | [Link](https://api.sexnguon.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | AV-色猫资源 | [Link](https://api.maozyapi.com) | [Link](https://api.maozyapi.com/inc/apijson_vod.php) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | AV-辣椒资源 | [Link](https://apilj.com) | [Link](https://apilj.com/api.php/provide/vod) | ✅ | 28 | 2 | 93.3% | ✅✅✅✅✅✅✅ |
| ✅ | AV-香奶儿资源 | [Link](https://www.gdlsp.com) | [Link](https://www.gdlsp.com/api/json.php) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | AV-鲨鱼资源 | [Link](https://shayuapi.com) | [Link](https://shayuapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | AV-黄AV资源 | [Link](https://www.pgxdy.com) | [Link](https://www.pgxdy.com/api/json.php) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | dxawi接口 | - | [Link](https://dxawi.github.io/0/0.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | HG接口 | - | [Link](https://api.hgyx.vip/hgyx.json) | ❌ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | iKun资源 | - | [Link](https://ikunzyapi.com/api.php/provide/vod/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | iqiyi资源 | - | [Link](https://www.iqiyizyapi.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | OK影视接口 | - | [Link](http://ok321.top/ok) | ❌ | 5 | 25 | 16.7% | ❌❌❌❌❌❌❌ |
| 🚨 | OK资源网 | - | [Link](https://okzyw.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | T4接口 | - | [Link](https://gitee.com/free-kingdom/dc/raw/main/T4.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-1080资源 | [Link](https://api.1080zyku.com) | [Link](https://api.1080zyku.com/inc/api_mac10.php) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-360资源 | [Link](https://360zy.com) | [Link](https://360zy.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-CK资源 | [Link](https://ckzy.me) | [Link](https://ckzy.me/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-ikun资源 | [Link](https://ikunzyapi.com) | [Link](https://ikunzyapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-U酷资源 | [Link](https://api.ukuapi.com) | [Link](https://api.ukuapi.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | TV-U酷资源 | [Link](https://api.ukuapi88.com) | [Link](https://api.ukuapi88.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-wujinapi无尽 | - | [Link](https://api.wujinapi.cc/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-光速资源 | [Link](https://api.guangsuapi.com) | [Link](https://api.guangsuapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-最大点播 | [Link](http://zuidazy.me) | [Link](http://zuidazy.me/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-最大资源 | [Link](https://api.zuidapi.com) | [Link](https://api.zuidapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-卧龙点播 | [Link](https://collect.wolongzyw.com) | [Link](https://collect.wolongzyw.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-卧龙资源 | - | [Link](https://collect.wolongzy.cc/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-卧龙资源 | [Link](https://wolongzyw.com) | [Link](https://wolongzyw.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-天涯资源 | [Link](https://tyyszy.com) | [Link](https://tyyszy.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-如意资源 | - | [Link](https://cj.rycjapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | TV-小猫咪资源 | [Link](https://zy.xmm.hk) | [Link](https://zy.xmm.hk/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | TV-无尽资源 | - | [Link](https://api.wujinapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-无尽资源 | - | [Link](https://api.wujinapi.me/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-无尽资源 | - | [Link](https://api.wujinapi.net/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-旺旺短剧 | [Link](https://wwzy.tv) | [Link](https://wwzy.tv/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-旺旺资源 | [Link](https://api.wwzy.tv) | [Link](https://api.wwzy.tv/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-暴风资源 | - | [Link](https://bfzyapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-樱花资源 | - | [Link](https://m3u8.apiyhzy.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | TV-步步高资源 | - | [Link](https://api.yparse.com/api/json) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | TV-牛牛点播 | [Link](https://api.niuniuzy.me) | [Link](https://api.niuniuzy.me/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-电影天堂资源 | [Link](http://caiji.dyttzyapi.com) | [Link](http://caiji.dyttzyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | TV-百度云资源 | [Link](https://api.apibdzy.com) | [Link](https://api.apibdzy.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | TV-神马云 | [Link](https://api.1080zyku.com) | [Link](https://api.1080zyku.com/inc/apijson.php/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-红牛资源 | [Link](https://www.hongniuzy2.com) | [Link](https://www.hongniuzy2.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-索尼资源 | - | [Link](https://suoniapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-茅台资源 | [Link](https://caiji.maotaizy.cc) | [Link](https://caiji.maotaizy.cc/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-虎牙资源 | [Link](https://www.huyaapi.com) | [Link](https://www.huyaapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | TV-豆瓣资源 | [Link](https://caiji.dbzy.tv) | [Link](https://caiji.dbzy.tv/api.php/provide/vod) | ❌ | 8 | 22 | 26.7% | ❌❌❌❌❌❌❌ |
| ✅ | TV-豆瓣资源 | [Link](https://dbzy.tv) | [Link](https://dbzy.tv/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | TV-豪华资源 | [Link](https://hhzyapi.com) | [Link](https://hhzyapi.com/api.php/provide/vod) | ❌ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | TV-速博资源 | - | [Link](https://subocaiji.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-金鹰点播 | [Link](https://jinyingzy.com) | [Link](https://jinyingzy.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-金鹰资源 | [Link](https://jyzyapi.com) | [Link](https://jyzyapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-閃電资源 | [Link](https://sdzyapi.com) | [Link](https://sdzyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-非凡资源 | [Link](https://cj.ffzyapi.com) | [Link](https://cj.ffzyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-飘零资源 | [Link](https://p2100.net) | [Link](https://p2100.net/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | TV-魔都动漫 | [Link](https://caiji.moduapi.cc) | [Link](https://caiji.moduapi.cc/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | TV-黑木耳 | [Link](https://json.heimuer.xyz) | [Link](https://json.heimuer.xyz/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | TV-黑木耳点播 | [Link](https://json02.heimuer.xyz) | [Link](https://json02.heimuer.xyz/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 七七影视 | - | [Link](https://www.qiqidys.com/api.php/provide/vod/) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 乐视资源 | - | [Link](https://leshiapi.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 优质资源库1080zyk6.com高清 | - | [Link](https://api.yzzy-api.com/inc/ldg_api_all.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 余生(游魂) | - | [Link](https://www.iyouhun.com/tv/ys) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 俊佬接口 | - | [Link](http://home.jundie.top:81/top98.json) | 无结果 | 29 | 1 | 96.7% | ✅❌✅✅✅✅✅ |
| ✅ | 儿童专属(游魂) | - | [Link](https://www.iyouhun.com/tv/et) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 光速HTTP | - | [Link](http://api.guangsuapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 光速资源(m3u8) | - | [Link](https://api.guangsuapi.com/api.php/provide/vod/from/gsm3u8/) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 八戒资源 | - | [Link](http://cj.bajiecaiji.com/inc/apijson_vod.php) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 分享接口 | - | [Link](https://raw.githubusercontent.com/maoystv/6/main/000.json) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 动漫城接口 | - | [Link](https://www.yingm.cc/dm/dm.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 华为吧(HW8) | - | [Link](https://hw8.live/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 华为吧资源 | - | [Link](https://huawei8.live/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 南风接口 | - | [Link](https://raw.githubusercontent.com/yoursmile66/TVBox/main/XC.json) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 哪吒接口 | - | [Link](https://哪吒.live/) | ❌ | 5 | 25 | 16.7% | ❌❌❌❌❌❌❌ |
| ✅ | 喵影视接口 | - | [Link](http://www.meowtv.vip/tvbox.json) | 无结果 | 28 | 2 | 93.3% | ✅✅✅✅✅✅✅ |
| 🚨 | 四九资源 | - | [Link](https://49zyw.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 大地资源网络 | - | [Link](https://dadiapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 天涯海角 | - | [Link](https://tyyszyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 天空资源 (极速) | - | [Link](https://api.tiankongapi.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 天空资源(m3u8) | - | [Link](https://m3u8.tiankongapi.com/api.php/provide/vod/from/tkm3u8/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 天空资源1 | - | [Link](https://m3u8.tiankongapi.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 天翼资源 | - | [Link](https://www.911ysw.top/tianyi.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 天翼资源(JSON) | - | [Link](https://www.911ysw.top/tianyi.php/provide/vod/at/json) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 奇虎资源 | - | [Link](https://caiji.qhzyapi.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 宝片资源 | - | [Link](https://zpsps.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 宝盒VIP | - | [Link](https://raw.githubusercontent.com/guot55/YGBH/main/vip2.json) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 小猫咪资源 | - | [Link](http://zy.xiaomaomi.cc/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 小盒子4K | - | [Link](http://xhztv.top/4k.json) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 小米接口 | - | [Link](http://www.mitvbox.xyz/小米/DEMO.json) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 小苹果接口 | - | [Link](https://bitbucket.org/xduo/duoapi/raw/master/xpg.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 小鸡资源 | - | [Link](https://api.xiaojizy.live/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | 小黄人资源 | - | [Link](https://iqyi.xiaohuangrentv.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 巧记接口 | - | [Link](http://cdn.qiaoji8.com/tvbox.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 影图资源 | - | [Link](https://cj.vodimg.top/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 影视工厂 | - | [Link](https://cj.lziapi.com/api.php/provide/vod/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 快播资源网站 | - | [Link](https://gayapi.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 快看资源 | - | [Link](https://kuaikan-api.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 快车资源 | - | [Link](https://caiji.kczyapi.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 快车资源阿 | - | [Link](https://caiji.kuaichezy.org/api.php/provide) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 恒耐资源 | - | [Link](https://api.hengnaizy.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 摸鱼儿接口 | - | [Link](http://我不是.摸鱼儿.com) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 新浪资源 | - | [Link](https://api.xinlangapi.com/xinlangapi.php/provide/vod/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 新浪资源阿 | - | [Link](https://api.xinlangapi.com/xinlangapi.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 映迷资源 | - | [Link](https://www.inmi.app/api.php/provide/vod/) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 映迷资源(XML) | - | [Link](https://www.inmi.app/api.php/provide/vod/at/xml) | ❌ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | 暴风APP | - | [Link](https://app.bfzyapi.com/api.php/provide/vod) | ❌ | 4 | 26 | 13.3% | ❌❌❌❌❌❌❌ |
| ✅ | 杏吧资源 | - | [Link](https://xingba111.com/api.php/provide/vod) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 极速资源 | [Link](https://jszyapi.com) | [Link](https://jszyapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 森林资源 | - | [Link](https://slapibf.com/api.php/provide/vod) | ✅ | 9 | 21 | 30.0% | ❌❌✅❌❌❌❌ |
| 🚨 | 欧歌接口 | - | [Link](http://tv.nxog.top/m/111.php?ou=公众号欧歌app&mz=all&jar=all&b=欧歌) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 毒盒接口 | - | [Link](https://毒盒.com/tv/) | ❌ | 7 | 23 | 23.3% | ❌❌❌❌❌❌❌ |
| 🚨 | 淘片资源 | - | [Link](https://taopianapi.com/cjapi/sda/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 潇洒接口 | - | [Link](https://9877.kstore.space/AnotherD/api.json) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 爱坤资源(m3u8) | - | [Link](https://ikunzyapi.com/api.php/provide/vod/from/ikm3u8/at/json/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 爱短剧.cc | - | [Link](https://www.aiduanju.cc/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 王二小接口 | - | [Link](http://tvbox.王二小放牛娃.top) | ❌ | 28 | 2 | 93.3% | ✅✅❌✅✅✅✅ |
| ✅ | 真心接口 | - | [Link](https://www.252035.xyz/z/FongMi.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 短剧接口 | - | [Link](https://cnb.cool/fish2018/duanju/-/git/raw/main/tvbox.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 神马资源 | - | [Link](https://img.smdyw.top/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 私密影院 | - | [Link](https://simiyy.com/api.php/provide/vod/) | ❌ | 10 | 20 | 33.3% | ✅✅✅✅❌❌❌ |
| ✅ | 红牛资源 | - | [Link](https://www.hongniuzy3.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 红牛资源(m3u8) | - | [Link](https://www.hongniuzy2.com/api.php/provide/vod/from/hnm3u8/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 索尼-闪电资源 | - | [Link](https://xsd.sdzyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 细胞采集黄色 | - | [Link](https://www.xxibaozyw.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 耀协资源 | - | [Link](http://zyz.yxys.top/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 肥猫接口 | - | [Link](http://肥猫.com) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 菜妮丝接口 | - | [Link](https://tv.菜妮丝.top) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 蜂巢片库 | - | [Link](https://api.fczy888.me/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 辣椒资源黄黄 | - | [Link](https://apilj.com/api.php/provide) | ❌ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 速博资源 | - | [Link](https://subocaiji.com/api.php/provide/vod/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 道长接口 | - | [Link](https://cdn.gitmirror.com/bb/xduo/libs/master/index.json) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 量子资源 | - | [Link](https://cj.lziapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 量子资源(m3u8) | - | [Link](https://cj.lziapi.com/api.php/provide/vod/from/lzm3u8/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 金马资源网 | - | [Link](https://api.jmzy.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 金鹰资源(m3u8) | - | [Link](https://jyzyapi.com/provide/vod/from/jinyingm3u8/) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 金鹰资源采集网 | - | [Link](https://jyzyapi.com/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 闪电资源(m3u8) | - | [Link](https://sdzyapi.com/api.php/provide/vod/from/sdm3u8/) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 阿里源 | - | [Link](http://aliys.cn:90/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 雨哥哥资源 | - | [Link](http://cj.baozi66.top:66/api.php/provide/vod/) | ❌ | 25 | 5 | 83.3% | ✅✅✅✅✅✅✅ |
| 🚨 | 青龙接口 | - | [Link](https://gitee.com/yiwu369/6758/raw/master/%E9%9D%92%E9%BE%99/1.json) | ❌ | 7 | 23 | 23.3% | ❌❌❌❌❌❌❌ |
| ✅ | 非凡影视new | [Link](http://ffzy5.tv) | [Link](https://api.ffzyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 飘花资源 | - | [Link](http://www.ahjiuman.com/api.php/provide/vod/at/json) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 飞刀资源 | - | [Link](http://www.feidaozy.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 飞速资源 | - | [Link](https://www.feisuzyapi.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 飞速资源2 | - | [Link](http://fszy1.com/api.php/provide/vod/) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 飞速资源3 | - | [Link](https://m3u8.feisuzyapi.com/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 饭团影视 | - | [Link](https://www.fantuan.tv/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| 🚨 | 饭太硬接口 | - | [Link](http://www.饭太硬.com/tv) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 香雅情接口 | - | [Link](https://raw.githubusercontent.com/xyq254245/xyqonlinerule/main/XYQTVBox.json) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 驸马接口 | - | [Link](http://fmys.top/fmys.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 高天流云 | - | [Link](https:/raw.githubusercontent.com/gaotianliuyun/gao/master/js.json) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 魔爪资源 | - | [Link](https://mozhuazy.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 魔都影视 | - | [Link](https://www.moduzy.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 魔都资源 | - | [Link](https://www.mdzyapi.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 鸭鸭资源 | - | [Link](https://cj.yayazy.net/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 黄色资源啊啊 | - | [Link](https://hsckzy888.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 黑木耳资源 | - | [Link](https://json.heimuer.xyz/api.php/provide/vod/) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
<!-- API_TABLE_END -->





