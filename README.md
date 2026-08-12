# 2026骞村紑鍙戣€呬笓鐢ㄦ満鍦烘帹鑽?- GitHub/Docker/NPM鍔犻€熸寚鍗?
> 闈㈠悜绋嬪簭鍛樺拰寮€鍙戣€呯殑涓撲笟鏈哄満閫夋嫨鎸囧崡锛岃仛鐒︿唬鐮佷粨搴撹闂€侀暅鍍忓姞閫熴€丄PI璋冪敤浼樺寲绛夋牳蹇冮渶姹?
## 鐩綍

- [寮€鍙戣€呯殑缃戠粶鐥涚偣](#寮€鍙戣€呯殑缃戠粶鐥涚偣)
- [寮€鍙戣€呮満鍦洪€夋嫨鏍囧噯](#寮€鍙戣€呮満鍦洪€夋嫨鏍囧噯)
- [寮€鍙戣€呮満鍦烘帹鑽怾(#寮€鍙戣€呮満鍦烘帹鑽?
- [GitHub鍔犻€熷疄鎴榏(#github鍔犻€熷疄鎴?
- [Docker闀滃儚鍔犻€焆(#docker闀滃儚鍔犻€?
- [NPM/Pip/Gem鍔犻€熸柟妗圿(#npmpipgem鍔犻€熸柟妗?
- [CI/CD浼樺寲鎸囧崡](#cicd浼樺寲鎸囧崡)
- [甯哥敤寮€鍙戝伐鍏峰姞閫焆(#甯哥敤寮€鍙戝伐鍏峰姞閫?
- [甯歌闂](#甯歌闂)

---

## 寮€鍙戣€呯殑缃戠粶鐥涚偣

### 鏃ュ父寮€鍙戜腑鐨勭綉缁滈殰纰?
#### GitHub璁块棶闂

| 闂绫诲瀷 | 琛ㄧ幇 | 褰卞搷 |
|---------|------|------|
| **杩炴帴瓒呮椂** | git clone澶辫触 | 鏃犳硶鑾峰彇浠ｇ爜 |
| **閫熷害鎱?* | 鍏嬮殕閫熷害<10KB/s | 娴垂鏃堕棿 |
| **杩炴帴閲嶇疆** | push澶辫触 | 浠ｇ爜鎻愪氦鍙楅樆 |
| **楠岃瘉鐮?* | 棰戠箒楠岃瘉 | 褰卞搷鏁堢巼 |
| **Raw鏂囦欢** | 鏃犳硶璁块棶 | 璧勬簮鍔犺浇澶辫触 |

#### Docker闀滃儚鎷夊彇闂

```
閿欒绀轰緥锛?Error: pull access denied for xxx/image
or
unauthorized: authentication required
or
net/http: TLS handshake timeout
```

**褰卞搷**锛?- 鏋勫缓鏃堕棿寤堕暱锛堜粠鍒嗛挓鍒板皬鏃讹級
- CI/CD娴佺▼澶辫触
- 寮€鍙戞晥鐜囬檷浣?
#### 鍖呯鐞嗗櫒闂

| 鍖呯鐞嗗櫒 | 闂 | 褰卞搷 |
|---------|------|------|
| **NPM** | registry.npmjs.org璁块棶鎱?| 瀹夎渚濊禆瓒呮椂 |
| **Pip** | files.pythonhosted.org鎱?| Python鍖呭畨瑁呮參 |
| **Gem** | rubygems.org涓嶇ǔ瀹?| Ruby渚濊禆闂 |
| **Go** | proxy.golang.org鎱?| Go妯″潡涓嬭浇鎱?|
| **Maven** | repo.maven.apache.org鎱?| Java鏋勫缓鎱?|
| **NuGet** | api.nuget.org鎱?| .NET鍖呯鐞嗘參 |

### 寮€鍙戝満鏅綉缁滈渶姹?
#### 涓嶅悓鍦烘櫙鐨勫甫瀹?寤惰繜闇€姹?
| 鍦烘櫙 | 甯﹀闇€姹?| 寤惰繜瑕佹眰 | 娴侀噺浼扮畻 |
|------|---------|---------|---------|
| **Git鍏嬮殕/鎺ㄩ€?* | 10-50Mbps | <200ms | 1-5GB/澶?|
| **Docker鏋勫缓** | 50-100Mbps | <300ms | 5-20GB/澶?|
| **鍖呭畨瑁?* | 20-50Mbps | <300ms | 1-3GB/澶?|
| **鏂囨。鏌ラ槄** | 5-10Mbps | <500ms | 100MB/澶?|
| **瑙嗛浼氳** | 5-10Mbps | <100ms | 500MB/澶?|
| **API璋冪敤** | 1-5Mbps | <100ms | 50MB/澶?|

---

## 寮€鍙戣€呮満鍦洪€夋嫨鏍囧噯

### 浜斿ぇ鏍稿績鎸囨爣

#### 1. GitHub璁块棶璐ㄩ噺

**娴嬭瘯鏂规硶**锛?
```bash
# 娴嬭瘯Git鍏嬮殕閫熷害
time git clone --depth=1 https://github.com/torvalds/linux.git

# 娴嬭瘯API寤惰繜
curl -w "@curl-format.txt" -o /dev/null -s https://api.github.com

# curl-format.txt鍐呭锛?time_namelookup:  %{time_namelookup}\n
time_connect:  %{time_connect}\n
time_appconnect:  %{time_appconnect}\n
time_starttransfer:  %{time_starttransfer}\n
time_total:  %{time_total}\n
```

**璇勫垎鏍囧噯**锛?
| 鎸囨爣 | 浼樼 | 鍚堟牸 | 杈冨樊 |
|------|------|------|------|
| 鍏嬮殕閫熷害 | >1MB/s | 100KB-1MB/s | <100KB/s |
| API寤惰繜 | <200ms | 200-500ms | >500ms |
| 鎴愬姛鐜?| >99% | 95-99% | <95% |

#### 2. Docker闀滃儚鎷夊彇閫熷害

**娴嬭瘯鑴氭湰**锛?
```bash
#!/bin/bash
# Docker鎷夊彇閫熷害娴嬭瘯

images=(
  "nginx:alpine"
  "node:18-alpine"
  "python:3.11-slim"
  "golang:1.21-alpine"
)

for img in "${images[@]}"; do
  echo "Testing $img..."
  start=$(date +%s.%N)
  docker pull $img
  end=$(date +%s.%N)
  duration=$(echo "$end - $start" | bc)
  echo "Time: ${duration}s"
  echo "---"
done
```

**璇勫垎鏍囧噯**锛?
| 闀滃儚澶у皬 | 浼樼鏃堕棿 | 鍚堟牸鏃堕棿 | 杈冨樊鏃堕棿 |
|---------|---------|---------|---------|
| <100MB | <10s | 10-30s | >30s |
| 100-500MB | <30s | 30-60s | >60s |
| >500MB | <60s | 60-120s | >120s |

#### 3. 鍖呯鐞嗗櫒鍔犻€?
**娴嬭瘯鍛戒护**锛?
```bash
# NPM
time npm install express --registry=https://registry.npmjs.org

# Pip
time pip install requests -i https://pypi.org/simple

# Go
time go get github.com/gin-gonic/gin

# Maven
time mvn dependency:resolve
```

#### 4. 绋冲畾鎬?
**寮€鍙戣€呯ǔ瀹氭€ц姹?*锛?
- **鍦ㄧ嚎鐜?*锛?99.5%锛堝厑璁稿伓灏旂淮鎶わ級
- **鏅氶珮宄拌〃鐜?*锛氶€熷害涓嶆樉钁椾笅闄?- **鏂嚎棰戠巼**锛?1娆?鍛?- **鎭㈠閫熷害**锛?5鍒嗛挓鑷姩鎭㈠

#### 5. 娴侀噺鎴愭湰

**寮€鍙戣€呮祦閲忎及绠?*锛?
```
鏃ュ父寮€鍙戞祦閲忔秷鑰楋紙鏈堬級锛?- Git鎿嶄綔锛?0-30GB
- Docker鏋勫缓锛?0-100GB
- 鍖呯鐞嗭細10-30GB
- 鏂囨。/鎼滅储锛?-10GB
- 鎬昏锛?5-170GB/鏈?```

**鎺ㄨ崘濂楅**锛?- 杞诲害寮€鍙戣€咃細100GB/鏈堬紙30鍏冿級
- 涓害寮€鍙戣€咃細200GB/鏈堬紙50鍏冿級
- 閲嶅害寮€鍙戣€咃細500GB/鏈堬紙80鍏冿級

---

## 寮€鍙戣€呮満鍦烘帹鑽?
### 馃捇 ClashVIP寮€鍙戣€呭椁?
**瀹樼綉**锛歨ttps://clashvip.net

#### 寮€鍙戣€呬笓鐢ㄧ壒鎬?
| 椤圭洰 | 閰嶇疆 |
|------|------|
| **鑺傜偣浼樺寲** | GitHub/Docker/NPM涓撶嚎 |
| **甯﹀** | 100Mbps璧?|
| **娴侀噺** | 100-500GB/鏈?|
| **浠锋牸** | 35-99鍏?鏈?|
| **鏀寔** | 寮€鍙戣€呬紭鍏堝鏈?|
| **绋冲畾鎬?* | 99.9%鍦ㄧ嚎鐜?|

#### 寮€鍙戣€呰妭鐐?
**GitHub浼樺寲鑺傜偣**锛?- 棣欐腐鑺傜偣锛氱洿杩濭itHub CDN
- 鏂板姞鍧¤妭鐐癸細浣庡欢杩烝PI璁块棶
- 鏃ユ湰鑺傜偣锛氱ǔ瀹歊aw鏂囦欢璁块棶

**Docker鍔犻€熻妭鐐?*锛?- 缇庤タ鑺傜偣锛欴ocker Hub鐩磋繛
- 鏂板姞鍧¤妭鐐癸細浜氭床闀滃儚鍔犻€?- 棣欐腐鑺傜偣锛氭贩鍚堝姞閫?
#### 瀹炴祴鏁版嵁

| 娴嬭瘯椤?| 寤惰繜/閫熷害 | 璇勫垎 |
|--------|----------|------|
| Git clone Linux鍐呮牳 | 2.5MB/s | 猸愨瓙猸愨瓙猸?|
| Docker pull nginx | 8绉?| 猸愨瓙猸愨瓙猸?|
| NPM install express | 3绉?| 猸愨瓙猸愨瓙猸?|
| GitHub API寤惰繜 | 120ms | 猸愨瓙猸愨瓙 |
| Raw鏂囦欢璁块棶 | 200ms | 猸愨瓙猸愨瓙 |

#### 涓轰粈涔堟帹鑽怌lashVIP寮€鍙戣€呭椁愶紵

1. **GitHub涓撶嚎浼樺寲**锛氱洿杩濭itHub CDN锛屽厠闅嗛€熷害>1MB/s
2. **Docker鍔犻€?*锛氭敮鎸丏ocker Hub闀滃儚鍔犻€?3. **澶氳妭鐐规敮鎸?*锛氶娓?鏂板姞鍧?鏃ユ湰/缇庡浗锛岃鐩栧叏鐞冩湇鍔?4. **娴侀噺鍏呰冻**锛?00GB璧凤紝婊¤冻鏃ュ父寮€鍙戦渶姹?5. **鎬т环姣旈珮**锛?5鍏?鏈堣捣锛屾瘮鑷缓VPS渚垮疁

---

## GitHub鍔犻€熷疄鎴?
### GitHub璁块棶浼樺寲閰嶇疆

#### Clash瑙勫垯閰嶇疆

```yaml
# GitHub鍔犻€熻鍒?rules:
  # GitHub涓荤珯
  - DOMAIN-SUFFIX,github.com,棣欐腐鑺傜偣
  - DOMAIN-SUFFIX,github.io,棣欐腐鑺傜偣
  - DOMAIN-SUFFIX,githubapp.com,棣欐腐鑺傜偣
  - DOMAIN-SUFFIX,githubassets.com,棣欐腐鑺傜偣
  - DOMAIN-SUFFIX,githubusercontent.com,棣欐腐鑺傜偣

  # GitHub API
  - DOMAIN-SUFFIX,api.github.com,鏂板姞鍧¤妭鐐?
  # GitHub Raw
  - DOMAIN-SUFFIX,raw.githubusercontent.com,鏃ユ湰鑺傜偣
  - DOMAIN-SUFFIX,camo.githubusercontent.com,鏃ユ湰鑺傜偣

  # GitHub Pages
  - DOMAIN-SUFFIX,github.io,棣欐腐鑺傜偣

  # GitHub CDN
  - DOMAIN-SUFFIX,github.githubassets.com,棣欐腐鑺傜偣

  # 鍏朵粬瑙勫垯
  - MATCH,PROXY
```

#### Git閰嶇疆浼樺寲

```bash
# Git浠ｇ悊閰嶇疆锛堟湰鍦颁唬鐞嗭級
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890

# 鎴栦娇鐢⊿SH鏂瑰紡锛堟帹鑽愶級
# 閰嶇疆~/.ssh/config
Host github.com
  HostName github.com
  User git
  ProxyCommand nc -X 5 -x 127.0.0.1:7890 %h %p
```

#### GitHub SSH鍔犻€?
**SSH閰嶇疆**锛坄~/.ssh/config`锛夛細

```
# GitHub SSH閫氳繃浠ｇ悊杩炴帴
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
  ProxyCommand nc -v -x 127.0.0.1:7890 %h %p

# 鎴栦娇鐢–onnect宸ュ叿锛圵indows锛?Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
  ProxyCommand "C:/Program Files/Git/mingw64/bin/connect.exe" -S 127.0.0.1:7890 %h %p
```

**娴嬭瘯杩炴帴**锛?
```bash
ssh -T git@github.com
# 鎴愬姛杈撳嚭锛欻i username! You've successfully authenticated...
```

### GitHub鍏嬮殕閫熷害浼樺寲

#### 鏂规硶1锛氫娇鐢ㄦ祬鍏嬮殕

```bash
# 浠呭厠闅嗘渶杩戜竴娆℃彁浜?git clone --depth=1 https://github.com/user/repo.git

# 鍚庣画闇€瑕佸巻鍙叉椂鍐嶆媺鍙?git fetch --unshallow
```

#### 鏂规硶2锛氫娇鐢ㄩ暅鍍忕珯鐐?
```bash
# 浣跨敤GitHub闀滃儚
git clone https://github.com.cnpmjs.org/user/repo.git
# 鎴?git clone https://hub.fastgit.org/user/repo.git
```

#### 鏂规硶3锛氬崟鏂囦欢涓嬭浇

```bash
# 浣跨敤curl浠ｇ悊涓嬭浇鍗曚釜鏂囦欢
curl -x http://127.0.0.1:7890 \
  -L https://raw.githubusercontent.com/user/repo/main/file.txt \
  -o file.txt
```

#### 鏂规硶4锛欸it clone鍔犻€熻剼鏈?
```bash
#!/bin/bash
# GitHub鍔犻€熷厠闅嗚剼鏈?
url=$1
proxy="http://127.0.0.1:7890"

if [[ $url == *"github.com"* ]]; then
  # 浣跨敤浠ｇ悊鍏嬮殕
  echo "浣跨敤浠ｇ悊鍏嬮殕..."
  git clone -c http.proxy=$proxy $url
else
  git clone $url
fi
```

### GitHub API璁块棶浼樺寲

#### API閫熺巼闄愬埗

| 璁よ瘉鏂瑰紡 | 閫熺巼闄愬埗 | 閫傜敤鍦烘櫙 |
|---------|---------|---------|
| 鏈璇?| 60娆?灏忔椂 | 鍏紑淇℃伅 |
| Basic Auth | 5000娆?灏忔椂 | 涓汉浣跨敤 |
| OAuth Token | 5000娆?灏忔椂 | 搴旂敤闆嗘垚 |

#### API璋冪敤浼樺寲

```bash
# 閰嶇疆GitHub Token
export GITHUB_TOKEN=your_token_here

# 浣跨敤Token璋冪敤API
curl -H "Authorization: token $GITHUB_TOKEN" \
  -x http://127.0.0.1:7890 \
  https://api.github.com/user/repos

# 鎴栭厤缃瓽it浣跨敤Token
git config --global credential.helper store
# 鍦▇/.git-credentials涓坊鍔狅細
# https://username:token@github.com
```

---

## Docker闀滃儚鍔犻€?
### Docker鍔犻€熸柟妗堝姣?
| 鏂规 | 浼樺娍 | 鍔ｅ娍 | 鎺ㄨ崘搴?|
|------|------|------|--------|
| **鏈哄満浠ｇ悊** | 鐏垫椿銆佺ǔ瀹?| 闇€閰嶇疆 | 猸愨瓙猸愨瓙猸?|
| **闀滃儚鍔犻€熷櫒** | 瀹樻柟鏀寔 | 閮ㄥ垎澶辨晥 | 猸愨瓙猸愨瓙 |
| **闀滃儚绔?* | 鍏嶈垂 | 涓嶇ǔ瀹?| 猸愨瓙猸?|
| **鑷缓Registry** | 鍙帶 | 鎴愭湰楂?| 猸愨瓙 |

### Docker浠ｇ悊閰嶇疆

#### Docker Desktop锛圵indows/Mac锛?
**閰嶇疆璺緞**锛?- Windows锛歚C:\Users\Administrator\.docker\daemon.json`
- Mac锛歚~/.docker/daemon.json`

**閰嶇疆鍐呭**锛?
```json
{
  "registry-mirrors": [
    "https://docker.mirrors.sjtug.sjtu.edu.cn",
    "https://docker.m.daocloud.io",
    "https://mirror.ccs.tencentyun.com"
  ],
  "proxies": {
    "default": {
      "httpProxy": "http://127.0.0.1:7890",
      "httpsProxy": "http://127.0.0.1:7890",
      "noProxy": "localhost,127.0.0.1,.local"
    }
  },
  "insecure-registries": [],
  "debug": false,
  "experimental": false
}
```

#### Docker Engine锛圠inux锛?
**閰嶇疆鏂囦欢**锛歚/etc/docker/daemon.json`

```json
{
  "registry-mirrors": [
    "https://docker.mirrors.sjtug.sjtu.edu.cn",
    "https://docker.m.daocloud.io"
  ],
  "proxies": {
    "default": {
      "httpProxy": "http://127.0.0.1:7890",
      "httpsProxy": "http://127.0.0.1:7890",
      "noProxy": "localhost,127.0.0.1,10.*,192.168.*"
    }
  }
}
```

**閲嶅惎Docker**锛?
```bash
sudo systemctl daemon-reload
sudo systemctl restart docker
```

#### Docker Pull娴嬭瘯

```bash
# 娴嬭瘯鎷夊彇閫熷害
time docker pull nginx:alpine

# 鏌ョ湅闀滃儚鏉ユ簮
docker inspect nginx:alpine | grep -i registry
```

### Docker闀滃儚婧愬垪琛?
#### 鍥藉唴闀滃儚婧?
| 闀滃儚婧?| 鍦板潃 | 鐘舵€?|
|--------|------|------|
| 涓婃捣浜ゅぇ | https://docker.mirrors.sjtug.sjtu.edu.cn | 鉁?绋冲畾 |
| DaoCloud | https://docker.m.daocloud.io | 鉁?绋冲畾 |
| 鑵捐浜?| https://mirror.ccs.tencentyun.com | 鉁?绋冲畾 |
| 涓澶?| https://docker.mirrors.ustc.edu.cn | 鈿狅笍 鏃跺ソ鏃跺潖 |
| 闃块噷浜?| https://[浣犵殑ID].mirror.aliyuncs.com | 鉁?闇€娉ㄥ唽 |

#### 閰嶇疆绀轰緥

```json
{
  "registry-mirrors": [
    "https://docker.mirrors.sjtug.sjtu.edu.cn",
    "https://docker.m.daocloud.io",
    "https://mirror.ccs.tencentyun.com"
  ]
}
```

### Docker Compose鍔犻€?
#### docker-compose.yml閰嶇疆

```yaml
version: '3.8'

services:
  app:
    image: node:18-alpine
    build:
      context: .
      args:
        - HTTP_PROXY=http://host.docker.internal:7890
        - HTTPS_PROXY=http://host.docker.internal:7890
    environment:
      - HTTP_PROXY=http://host.docker.internal:7890
      - HTTPS_PROXY=http://host.docker.internal:7890
      - NO_PROXY=localhost,127.0.0.1
```

**娉ㄦ剰**锛?- `host.docker.internal`锛欴ocker Desktop鑷姩瑙ｆ瀽鍒板涓绘満
- Linux闇€瑕佹坊鍔狅細`extra_hosts: ["host.docker.internal:host-gateway"]`

---

## NPM/Pip/Gem鍔犻€熸柟妗?
### NPM鍔犻€?
#### 鏂规硶1锛氫娇鐢ㄥ浗鍐呴暅鍍忔簮

```bash
# 涓存椂浣跨敤
npm install package-name --registry=https://registry.npmmirror.com

# 姘镐箙閰嶇疆
npm config set registry https://registry.npmmirror.com

# 鎭㈠瀹樻柟婧?npm config set registry https://registry.npmjs.org

# 鏌ョ湅褰撳墠婧?npm config get registry
```

#### 鏂规硶2锛氫娇鐢ㄤ唬鐞?
```bash
# 閰嶇疆浠ｇ悊
npm config set proxy http://127.0.0.1:7890
npm config set https-proxy http://127.0.0.1:7890

# 鍙栨秷浠ｇ悊
npm config delete proxy
npm config delete https-proxy
```

#### 鏂规硶3锛氫娇鐢╪rm绠＄悊婧?
```bash
# 瀹夎nrm
npm install -g nrm

# 鏌ョ湅鍙敤婧?nrm ls

# 鍒囨崲婧?nrm use taobao

# 娴嬭瘯閫熷害
nrm test

# 娣诲姞鑷畾涔夋簮
nrm add company http://npm.company.com
```

#### 甯哥敤NPM闀滃儚婧?
| 婧愬悕绉?| 鍦板潃 | 璇存槑 |
|--------|------|------|
| 娣樺疂闀滃儚 | https://registry.npmmirror.com | 鎺ㄨ崘锛岀ǔ瀹?|
| 鍗庝负浜?| https://repo.huaweicloud.com/repository/npm/ | 澶囩敤 |
| 鑵捐浜?| https://mirrors.cloud.tencent.com/npm/ | 澶囩敤 |
| 瀹樻柟婧?| https://registry.npmjs.org | 闇€浠ｇ悊 |

### Pip鍔犻€?
#### 鏂规硶1锛氫复鏃朵娇鐢ㄩ暅鍍忔簮

```bash
# 鍗曟浣跨敤
pip install package-name -i https://pypi.tuna.tsinghua.edu.cn/simple

# 鎴栦娇鐢ㄥ畬鏁碪RL
pip install package-name --index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

#### 鏂规硶2锛氭案涔呴厤缃?
**閰嶇疆鏂囦欢**锛?- Linux/Mac锛歚~/.pip/pip.conf`
- Windows锛歚C:\Users\Administrator\pip\pip.ini`

**閰嶇疆鍐呭**锛?
```ini
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
trusted-host = pypi.tuna.tsinghua.edu.cn

# 澶囩敤婧?# index-url = https://mirrors.aliyun.com/pypi/simple/
# trusted-host = mirrors.aliyun.com
```

#### 鏂规硶3锛氫娇鐢ㄤ唬鐞?
```bash
# 涓存椂浠ｇ悊
pip install package-name --proxy http://127.0.0.1:7890

# 鐜鍙橀噺
export HTTP_PROXY=http://127.0.0.1:7890
export HTTPS_PROXY=http://127.0.0.1:7890
pip install package-name
```

#### 甯哥敤Pip闀滃儚婧?
| 婧愬悕绉?| 鍦板潃 | 璇存槑 |
|--------|------|------|
| 娓呭崕闀滃儚 | https://pypi.tuna.tsinghua.edu.cn/simple | 鎺ㄨ崘 |
| 闃块噷浜?| https://mirrors.aliyun.com/pypi/simple/ | 绋冲畾 |
| 鍗庝负浜?| https://repo.huaweicloud.com/repository/pypi/simple | 澶囩敤 |
| 鑵捐浜?| https://mirrors.cloud.tencent.com/pypi/simple | 澶囩敤 |

### Go妯″潡鍔犻€?
#### Go浠ｇ悊閰嶇疆

```bash
# 璁剧疆Go浠ｇ悊
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct

# 鎴栦娇鐢ㄤ竷鐗涗簯
go env -w GOPROXY=https://goproxy.io,direct

# 鎴栦娇鐢ㄩ樋閲屼簯
go env -w GOPROXY=https://mirrors.aliyun.com/goproxy/,direct

# 鏌ョ湅閰嶇疆
go env GOPROXY
```

#### 甯哥敤Go浠ｇ悊

| 浠ｇ悊 | 鍦板潃 | 璇存槑 |
|------|------|------|
| 涓冪墰浜?| https://goproxy.cn | 鎺ㄨ崘 |
| 闃块噷浜?| https://mirrors.aliyun.com/goproxy/ | 澶囩敤 |
| 瀹樻柟 | https://proxy.golang.org | 闇€浠ｇ悊 |
| 鐩磋繛 | direct | 涓嶄娇鐢ㄤ唬鐞?|

### Maven鍔犻€?
#### Maven閰嶇疆

**閰嶇疆鏂囦欢**锛歚~/.m2/settings.xml`

```xml
<settings>
  <mirrors>
    <mirror>
      <id>aliyun</id>
      <name>Aliyun Maven</name>
      <url>https://maven.aliyun.com/repository/public</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>huawei</id>
      <name>Huawei Maven</name>
      <url>https://repo.huaweicloud.com/repository/maven/</url>
      <mirrorOf>central</mirrorOf>
    </mirror>
  </mirrors>

  <proxies>
    <proxy>
      <id>clash</id>
      <active>true</active>
      <protocol>http</protocol>
      <host>127.0.0.1</host>
      <port>7890</port>
    </proxy>
  </proxies>
</settings>
```

---

## CI/CD浼樺寲鎸囧崡

### GitHub Actions浼樺寲

#### 浣跨敤浠ｇ悊鐨凣itHub Actions

```yaml
name: CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          registry-url: 'https://registry.npmmirror.com'

      - name: Install dependencies
        run: npm install
        env:
          NODE_CONFIG_CACHE: /tmp/npm-cache

      - name: Build
        run: npm run build
```

#### 浣跨敤Self-hosted Runner

```yaml
jobs:
  build:
    runs-on: self-hosted  # 浣跨敤鑷墭绠unner

    steps:
      - name: Checkout
        uses: actions/checkout@v3

      # Runner宸查厤缃唬鐞嗭紝鏃犻渶棰濆閰嶇疆
      - name: Build
        run: npm run build
```

### GitLab CI/CD浼樺寲

#### .gitlab-ci.yml閰嶇疆

```yaml
variables:
  HTTP_PROXY: http://proxy.company.com:7890
  HTTPS_PROXY: http://proxy.company.com:7890
  NO_PROXY: localhost,127.0.0.1

stages:
  - build
  - test
  - deploy

build:
  stage: build
  image: node:18-alpine
  before_script:
    - npm config set registry https://registry.npmmirror.com
  script:
    - npm install
    - npm run build
  cache:
    paths:
      - node_modules/

test:
  stage: test
  image: node:18-alpine
  script:
    - npm test
  dependencies:
    - build
```

### Jenkins Pipeline浼樺寲

#### Jenkinsfile閰嶇疆

```groovy
pipeline {
  agent {
    docker {
      image 'node:18-alpine'
      args '-e HTTP_PROXY=http://proxy:7890 -e HTTPS_PROXY=http://proxy:7890'
    }
  }

  environment {
    NPM_CONFIG_REGISTRY = 'https://registry.npmmirror.com'
  }

  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }

  post {
    always {
      cleanWs()
    }
  }
}
```

---

## 甯哥敤寮€鍙戝伐鍏峰姞閫?
### VS Code鍔犻€?
#### 璁剧疆浠ｇ悊

**settings.json**锛?
```json
{
  "http.proxy": "http://127.0.0.1:7890",
  "http.proxyStrictSSL": false,
  "http.proxySupport": "on"
}
```

#### 鎵╁睍甯傚満鍔犻€?
```json
{
  "extensions.autoUpdate": true,
  "extensions.autoCheckUpdates": true,
  "extensions.ignoreRecommendations": false
}
```

### JetBrains IDE鍔犻€?
#### IDEA浠ｇ悊閰嶇疆

**Settings 鈫?Appearance & Behavior 鈫?System Settings 鈫?HTTP Proxy**锛?
- Proxy host: `127.0.0.1`
- Proxy port: `7890`
- Proxy authentication: 鏃犻渶锛堟湰鍦颁唬鐞嗭級

#### Maven閰嶇疆

鍦↖DEA涓厤缃甅aven浣跨敤闀滃儚婧愶細
- Settings 鈫?Build, Execution, Deployment 鈫?Build Tools 鈫?Maven
- 璁剧疆User settings file: `~/.m2/settings.xml`

### Terminal浠ｇ悊閰嶇疆

#### Bash閰嶇疆锛垀/.bashrc锛?
```bash
# 浠ｇ悊閰嶇疆
export http_proxy="http://127.0.0.1:7890"
export https_proxy="http://127.0.0.1:7890"
export HTTP_PROXY="http://127.0.0.1:7890"
export HTTPS_PROXY="http://127.0.0.1:7890"
export no_proxy="localhost,127.0.0.1,localaddress,.localdomain.com"
export NO_PROXY="localhost,127.0.0.1,localaddress,.localdomain.com"

# 蹇嵎鍛戒护
alias proxy='export http_proxy=http://127.0.0.1:7890 https_proxy=http://127.0.0.1:7890'
alias unproxy='unset http_proxy https_proxy'
alias testproxy='curl -I https://www.google.com'
```

#### Zsh閰嶇疆锛垀/.zshrc锛?
```bash
# 浠ｇ悊閰嶇疆
export http_proxy="http://127.0.0.1:7890"
export https_proxy="http://127.0.0.1:7890"

# 蹇嵎鍑芥暟
proxy() {
  export http_proxy="http://127.0.0.1:7890"
  export https_proxy="http://127.0.0.1:7890"
  echo "Proxy enabled"
}

noproxy() {
  unset http_proxy
  unset https_proxy
  echo "Proxy disabled"
}
```

#### PowerShell閰嶇疆锛?PROFILE锛?
```powershell
# 浠ｇ悊閰嶇疆
$env:http_proxy = "http://127.0.0.1:7890"
$env:https_proxy = "http://127.0.0.1:7890"

# 蹇嵎鍑芥暟
function Set-Proxy {
  $env:http_proxy = "http://127.0.0.1:7890"
  $env:https_proxy = "http://127.0.0.1:7890"
  Write-Host "Proxy enabled"
}

function Remove-Proxy {
  $env:http_proxy = $null
  $env:https_proxy = $null
  Write-Host "Proxy disabled"
}

# 鍒悕
Set-Alias proxy Set-Proxy
Set-Alias noproxy Remove-Proxy
```

---

## 甯歌闂

### Q: Git鍏嬮殕閫熷害寰堟參鎬庝箞鍔烇紵

**瑙ｅ喅鏂规**锛?
1. **浣跨敤娴呭厠闅?*
   ```bash
   git clone --depth=1 https://github.com/user/repo.git
   ```

2. **閰嶇疆浠ｇ悊**
   ```bash
   git config --global http.proxy http://127.0.0.1:7890
   ```

3. **浣跨敤SSH鏂瑰紡**
   ```bash
   git clone git@github.com:user/repo.git
   ```

4. **浣跨敤闀滃儚绔?*
   ```bash
   git clone https://hub.fastgit.org/user/repo.git
   ```

### Q: Docker鎷夊彇闀滃儚澶辫触鎬庝箞鍔烇紵

**鎺掓煡姝ラ**锛?
1. **妫€鏌ヤ唬鐞嗛厤缃?*
   ```bash
   cat /etc/docker/daemon.json
   ```

2. **娴嬭瘯浠ｇ悊杩炴帴**
   ```bash
   curl -x http://127.0.0.1:7890 https://registry-1.docker.io/v2/
   ```

3. **鏌ョ湅Docker鏃ュ織**
   ```bash
   journalctl -u docker.service
   ```

4. **閲嶅惎Docker**
   ```bash
   sudo systemctl restart docker
   ```

### Q: NPM瀹夎渚濊禆澶辫触锛?
**瑙ｅ喅鏂规**锛?
1. **鍒囨崲闀滃儚婧?*
   ```bash
   npm config set registry https://registry.npmmirror.com
   ```

2. **娓呴櫎缂撳瓨**
   ```bash
   npm cache clean --force
   ```

3. **鍒犻櫎node_modules**
   ```bash
   rm -rf node_modules package-lock.json
   npm install
   ```

4. **浣跨敤yarn**
   ```bash
   yarn install --registry https://registry.npmmirror.com
   ```

### Q: 濡備綍娴嬭瘯鏈哄満鐨勫紑鍙戣€呭姛鑳斤紵

**娴嬭瘯娓呭崟**锛?
```bash
# 1. Git鍏嬮殕娴嬭瘯
time git clone --depth=1 https://github.com/torvalds/linux.git /tmp/test

# 2. Docker鎷夊彇娴嬭瘯
time docker pull nginx:alpine

# 3. NPM瀹夎娴嬭瘯
time npm install express

# 4. API寤惰繜娴嬭瘯
curl -w "Time: %{time_total}s\n" https://api.github.com

# 5. Raw鏂囦欢璁块棶
time curl https://raw.githubusercontent.com/github/gitignore/main/Node.gitignore
```

### Q: 寮€鍙戣€呴渶瑕佸澶ф祦閲忥紵

**娴侀噺浼扮畻琛?*锛?
| 浣跨敤棰戠巼 | Git鎿嶄綔 | Docker | 鍖呯鐞?| 鏂囨。鏌ラ槄 | 鎬昏 |
|---------|--------|--------|--------|---------|------|
| 杞诲害 | 5GB/鏈?| 20GB/鏈?| 5GB/鏈?| 2GB/鏈?| 32GB/鏈?|
| 涓害 | 15GB/鏈?| 50GB/鏈?| 15GB/鏈?| 5GB/鏈?| 85GB/鏈?|
| 閲嶅害 | 30GB/鏈?| 100GB/鏈?| 30GB/鏈?| 10GB/鏈?| 170GB/鏈?|

**寤鸿**锛?- 涓汉寮€鍙戣€咃細100GB/鏈?- 鍥㈤槦寮€鍙戯細200GB/鏈?- CI/CD瀵嗛泦锛?00GB/鏈?
---

## 鐩稿叧璧勬簮

- **ClashVIP寮€鍙戣€呭椁?*锛歨ttps://clashvip.net
- **鏈哄満瀵艰埅**锛歨ttps://nav.clashvip.net
- **鎶€鏈ぞ鍖?*锛歨ttps://bbs.clashhub.net
- **VPS鎺ㄨ崘**锛歨ttps://vpsvip.net锛堣嚜寤烘柟妗堬級

---

## 鍏嶈矗澹版槑

1. 鏈粨搴撲粎鎻愪緵寮€鍙戣€呯綉缁滀紭鍖栨妧鏈俊鎭?2. 璇烽伒瀹堝悇骞冲彴鏈嶅姟鏉℃浣跨敤缃戠粶鏈嶅姟
3. 浠ｇ爜浠撳簱鍜岄暅鍍忚閬靛畧寮€婧愬崗璁?4. 璇峰嬁鐢ㄤ簬浠讳綍杩濇硶鐢ㄩ€?
---

## 璁稿彲璇?
MIT License

---

**鏇存柊鏃堕棿**锛?026-08-12
**涓婚**锛氬紑鍙戣€呬笓鐢ㄦ満鍦烘帹鑽?- GitHub/Docker/NPM鍔犻€熸寚鍗?**瀛楄妭鏁?*锛氱害18000瀛楄妭