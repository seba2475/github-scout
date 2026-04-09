# GitHub Scout

這是一個用 Vue 3 製作的小網站。使用者輸入 GitHub 帳號後，可以查詢該使用者的公開資料，包含大頭貼、名稱、簡介與 GitHub 個人頁面。

## 我問 AI 什麼問題來理解程式碼？

我有問 AI 下面這些問題來幫助自己理解：

1. 哪一行程式碼是在記住我輸入的 GitHub 名字？
2. 按下查詢按鈕後，程式是怎麼開始找資料的？
3. 「查無此人」這句話是由哪一段程式碼控制出現的？
4. 為什麼找到資料後，照片和名稱才會顯示出來？

## AI 用了什麼比喻幫我理解？

AI 用了幾個很好懂的比喻：

- 輸入框像把資料放進一個盒子
- 按鈕像開關，按下去就開始做事
- 條件判斷像守門員，決定哪些內容可以出現在畫面上
- 畫面更新像公告欄，資料變了，公告欄也跟著更新

## 功能

- 輸入 GitHub 帳號
- 查詢 GitHub 使用者公開資料
- 顯示大頭貼、名稱、簡介、GitHub 連結
- 空白輸入時提示
- 查不到使用者時提示

## 執行方式

```bash
npm install
npm run dev

已上傳的圖像
已上傳的圖像
已上傳的圖像
已上傳的圖像
已上傳的圖像
參考網址https://zh-hk.vuejs.org/guide/quick-start.html    幫我完成

已思考 18s
可以，我直接幫你整理成可交作業版本。
你這份作業重點其實有三塊：

用 Vue 3 建專案

留下你跟 AI 的對話痕跡

交 README.md + docs/PLAN.md + GitHub 連結

根據 Vue 官方 quick start，本地建立 Vue 專案前要先有 Node.js 18.3 以上，建立專案可用 npm create vue@latest，之後進專案資料夾執行 npm install 和 npm run dev。

一、先做專案建立指令
你在終端機輸入：

npm create vue@latest
接著建議你這樣選：

Project name: github-scout
Add TypeScript? No
Add JSX Support? No
Add Vue Router for Single Page Application development? No
Add Pinia for state management? No
Add Vitest for Unit testing? No
Add an End-to-End Testing Solution? No
Add ESLint for code quality? Yes
Add Prettier for code formatting? Yes
Add Vue DevTools 7 extension for debugging? No
Vue 官方文件有列出 create-vue 會詢問的這些選項；如果不確定，直接選 No 也可以。建立完後再執行 cd <project-name>、npm install、npm run dev 啟動開發伺服器。

接著：

cd github-scout
npm install
npm run dev
二、你可以直接貼給 AI 的初始化指令
這段很符合你作業第一階段：

/init "建立一個 Vue 3 專案『GitHub Scout』。寫入 AGENTS.md：
1. 我是大二初學者，只懂 HTML。
2. 你是我的私人導師，禁止對我使用 Vue 的專業術語（例如 ref、reactive、lifecycle、composition API），請改用生活化比喻，像是『盒子』『開關』『記憶格子』。
3. 每次只能講一小段，先講做什麼，再講原因。
4. 寫程式時每一段都加上白話註解。
5. 當我問『哪一行在控制這個功能』時，你要直接指出那一行程式碼，並用國中生聽得懂的方式解釋。
6. 如果有錯誤，先說錯在哪裡，再教我怎麼改，不要一次丟太多內容。"
三、Phase 2 對話內容，我幫你寫好
你作業要的是「對話紀錄」，所以你可以照下面這些句子去問 AI。

1）Plan 模式可直接貼
請跟我討論這個網頁的步驟。如果我在輸入框打字，按下按鈕，到照片出現，中間經過了哪些關卡？請用小學生的語言解釋，並把步驟寫進 docs/PLAN.md。
2）Build 模式可直接貼
按照第一步把畫面做出來。畫面需要有：
1. 一個輸入 GitHub 使用者名稱的輸入框
2. 一個查詢按鈕
3. 找到使用者時顯示大頭貼、名稱、個人簡介、GitHub 連結
4. 找不到使用者時顯示「查無此人」
5. 請在每一段程式碼旁邊加白話註解
6. 做完後告訴我：哪一行程式碼是在「記住」我輸入的名字？
3）Refine / Debug 可直接貼
請幫我微調：
1. 照片改成圓形
2. 加深色背景
3. 卡片加陰影和圓角
4. 如果輸入空白，不要送出，顯示「請先輸入 GitHub 帳號」
5. 如果查不到人，顯示「查無此人」
6. 請教我：是哪一段程式碼在控制這些提示文字什麼時候出現？
四、可直接交的 docs/PLAN.md
把下面內容存成 docs/PLAN.md：

# GitHub Scout Plan

這個小網站的流程，可以想成「查名字找人」：

1. 使用者先在輸入框打入 GitHub 帳號。
2. 網頁把這個名字先記住，像把紙條放進小盒子裡。
3. 使用者按下查詢按鈕。
4. 程式檢查盒子裡有沒有名字。
5. 如果是空的，就直接提醒「請先輸入 GitHub 帳號」。
6. 如果有名字，程式就去 GitHub 的公開網址找這個人。
7. 等待資料回來時，畫面可以先顯示「查詢中」。
8. 如果真的找到人，就把照片、名字、簡介、個人頁面顯示出來。
9. 如果找不到人，就顯示「查無此人」。
10. 每查一次，都是「輸入名字 → 按按鈕 → 檢查 → 去找資料 → 顯示結果」這樣的流程。

## 我學到的重點

- 輸入框不是直接變成結果，它只是先把資料交給程式記住。
- 按鈕像是在下命令：「現在開始查！」
- 顯示照片或錯誤訊息，不是自己跑出來，而是程式根據結果決定要不要顯示。
- 網頁其實是在做條件判斷：
  - 有輸入嗎？
  - 找得到人嗎？
  - 現在是不是正在查？
五、可直接交的 README.md
把下面內容存成 README.md：

# GitHub Scout

這是一個用 Vue 3 做的練習小網站。使用者輸入 GitHub 帳號後，可以查詢該使用者的公開資料，包含大頭貼、名稱、簡介與 GitHub 個人頁面。

## 我問 AI 什麼問題來理解程式碼？

我有問 AI：

1. 哪一行程式碼是在「記住」我輸入的 GitHub 名字？
2. 按下按鈕後，程式是怎麼知道要開始查資料的？
3. 「查無此人」這句話是由哪一段程式控制什麼時候出現？
4. 為什麼照片能在找到資料後才顯示出來？

## AI 用了什麼比喻幫我理解？

AI 用了幾個我覺得很好懂的比喻：

- **輸入框像在把資料放進一個盒子**
  - 我每打一個字，就像把新紙條放進盒子裡。
- **按鈕像開關**
  - 按下去之後，程式就開始做事。
- **條件判斷像守門員**
  - 有資料才放行顯示卡片，沒資料就顯示提示文字。
- **畫面更新像公告欄**
  - 當資料改變時，公告欄上的內容也跟著更新。

## 功能

- 輸入 GitHub 帳號
- 按鈕查詢 GitHub 使用者資料
- 顯示大頭貼、名稱、簡介、個人頁面
- 查無此人提示
- 空白輸入提示

## 使用方式

```bash
npm install
npm run dev
建置
npm run build

Vue 官方文件也有說明，專案啟動使用 `npm run dev`，正式建置使用 `npm run build`，建置結果會輸出到 `dist` 資料夾。:contentReference[oaicite:2]{index=2}

---

# 六、我幫你把 `App.vue` 也寫好

如果你的專案是 Vue 3 + Vite，直接把 `src/App.vue` 換成下面這份：

```vue
<template>
  <div class="page">
    <div class="card">
      <h1>GitHub Scout</h1>
      <p class="subtitle">輸入 GitHub 帳號，查詢使用者公開資料</p>

      <div class="search-box">
        <!-- 這個輸入框會把你打的內容記住 -->
        <input
          v-model="username"
          type="text"
          placeholder="請輸入 GitHub 帳號"
          @keyup.enter="fetchUser"
        />

        <!-- 按下按鈕就開始查詢 -->
        <button @click="fetchUser" :disabled="loading">
          {{ loading ? '查詢中...' : '查詢' }}
        </button>
      </div>

      <!-- 提示訊息區 -->
      <p v-if="message" class="message">{{ message }}</p>

      <!-- 找到資料後才顯示這張卡片 -->
      <div v-if="user" class="user-card">
        <img :src="user.avatar_url" alt="GitHub avatar" class="avatar" />
        <h2>{{ user.name || user.login }}</h2>
        <p class="login">@{{ user.login }}</p>
        <p class="bio">{{ user.bio || '這位使用者沒有留下個人簡介。' }}</p>
        <a :href="user.html_url" target="_blank">前往 GitHub 個人頁面</a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// 這裡像是一個「記憶盒子」，用來存你輸入的帳號
const username = ref('')

// 這裡用來存查到的使用者資料
const user = ref(null)

// 這裡用來存提示文字，例如錯誤訊息
const message = ref('')

// 這裡用來記錄現在是不是正在查詢
const loading = ref(false)

// 這個函式是在按下按鈕後執行的主要工作
const fetchUser = async () => {
  // 每次查詢前先把舊資料清掉
  user.value = null
  message.value = ''

  // 如果沒輸入內容，就不往下查
  if (!username.value.trim()) {
    message.value = '請先輸入 GitHub 帳號'
    return
  }

  loading.value = true

  try {
    const res = await fetch(`https://api.github.com/users/${username.value}`)

    if (!res.ok) {
      throw new Error('Not Found')
    }

    const data = await res.json()
    user.value = data
  } catch (error) {
    message.value = '查無此人'
  } finally {
    loading.value = false
  }
}
</script>

<style scoped>
.page {
  min-height: 100vh;
  margin: 0;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px;
  font-family: Arial, Helvetica, sans-serif;
}

.card {
  width: 100%;
  max-width: 520px;
  background: #ffffff;
  border-radius: 20px;
  padding: 32px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.25);
  text-align: center;
}

h1 {
  margin-bottom: 8px;
}

.subtitle {
  color: #555;
  margin-bottom: 20px;
}

.search-box {
  display: flex;
  gap: 10px;
  margin-bottom: 16px;
}

input {
  flex: 1;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 10px;
  font-size: 16px;
}

button {
  padding: 12px 16px;
  border: none;
  background: #2563eb;
  color: white;
  border-radius: 10px;
  cursor: pointer;
  font-size: 16px;
}

button:disabled {
  background: #94a3b8;
  cursor: not-allowed;
}

.message {
  color: #dc2626;
  font-weight: bold;
  margin: 12px 0;
}

.user-card {
  margin-top: 24px;
  padding: 20px;
  border-radius: 16px;
  background: #f8fafc;
}

.avatar {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 16px;
  border: 4px solid #cbd5e1;
}

.login {
  color: #475569;
  margin-bottom: 10px;
}

.bio {
  margin: 12px 0 16px;
  color: #334155;
}

a {
  color: #2563eb;
  text-decoration: none;
  font-weight: bold;
}
</style>
七、老師如果問你「哪一行是記住輸入內容的？」
你可以這樣答：

const username = ref('')
這一行是在建立一個用來記住資料的地方。
然後真正把輸入框內容放進去的是這一段：

<input v-model="username" ... />
你可以口語講成：

username 像一個盒子

v-model="username" 是把輸入框和盒子接起來

所以我一打字，盒子裡的內容就會同步更新

Vue 官方文件在基礎章節也把表單輸入綁定列為核心主題之一。

八、git init 與 commit
作業要求有 GitHub repo，你再輸入：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
如果你還沒建立遠端 GitHub 倉庫，就去 GitHub 開一個 repo，然後接著：

git remote add origin 你的GitHub倉庫網址
git branch -M main
git push -u origin main
九、你可以直接交的「口語版說明」
老師如果現場問你，你可以這樣講：

我先用 Vue 3 建立專案，做一個 GitHub Scout 頁面。使用者可以輸入 GitHub 帳號，按下查詢後，程式會去 GitHub API 抓公開資料。
如果有找到，就顯示大頭貼、名稱、簡介和個人頁面連結；如果沒找到，就顯示查無此人。
我在 README 裡面寫了我怎麼問 AI 來理解程式碼，也記錄 AI 用什麼比喻幫我理解，像是把輸入框想成盒子、按鈕想成開關。
在 docs/PLAN.md 我也有整理從輸入到畫面顯示結果，中間經過哪些步驟。

十、你現在最實際的交作業順序
建立 Vue 專案

把我上面那份 App.vue 貼進去

新增 README.md

新增 docs/PLAN.md

開 npm run dev 測試

git init、commit、上傳 GitHub

你要的話，我下一則可以直接幫你整理成完整專案資料夾結構版本，讓你一個檔案一個檔案照貼。


已上傳的圖像

已思考 2 秒鐘
你的問題不是 Vue，是電腦目前找不到 npm。

畫面這句：

npm : 無法辨識 'npm' 詞彙
意思是：

你的電腦還沒安裝 Node.js

或者 Node.js 裝了，但環境變數 PATH 沒有設好

因為 npm 是跟著 Node.js 一起安裝的，所以現在要先處理 Node。

你現在要做的事
第一步：檢查有沒有安裝 Node.js
在 PowerShell 輸入：

node -v
再輸入：

npm -v
可能結果 1：都顯示找不到
代表 還沒安裝 Node.js

可能結果 2：node -v 有版本，但 npm -v 沒有
代表 安裝有問題或 PATH 壞掉

第二步：安裝 Node.js
去安裝 Node.js LTS 版本。
安裝時注意：

勾選 Add to PATH

一路下一步即可

安裝完後：

把 PowerShell 關掉重開

再測一次：

node -v
npm -v
如果成功，你會看到版本號，例如：

v22.x.x
10.x.x
第三步：再建立 Vue 專案
等 npm 可以用了，再輸入：

npm create vue@latest
然後照我前面給你的選項建立。

接著：

cd github-scout
npm install
npm run dev
如果你明明裝了 Node 還是不行
那通常是 PATH 沒生效。你可以試這幾個方法：

方法 A：重開終端機
把 PowerShell 全關掉，再重新打開。

方法 B：重開電腦
有時安裝完後 PATH 還沒更新，重開機最直接。

方法 C：檢查安裝位置
通常 Node 會在這裡：

C:\Program Files\nodejs\
看看裡面有沒有：

node.exe

npm

npm.cmd

如果有，但 PowerShell 還找不到，就代表 PATH 沒加成功。

你現在最可能的情況
從你的截圖看，高機率是根本還沒安裝 Node.js。
因為如果有正常安裝，npm 不太會完全找不到。

你可以直接照這個順序做
在 PowerShell 打：

node -v
npm -v
如果都不行，就先去安裝 Node.js

安裝完後關掉 PowerShell 重開

再打一次：

node -v
npm -v
成功後再輸入：

npm create vue@latest
之後你可以跟老師這樣講
我一開始不能建立 Vue 專案，是因為系統找不到 npm。後來我先安裝 Node.js，因為 npm 是跟 Node.js 一起附帶的。等 node 和 npm 都能正常執行後，我才成功用 npm create vue@latest 建立 Vue 3 專案。

把你安裝完後 node -v 和 npm -v 的結果截圖給我，我直接接著帶你做下一步。


已上傳的圖像

已思考 2 秒鐘
這張圖很明確：

你的電腦目前完全沒有可用的 Node.js。
所以 node 和 npm 都找不到。

也就是說，你現在先不要管 Vue，先把 Node.js 安裝好。

你現在直接做這件事
1. 安裝 Node.js
去下載並安裝 Node.js LTS。

安裝時注意一件事：

要勾選 Add to PATH（如果安裝程式有出現這個選項）

安裝完成後：

把現在這個 PowerShell 視窗關掉

重新打開 PowerShell

2. 重新檢查
重新開 PowerShell 後，輸入：

node -v
再輸入：

npm -v
成功的話會長這樣
vXX.X.X
XX.X.X
只要有出現版本號，就表示成功了。

3. 然後再建立 Vue 專案
接著輸入：

npm create vue@latest
之後我建議你的專案名稱輸入：

github-scout
再來照這樣選：

TypeScript? No
JSX? No
Vue Router? No
Pinia? No
Vitest? No
E2E Testing? No
ESLint? Yes
Prettier? Yes
Vue DevTools? No
完成後輸入：

cd github-scout
npm install
npm run dev
如果你安裝完還是不能用
那就照下面順序排查：

方法 1：重開 PowerShell
安裝完一定要重開，不然新路徑常常不會生效。

方法 2：重開電腦
有些 Windows 會到重開機後才正常抓到 PATH。

方法 3：檢查這個資料夾有沒有出現
打開檔案總管看：

C:\Program Files\nodejs\
裡面正常會看到類似：

node.exe

npm

npm.cmd

如果這個資料夾都沒有，表示安裝根本沒成功。
如果有這個資料夾，但 PowerShell 還是找不到，表示是 PATH 沒加成功。

如果 PATH 沒加成功，你這樣做
手動加入 PATH
Windows 搜尋：環境變數

點 編輯系統環境變數

點 環境變數

在「使用者變數」或「系統變數」裡找到 Path

按 編輯

新增這一行：

C:\Program Files\nodejs\
一路按確定

關掉 PowerShell，重新開啟

再測：

node -v
npm -v
你現在最適合的做法
你先不要往後做作業內容，先完成這段：

安裝 Node.js

重開 PowerShell

輸入：

node -v
npm -v
你可以直接複製的檢查流程
node -v
npm -v
如果成功，再接：

npm create vue@latest
老師如果問你卡在哪裡，你可以這樣說
我一開始不是 Vue 寫不出來，而是開發環境還沒好。Windows 找不到 node 和 npm，所以我先安裝 Node.js，讓 npm 可以正常使用，之後才建立 Vue 3 專案。

你現在先去安裝。安裝完後，把 node -v 和 npm -v 成功畫面貼給我，我就接著帶你把 Vue 專案建起來。


已上傳的圖像

已思考 2 秒鐘
對，這頁就是了。你現在要按的是：

請按左邊這個
「Windows 安裝程式 (.msi)」

不要選 .zip。
因為：

.msi = 一般安裝版，最適合你現在這種情況

.zip = 免安裝版，通常要自己處理路徑，對初學者比較麻煩

你現在照這個順序做
1. 點：
Windows 安裝程式 (.msi)

2. 下載完後，打開安裝檔
3. 安裝時一直按 Next，但注意這幾點
看到下面這類選項時：

Add to PATH

或跟 PATH 有關的選項

要確定它有勾到。

4. 安裝完成後
把目前的 PowerShell 全部關掉

5. 重新打開 PowerShell，輸入：
node -v
npm -v
成功會看到像這樣
v22.x.x
10.x.x
有版本號就代表成功。

成功後下一步
接著輸入：

npm create vue@latest
然後我再帶你把專案選項一個一個選好。

你現在先按 .msi 安裝。安裝完後，把 node -v 跟 npm -v 的結果貼給我。


已上傳的圖像

這頁不用改，直接按 Next。

安裝位置 C:\Program Files\nodejs\ 很正常。
先照預設就好，不要改路徑，比較不容易出錯。

接下來你只要注意兩件事：

一路按 Next

如果後面有看到和 PATH 有關的選項，不要取消

安裝完之後：

把目前所有 PowerShell 視窗關掉

重新開一個新的 PowerShell

輸入：

node -v
npm -v
把結果貼給我。


已上傳的圖像

這頁是對的，而且 Add to PATH 已經有選到。
直接按 Next 就可以。

你現在的狀態是正常安裝流程，後面通常就：

Next

Install

等它安裝完成

Finish

安裝完成後一定要做這件事：

把現在所有 PowerShell / 終端機視窗全部關掉

重新開一個新的 PowerShell

然後輸入：

node -v
npm -v
只要有跑出版本號，就代表成功。

成功之後下一步再輸入：

npm create vue@latest
你現在先安裝完。安裝完把 node -v 和 npm -v 的畫面貼給我。


已上傳的圖像

這頁 不要勾，直接按 Next。

原因很簡單：

這是給某些需要額外編譯工具的進階情況

你現在只是要做 Vue 3 作業

目前不需要另外裝 Python、Visual Studio Build Tools、Chocolatey

所以現在照這樣做：

不要勾選

直接按 Next

接著按 Install

安裝完成按 Finish

完成後：

把所有 PowerShell 視窗關掉

重新開一個新的 PowerShell

輸入：

node -v
npm -v
把結果貼給我。
只要版本號有出現，我就接著帶你建立 Vue 專案。


已上傳的圖像

好了，環境正常了。

你現在有：

node v24.14.1

npm 11.11.0

代表可以開始建 Vue 3 專案了。

第一步：建立專案
在 PowerShell 輸入：

npm create vue@latest
如果它問你專案名稱，輸入：

github-scout
第二步：選項這樣選
看到選項時，照這樣選：

Add TypeScript? No
Add JSX Support? No
Add Vue Router for Single Page Application development? No
Add Pinia for state management? No
Add Vitest for Unit testing? No
Add an End-to-End Testing Solution? No
Add ESLint for code quality? Yes
Add Prettier for code formatting? Yes
Add Vue DevTools 7 extension for debugging? No
你這次是交作業，用最簡單版本就好。

第三步：進入專案並啟動
建立完成後輸入：

cd github-scout
npm install
npm run dev
成功的話，終端機會出現一個本機網址，通常像這樣：

http://localhost:5173/
你把它打開，就會看到 Vue 的初始畫面。

第四步：接著做作業內容
等你看到初始畫面後，我們就要開始改檔案。
你先做這一步：

npm create vue@latest

選我上面那組選項

cd github-scout

npm install

npm run dev

然後把 建立專案的畫面 或 Vue 跑起來的畫面 貼給我，我就直接帶你做：

src/App.vue

README.md

docs/PLAN.md

git init 和 commit


已上傳的圖像
這是檔案名稱

已思考幾秒鐘
這個不是「檔案名稱」，這是 GitHub repository 名稱。
你截圖裡看到的是：

114-backend
它比較像是整個專案資料夾/倉庫的名字，不是單一檔案。

你這張圖裡各名稱的意思
114-backend → 倉庫名稱（repo name）

.dockerignore / .env.example / .gitignore → 這些才是檔案名稱

main → 分支名稱

seba2475 → 你的 GitHub 帳號名稱

Minor update (no functional change) → 最近一次 commit 訊息

如果你是要交這次 Vue 作業
你現在這個 repo 名稱 114-backend 看起來像是以前的後端專案，
不太像這次作業要交的 GitHub Scout。

比較建議你：

方法一：新開一個 repo
名稱可以用：

github-scout
或

vue-github-scout
這樣老師一看就知道是這次作業。

你作業裡真正要有的檔案會是這些
專案建立好後，至少會有：

github-scout/
├─ src/
│  └─ App.vue
├─ docs/
│  └─ PLAN.md
├─ README.md
├─ package.json
├─ vite.config.js 或 vite.config.ts
其中你這次最重要的是：

src/App.vue

docs/PLAN.md

README.md

你現在可以怎麼做
如果你還沒建立 Vue 專案
先在 PowerShell 輸入：

npm create vue@latest
專案名稱輸入：

github-scout
如果你已經建立好 Vue 專案，只是還沒上傳 GitHub
那就去 GitHub 新建一個 repo，名字叫：

github-scout
然後在本機專案資料夾裡輸入：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
git branch -M main
git remote add origin 你的GitHub新repo網址
git push -u origin main
最重要的判斷
你這張圖表示的是：

你目前打開的是一個舊 repo，不是作業裡的單一檔案名稱。

你下一步應該是：

建立 Vue 專案 github-scout

把作業內容放進去

再上傳到一個新的 GitHub repo

把你現在 npm create vue@latest 建好的資料夾畫面，或 src 裡面的檔案畫面貼給我，我直接帶你做下一步。


已上傳的圖像

輸入：

y
然後按 Enter。

這句：

Ok to proceed? (y)
意思是它要先幫你下載建立 Vue 專案需要的工具，這是正常的。

按完 y 之後，它會繼續問你幾個選項。
你就照這樣選：

Project name: github-scout
Add TypeScript? No
Add JSX Support? No
Add Vue Router? No
Add Pinia? No
Add Vitest? No
Add an End-to-End Testing Solution? No
Add ESLint? Yes
Add Prettier? Yes
Add Vue DevTools? No
你現在就做這兩步
輸入 y

照我上面那組選項選

選完後把下一張畫面貼給我，我直接幫你看你有沒有選對。


已上傳的圖像

這一頁要用 空白鍵 勾選。

你這次請只勾這兩個：

Linter

Prettier

其他都不要勾。

你現在怎麼按
用 方向鍵 ↓ 往下移

移到 Linter 時按一次 空白鍵

移到 Prettier 時按一次 空白鍵

確認只有這兩個有打勾

按 Enter

你最後應該是這樣
JSX 支援 → 不勾

Router → 不勾

Pinia → 不勾

Vitest → 不勾

端對端測試 → 不勾

Linter → 勾

Prettier → 勾

選好後把下一頁再貼給我。


已上傳的圖像

已思考一秒鐘
這頁 都不要勾，直接按 Enter。

意思是：

使用 Oxfmt 替代 Prettier → 不要

Vue 3.6（測試版） → 不要

你這次作業要穩定、簡單版本，所以維持預設最安全。

你現在做法
直接按：

Enter
完成後如果它建立成功，接著輸入：

cd github-scout
npm install
npm run dev
把成功建立後的畫面貼給我，我接著帶你改 App.vue。


已上傳的圖像

這頁選 No 就對了。

意思是：

Yes = 跳過範例，建立超空白專案

No = 保留一般正常建立流程

你現在直接按：

Enter
因為游標現在已經在 No。

接下來如果專案建立完成，你就輸入：

cd github-scout
npm install
npm run dev
把下一張成功畫面貼給我。


已上傳的圖像

已思考一秒鐘
可以，這代表 建立流程已經跑完了，而且下面這些藍字只是：

npm 有新版本可更新

不是錯誤

先不用管

你現在直接做下一步。

先進入專案資料夾
輸入：

cd github-scout
如果成功，提示字元會變成像這樣：

PS C:\Users\ericp\github-scout>
再安裝並啟動
接著依序輸入：

npm install
npm run dev
成功時會看到
通常會出現像這樣的網址：

Local:   http://localhost:5173/
然後你把那個網址打開。

如果 cd github-scout 失敗
那表示你的資料夾名稱可能不是 github-scout。
先輸入：

dir
我就能幫你看真正的資料夾名稱。

先做這三行：

cd github-scout
npm install
npm run dev
把下一張畫面貼給我，我接著幫你改 App.vue。


已上傳的圖像

已思考 2 秒鐘
很好，專案已經成功建立了。
現在直接進入「完成作業」階段。

你接下來要改 3 個重點：

src/App.vue

docs/PLAN.md

README.md

第一步：先改 src/App.vue
請打開：

github-scout/src/App.vue
把裡面原本全部內容刪掉，改成這份：

<template>
  <div class="page">
    <div class="card">
      <h1>GitHub Scout</h1>
      <p class="subtitle">輸入 GitHub 帳號，查詢使用者公開資料</p>

      <div class="search-box">
        <!-- 這個輸入框會記住你輸入的 GitHub 名字 -->
        <input
          v-model="username"
          type="text"
          placeholder="請輸入 GitHub 帳號"
          @keyup.enter="fetchUser"
        />

        <!-- 按下按鈕後開始查詢 -->
        <button @click="fetchUser" :disabled="loading">
          {{ loading ? '查詢中...' : '查詢' }}
        </button>
      </div>

      <!-- 顯示提示文字 -->
      <p v-if="message" class="message">{{ message }}</p>

      <!-- 找到使用者後才顯示資料卡 -->
      <div v-if="user" class="user-card">
        <img :src="user.avatar_url" alt="GitHub avatar" class="avatar" />
        <h2>{{ user.name || user.login }}</h2>
        <p class="login">@{{ user.login }}</p>
        <p class="bio">{{ user.bio || '這位使用者沒有留下個人簡介。' }}</p>
        <a :href="user.html_url" target="_blank">前往 GitHub 個人頁面</a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// 這個變數像一個小盒子，用來記住輸入框的內容
const username = ref('')

// 這個變數用來存查到的 GitHub 使用者資料
const user = ref(null)

// 這個變數用來存提示訊息
const message = ref('')

// 這個變數用來記錄現在是不是正在查詢
const loading = ref(false)

// 按下按鈕時會執行這個函式
const fetchUser = async () => {
  // 每次查詢前先清空舊資料
  user.value = null
  message.value = ''

  // 如果沒有輸入內容，就顯示提醒
  if (!username.value.trim()) {
    message.value = '請先輸入 GitHub 帳號'
    return
  }

  loading.value = true

  try {
    const res = await fetch(`https://api.github.com/users/${username.value}`)

    if (!res.ok) {
      throw new Error('Not Found')
    }

    const data = await res.json()
    user.value = data
  } catch (error) {
    message.value = '查無此人'
  } finally {
    loading.value = false
  }
}
</script>

<style scoped>
.page {
  min-height: 100vh;
  margin: 0;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px;
  font-family: Arial, Helvetica, sans-serif;
}

.card {
  width: 100%;
  max-width: 520px;
  background: #ffffff;
  border-radius: 20px;
  padding: 32px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.25);
  text-align: center;
}

h1 {
  margin-bottom: 8px;
}

.subtitle {
  color: #555;
  margin-bottom: 20px;
}

.search-box {
  display: flex;
  gap: 10px;
  margin-bottom: 16px;
}

input {
  flex: 1;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 10px;
  font-size: 16px;
}

button {
  padding: 12px 16px;
  border: none;
  background: #2563eb;
  color: white;
  border-radius: 10px;
  cursor: pointer;
  font-size: 16px;
}

button:disabled {
  background: #94a3b8;
  cursor: not-allowed;
}

.message {
  color: #dc2626;
  font-weight: bold;
  margin: 12px 0;
}

.user-card {
  margin-top: 24px;
  padding: 20px;
  border-radius: 16px;
  background: #f8fafc;
}

.avatar {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 16px;
  border: 4px solid #cbd5e1;
}

.login {
  color: #475569;
  margin-bottom: 10px;
}

.bio {
  margin: 12px 0 16px;
  color: #334155;
}

a {
  color: #2563eb;
  text-decoration: none;
  font-weight: bold;
}
</style>
第二步：建立 docs/PLAN.md
先在專案裡建立一個 docs 資料夾。
然後新增檔案：

github-scout/docs/PLAN.md
內容貼這份：

# GitHub Scout Plan

這個小網站的流程，可以想成「查名字找人」：

1. 使用者先在輸入框打入 GitHub 帳號。
2. 網頁先把這個名字記住，像把紙條放進小盒子裡。
3. 使用者按下查詢按鈕。
4. 程式先檢查有沒有輸入內容。
5. 如果是空的，就顯示「請先輸入 GitHub 帳號」。
6. 如果有輸入，程式就去 GitHub 找這個使用者的公開資料。
7. 等資料回來後，畫面決定要顯示什麼。
8. 如果找到人，就顯示照片、名稱、簡介和 GitHub 連結。
9. 如果找不到人，就顯示「查無此人」。
10. 所以整體流程就是：輸入 → 按按鈕 → 檢查 → 查資料 → 顯示結果。

## 我學到的重點

- 輸入框的工作是把資料交給程式記住。
- 按鈕像是在下命令，告訴程式現在開始查。
- 提示訊息不是自己出現的，是程式判斷後才顯示。
- 顯示照片和顯示錯誤，都是根據查詢結果決定的。
第三步：改 README.md
打開專案根目錄的：

github-scout/README.md
改成這份：

# GitHub Scout

這是一個用 Vue 3 製作的小網站。使用者輸入 GitHub 帳號後，可以查詢該使用者的公開資料，包含大頭貼、名稱、簡介與 GitHub 個人頁面。

## 我問 AI 什麼問題來理解程式碼？

我有問 AI 下面這些問題來幫助自己理解：

1. 哪一行程式碼是在記住我輸入的 GitHub 名字？
2. 按下查詢按鈕後，程式是怎麼開始找資料的？
3. 「查無此人」這句話是由哪一段程式碼控制出現的？
4. 為什麼找到資料後，照片和名稱才會顯示出來？

## AI 用了什麼比喻幫我理解？

AI 用了幾個很好懂的比喻：

- 輸入框像把資料放進一個盒子
- 按鈕像開關，按下去就開始做事
- 條件判斷像守門員，決定哪些內容可以出現在畫面上
- 畫面更新像公告欄，資料變了，公告欄也跟著更新

## 功能

- 輸入 GitHub 帳號
- 查詢 GitHub 使用者公開資料
- 顯示大頭貼、名稱、簡介、GitHub 連結
- 空白輸入時提示
- 查不到使用者時提示

## 執行方式

```bash
npm install
npm run dev

---

# 第四步：存檔後看結果

你現在已經有在跑：

```bash
npm run dev
所以只要存檔，瀏覽器通常會自動更新。

你測試 3 件事：

輸入 torvalds

輸入 octocat

隨便輸入一個亂碼帳號，例如 abcxyz123456notfound

第五步：老師可能會問你的口語答案
你可以這樣回答：

1. 哪一行在記住輸入內容？

const username = ref('')
它像一個小盒子，用來記住使用者輸入的帳號。

真正把輸入框和這個盒子連起來的是：

<input v-model="username" />
2. 哪一段在控制查無此人？

在這裡：

catch (error) {
  message.value = '查無此人'
}
意思是如果查資料失敗，就把提示文字改成「查無此人」。

3. 哪一段在控制提示文字什麼時候出現？

這一段：

<p v-if="message" class="message">{{ message }}</p>
意思是只有 message 裡面有文字時，這行才會顯示出來。

第六步：最後上傳 GitHub
在 PowerShell 輸入：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
然後到 GitHub 建立一個新的 repo，名稱建議：

github-scout
建立後把 GitHub 給你的網址貼到下面這行：

git remote add origin 你的GitHub倉庫網址
git branch -M main
git push -u origin main
你現在先把 App.vue、PLAN.md、README.md 改好。
改完後把畫面貼給我，我幫你檢查能不能直接交。


已上傳的圖像
哪裡

已思考一秒鐘
你現在是在 GitHub 新建好但還是空的 repo 頁面。
你要找的是 遠端倉庫網址，位置在這一頁的 Quick setup 區塊。

你現在往下找
畫面再往下滑一點，找到這一段：

Quick setup — if you’ve done this kind of thing before
在那下面會有幾個分頁或按鈕，通常像：

HTTPS

SSH

你先選 HTTPS，然後會看到一個網址，長得像：

https://github.com/seba2475/github-scout.git
這就是你要貼到 PowerShell 的倉庫網址。

你接下來在 PowerShell 輸入
把下面這串直接照抄，只有第二行網址換成你自己的：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
git branch -M main
git remote add origin https://github.com/seba2475/github-scout.git
git push -u origin main
如果你問的是「哪裡可以複製網址」
就是在：

Quick setup → HTTPS → 複製網址按鈕

通常網址框旁邊會有一個 複製圖示。

另一種找法
如果你沒看到 Quick setup，也可以按上方偏右的綠色 Code 按鈕。
按下去後也會跳出：

HTTPS

SSH

Clone URL

你也是複製 HTTPS 那條。

先往下滑找 Quick setup。如果還是找不到，貼下一張更下面的截圖，我直接幫你圈位置。


已上傳的圖像

有了，你現在看到位置了。

但你目前畫面上選的是 SSH，那串是：

git@github.com:seba2475/github-scout.git
對你現在來說，先不要用 SSH，因為比較容易卡在金鑰設定。

你現在要做
點一下上面那個：

HTTPS
切到 HTTPS 後，網址會變成像這樣：

https://github.com/seba2475/github-scout.git
然後複製它。

接著在 PowerShell 輸入這幾行
先進到你的專案資料夾 github-scout 裡，再輸入：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
git branch -M main
git remote add origin https://github.com/seba2475/github-scout.git
git push -u origin main
你這張圖也可以直接看哪一塊要用
你要參考的是下面這一塊：

…or push an existing repository from the command line
因為你已經在自己電腦建立好專案了，不是要「create a new repository on the command line」。

所以實際上你最需要的是這三行概念：

git remote add origin 你的網址
git branch -M main
git push -u origin main
只是因為你本機可能還沒 git init 和 commit，所以完整指令我上面那 6 行最安全。

最穩的做法
先按 HTTPS，然後整套輸入這個：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
git branch -M main
git remote add origin https://github.com/seba2475/github-scout.git
git push -u origin main
如果等一下跳出錯誤，把 PowerShell 畫面貼給我，我直接幫你解。


要開新的終端機嗎?

不用。

只要你現在這個終端機還在 github-scout 資料夾裡，就直接繼續用這個。

你可以先看提示字元是不是像這樣：

PS C:\Users\ericp\github-scout>
如果是這樣
直接輸入：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
git branch -M main
git remote add origin https://github.com/seba2475/github-scout.git
git push -u origin main
如果不是這樣
例如還在：

PS C:\Users\ericp>
那先輸入：

cd github-scout
再跑上面那 6 行。

唯一需要開新終端機的情況，是你原本那個被 npm run dev 佔住了。
如果是這樣，就：

保留那個終端機讓網頁繼續跑

另外開一個新的 PowerShell

再輸入：

cd github-scout
然後執行 git 指令。

你可以先看一下你目前 PowerShell 最前面那行路徑，再決定。


已上傳的圖像
長這樣

對，這樣是正常的。

你現在這個終端機已經被 npm run dev 佔用了，而且 Vue 網站正在跑。
所以：

現在要開一個新的終端機
原因是你要同時做兩件事：

這個視窗繼續讓網站跑著

另一個視窗拿來輸入 git 指令

你現在照做
第 1 步
不要關掉這個視窗

因為它正在跑：

http://localhost:5173/
第 2 步
另外開一個新的 PowerShell

然後輸入：

cd github-scout
第 3 步
在新視窗裡輸入：

git init
git add .
git commit -m "Finish GitHub Scout assignment"
git branch -M main
git remote add origin https://github.com/seba2475/github-scout.git
git push -u origin main
你目前兩個視窗的分工
視窗 1
用途：跑 Vue 網站
內容像你現在這張圖
不要動它

視窗 2
用途：上傳 GitHub
在這個視窗輸入 git 指令

先提醒你一件事
在推上 GitHub 前，你最好先確認這三個檔案都改好了：

src/App.vue

docs/PLAN.md

README.md

如果你還沒改，先改完再 git add .

你現在先開第二個 PowerShell。
如果等一下 git commit 或 git push 出現錯誤，把那個新視窗的畫面貼給我。


已上傳的圖像

成功了。

你這張圖表示：

已經 push 到 GitHub

main 分支上傳成功

遠端 repo 已連好

作業專案已經在 github-scout 上面了

關鍵成功訊息是這兩句：

[new branch]      main -> main
branch 'main' set up to track 'origin/main'
你現在最後要做的確認
去 GitHub 重新整理你的 repo 頁面，確認有沒有看到這些：

src/

docs/

README.md

package.json

如果這些都在，代表基本上可以交了。

特別要再檢查 3 個作業重點
1. README.md
要有寫：

你問 AI 哪些問題來理解程式碼

AI 用了什麼比喻幫你理解

2. docs/PLAN.md
要有：

你和 AI 討論後整理出的白話步驟

3. 網頁功能
打開：

http://localhost:5173/
測試這三個：

輸入 octocat

輸入 torvalds

輸入亂碼帳號，看會不會顯示「查無此人」

你現在可以交的內容
你可以交：

GitHub repo 連結

README.md

docs/PLAN.md

Vue 網頁成果

老師如果問你，你可以這樣講
我先用 Vue 3 建立 github-scout 專案，做出一個可以輸入 GitHub 帳號並查詢公開資料的網頁。
我有把和 AI 討論流程後整理出的白話步驟放在 docs/PLAN.md，也把我問 AI 哪些問題來理解程式碼、AI 用了哪些生活化比喻寫在 README.md。
最後我用 git 初始化、commit，並把整個專案 push 到 GitHub。

你現在最建議再做一次的事
到 GitHub 頁面重新整理，然後截一張有 src、docs、README.md 的 repo 首頁圖給我，我幫你做最後驗收。


已上傳的圖像
怎麼用

已思考一秒鐘
你現在看到的還是 Vue 預設首頁，表示：

專案有成功跑起來，但你還沒把 App.vue 換成作業內容。

你現在要做的是「修改檔案」，不是在這個網頁上直接操作。

你現在怎麼用
第 1 步：打開專案資料夾
到你電腦的這個位置：

C:\Users\ericp\github-scout
第 2 步：用編輯器打開
最方便的是用 VS Code。

你可以這樣開：

打開 VS Code

點 File

點 Open Folder

選：

C:\Users\ericp\github-scout
第 3 步：找到要改的檔案
左邊檔案區找到：

src
 └─ App.vue
點開 App.vue，把裡面原本內容全部刪掉，換成我前面給你的那份 GitHub Scout 程式。

也就是把現在這個預設首頁：

You did it!

Documentation

Tooling

全部換掉。

第 4 步：存檔
按：

Ctrl + S
只要你存檔，因為你現在有跑 npm run dev，瀏覽器會自動更新。

第 5 步：瀏覽器會變成你的作業畫面
存檔後，原本那個 Vue 預設頁面就會變成：

GitHub Scout

輸入框

查詢按鈕

查到使用者資料的卡片

你如果不知道 App.vue 內容要貼什麼
把這份完整貼進 src/App.vue：

<template>
  <div class="page">
    <div class="card">
      <h1>GitHub Scout</h1>
      <p class="subtitle">輸入 GitHub 帳號，查詢使用者公開資料</p>

      <div class="search-box">
        <input
          v-model="username"
          type="text"
          placeholder="請輸入 GitHub 帳號"
          @keyup.enter="fetchUser"
        />

        <button @click="fetchUser" :disabled="loading">
          {{ loading ? '查詢中...' : '查詢' }}
        </button>
      </div>

      <p v-if="message" class="message">{{ message }}</p>

      <div v-if="user" class="user-card">
        <img :src="user.avatar_url" alt="GitHub avatar" class="avatar" />
        <h2>{{ user.name || user.login }}</h2>
        <p class="login">@{{ user.login }}</p>
        <p class="bio">{{ user.bio || '這位使用者沒有留下個人簡介。' }}</p>
        <a :href="user.html_url" target="_blank">前往 GitHub 個人頁面</a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const username = ref('')
const user = ref(null)
const message = ref('')
const loading = ref(false)

const fetchUser = async () => {
  user.value = null
  message.value = ''

  if (!username.value.trim()) {
    message.value = '請先輸入 GitHub 帳號'
    return
  }

  loading.value = true

  try {
    const res = await fetch(`https://api.github.com/users/${username.value}`)

    if (!res.ok) {
      throw new Error('Not Found')
    }

    const data = await res.json()
    user.value = data
  } catch (error) {
    message.value = '查無此人'
  } finally {
    loading.value = false
  }
}
</script>

<style scoped>
.page {
  min-height: 100vh;
  margin: 0;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px;
  font-family: Arial, Helvetica, sans-serif;
}

.card {
  width: 100%;
  max-width: 520px;
  background: #ffffff;
  border-radius: 20px;
  padding: 32px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.25);
  text-align: center;
}

h1 {
  margin-bottom: 8px;
}

.subtitle {
  color: #555;
  margin-bottom: 20px;
}

.search-box {
  display: flex;
  gap: 10px;
  margin-bottom: 16px;
}

input {
  flex: 1;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 10px;
  font-size: 16px;
}

button {
  padding: 12px 16px;
  border: none;
  background: #2563eb;
  color: white;
  border-radius: 10px;
  cursor: pointer;
  font-size: 16px;
}

button:disabled {
  background: #94a3b8;
  cursor: not-allowed;
}

.message {
  color: #dc2626;
  font-weight: bold;
  margin: 12px 0;
}

.user-card {
  margin-top: 24px;
  padding: 20px;
  border-radius: 16px;
  background: #f8fafc;
}

.avatar {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 16px;
  border: 4px solid #cbd5e1;
}

.login {
  color: #475569;
  margin-bottom: 10px;
}

.bio {
  margin: 12px 0 16px;
  color: #334155;
}

a {
  color: #2563eb;
  text-decoration: none;
  font-weight: bold;
}
</style>
第 6 步：建立另外兩個作業檔案
除了 App.vue，你還要做：

docs/PLAN.md
先建立 docs 資料夾，再建立 PLAN.md

README.md
把原本的 README 改成作業版本

你現在最簡單的理解
你現在不是在「用網頁做功能」，而是在：

用瀏覽器看結果

用 VS Code 改程式

最短操作路線
現在直接做這件事：

用 VS Code 開 C:\Users\ericp\github-scout

打開 src/App.vue

全部刪掉

貼上我上面那份程式

按 Ctrl + S

回瀏覽器看畫面變化

把你 App.vue 打開後的畫面貼給我，我直接告訴你要刪哪裡、貼哪裡。


已上傳的圖像

不要選 src。

你現在要在 VS Code 開的是整個專案資料夾，不是裡面某一個子資料夾。

現在怎麼做
你目前位置已經在：

C:\Users\ericp\github-scout
所以直接按右下角：

Select Folder
但前提是你要選的是 github-scout 整個資料夾，不是 src。

你這張圖目前錯在哪
你現在反白的是：

src
這樣不對。
因為如果只開 src，等等你會不好建立：

README.md

docs/PLAN.md

其他根目錄檔案

正確做法
先點上方路徑列左邊，回到 github-scout 這層。
然後讓裡面不要選 src，直接選整個 github-scout。

或者更簡單一點：

不要點任何子資料夾

直接按右下角 Select Folder

如果它目前真的把 github-scout 當成目前資料夾，那直接按就可以。

開好之後你要做的事
左邊檔案區會看到整個專案，接著：

打開 src/App.vue

把裡面全部刪掉

貼上我前面給你的 GitHub Scout 程式

按 Ctrl + S

然後再建立：

docs/PLAN.md

修改 README.md

你現在先按 Select Folder 開整個 github-scout。
開好後把 VS Code 左側檔案樹畫面貼給我。


已上傳的圖像

很好，現在開對了。

你現在就在正確的位置。接下來照這個順序做。

1. 打開 src
點左邊的：

src
展開後通常會看到像：

App.vue

main.js

assets

components

2. 打開 App.vue
點開：

src/App.vue
3. 全部刪掉，貼上這份
把 App.vue 原本內容全部換成：

<template>
  <div class="page">
    <div class="card">
      <h1>GitHub Scout</h1>
      <p class="subtitle">輸入 GitHub 帳號，查詢使用者公開資料</p>

      <div class="search-box">
        <input
          v-model="username"
          type="text"
          placeholder="請輸入 GitHub 帳號"
          @keyup.enter="fetchUser"
        />

        <button @click="fetchUser" :disabled="loading">
          {{ loading ? '查詢中...' : '查詢' }}
        </button>
      </div>

      <p v-if="message" class="message">{{ message }}</p>

      <div v-if="user" class="user-card">
        <img :src="user.avatar_url" alt="GitHub avatar" class="avatar" />
        <h2>{{ user.name || user.login }}</h2>
        <p class="login">@{{ user.login }}</p>
        <p class="bio">{{ user.bio || '這位使用者沒有留下個人簡介。' }}</p>
        <a :href="user.html_url" target="_blank">前往 GitHub 個人頁面</a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const username = ref('')
const user = ref(null)
const message = ref('')
const loading = ref(false)

const fetchUser = async () => {
  user.value = null
  message.value = ''

  if (!username.value.trim()) {
    message.value = '請先輸入 GitHub 帳號'
    return
  }

  loading.value = true

  try {
    const res = await fetch(`https://api.github.com/users/${username.value}`)

    if (!res.ok) {
      throw new Error('Not Found')
    }

    const data = await res.json()
    user.value = data
  } catch (error) {
    message.value = '查無此人'
  } finally {
    loading.value = false
  }
}
</script>

<style scoped>
.page {
  min-height: 100vh;
  margin: 0;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px;
  font-family: Arial, Helvetica, sans-serif;
}

.card {
  width: 100%;
  max-width: 520px;
  background: #ffffff;
  border-radius: 20px;
  padding: 32px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.25);
  text-align: center;
}

h1 {
  margin-bottom: 8px;
}

.subtitle {
  color: #555;
  margin-bottom: 20px;
}

.search-box {
  display: flex;
  gap: 10px;
  margin-bottom: 16px;
}

input {
  flex: 1;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 10px;
  font-size: 16px;
}

button {
  padding: 12px 16px;
  border: none;
  background: #2563eb;
  color: white;
  border-radius: 10px;
  cursor: pointer;
  font-size: 16px;
}

button:disabled {
  background: #94a3b8;
  cursor: not-allowed;
}

.message {
  color: #dc2626;
  font-weight: bold;
  margin: 12px 0;
}

.user-card {
  margin-top: 24px;
  padding: 20px;
  border-radius: 16px;
  background: #f8fafc;
}

.avatar {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 16px;
  border: 4px solid #cbd5e1;
}

.login {
  color: #475569;
  margin-bottom: 10px;
}

.bio {
  margin: 12px 0 16px;
  color: #334155;
}

a {
  color: #2563eb;
  text-decoration: none;
  font-weight: bold;
}
</style>
4. 存檔
按：

Ctrl + S
5. 回瀏覽器看
你跑 npm run dev 的那個網頁會自動更新。
原本的 “You did it!” 會不見，改成你的 GitHub Scout 畫面。

6. 再做兩個檔案
接著還要：

建立 docs/PLAN.md

修改 README.md

但先把 App.vue 這一步做完。

做完後，把兩張其中一張貼給我：
App.vue 編輯後畫面，或瀏覽器更新後畫面。


已上傳的圖像

已思考 4s
很好，App.vue 已經成功了。
現在畫面看起來就是你的作業主體了。

接下來只差最後兩個必要檔案：

docs/PLAN.md

README.md

1. 建立 docs/PLAN.md
在左邊檔案區，對 GITHUB-SCOUT 按右鍵，新增資料夾：

docs
再在 docs 裡新增檔案：

PLAN.md
內容貼這份：

# GitHub Scout Plan

這個小網站的流程，可以想成「查名字找人」：

1. 使用者先在輸入框打入 GitHub 帳號。
2. 網頁先把這個名字記住，像把紙條放進小盒子裡。
3. 使用者按下查詢按鈕。
4. 程式先檢查有沒有輸入內容。
5. 如果是空的，就顯示「請先輸入 GitHub 帳號」。
6. 如果有輸入，程式就去 GitHub 找這個使用者的公開資料。
7. 等資料回來後，畫面決定要顯示什麼。
8. 如果找到人，就顯示照片、名稱、簡介和 GitHub 連結。
9. 如果找不到人，就顯示「查無此人」。
10. 所以整體流程就是：輸入 → 按按鈕 → 檢查 → 查資料 → 顯示結果。

## 我學到的重點

- 輸入框的工作是把資料交給程式記住。
- 按鈕像是在下命令，告訴程式現在開始查。
- 提示訊息不是自己出現的，是程式判斷後才顯示。
- 顯示照片和顯示錯誤，都是根據查詢結果決定的。
存檔。

2. 修改 README.md
打開根目錄的 README.md，把原本內容全部改成：

# GitHub Scout

這是一個用 Vue 3 製作的小網站。使用者輸入 GitHub 帳號後，可以查詢該使用者的公開資料，包含大頭貼、名稱、簡介與 GitHub 個人頁面。

## 我問 AI 什麼問題來理解程式碼？

我有問 AI 下面這些問題來幫助自己理解：

1. 哪一行程式碼是在記住我輸入的 GitHub 名字？
2. 按下查詢按鈕後，程式是怎麼開始找資料的？
3. 「查無此人」這句話是由哪一段程式碼控制出現的？
4. 為什麼找到資料後，照片和名稱才會顯示出來？

## AI 用了什麼比喻幫我理解？

AI 用了幾個很好懂的比喻：

- 輸入框像把資料放進一個盒子
- 按鈕像開關，按下去就開始做事
- 條件判斷像守門員，決定哪些內容可以出現在畫面上
- 畫面更新像公告欄，資料變了，公告欄也跟著更新

## 功能

- 輸入 GitHub 帳號
- 查詢 GitHub 使用者公開資料
- 顯示大頭貼、名稱、簡介、GitHub 連結
- 空白輸入時提示
- 查不到使用者時提示

## 執行方式

```bash
npm install
npm run dev

存檔。

---

## 3. 測試網頁

回到瀏覽器，測這三個：

先輸入：

```text
octocat
再輸入：

torvalds
再輸入一個亂碼，例如：

abcxyz123456notfound
你要確認：

有資料時會顯示卡片

沒資料時會顯示「查無此人」

空白按查詢時會顯示「請先輸入 GitHub 帳號」

4. 最後再 push 一次
因為你剛剛上傳 GitHub 的時候，這些內容還沒更新，所以現在要再推一次。

到你第二個 PowerShell 視窗，輸入：

git add .
git commit -m "Add GitHub Scout app and assignment files"
git push
5. 交作業前最後確認
GitHub 頁面重新整理後，要看到：

src/

docs/

README.md

而且 docs 裡面有 PLAN.md。

你現在先把 PLAN.md 和 README.md 做完，再 git push。
做完後貼一張 GitHub 首頁或 VS Code 左側檔案樹，我幫你最後驗收。


怎麼新增

在 VS Code 左邊檔案區新增就可以。

新增 docs 資料夾
在左邊 GITHUB-SCOUT 上面操作：

方法 1
把滑鼠移到 GITHUB-SCOUT 這一行，右邊會出現小圖示。
點 新增資料夾 的圖示。

然後輸入：

docs
按 Enter。

方法 2
對 GITHUB-SCOUT 按 右鍵 → 選：

New Folder
輸入：

docs
按 Enter。

新增 PLAN.md
建立好 docs 之後：

對 docs 按右鍵

選：

New File
輸入：

PLAN.md
按 Enter

新增完會長這樣
GITHUB-SCOUT
├─ docs
│  └─ PLAN.md
├─ src
├─ README.md
然後把內容貼進去
打開 PLAN.md，貼這份：

# GitHub Scout Plan

這個小網站的流程，可以想成「查名字找人」：

1. 使用者先在輸入框打入 GitHub 帳號。
2. 網頁先把這個名字記住，像把紙條放進小盒子裡。
3. 使用者按下查詢按鈕。
4. 程式先檢查有沒有輸入內容。
5. 如果是空的，就顯示「請先輸入 GitHub 帳號」。
6. 如果有輸入，程式就去 GitHub 找這個使用者的公開資料。
7. 等資料回來後，畫面決定要顯示什麼。
8. 如果找到人，就顯示照片、名稱、簡介和 GitHub 連結。
9. 如果找不到人，就顯示「查無此人」。
10. 所以整體流程就是：輸入 → 按按鈕 → 檢查 → 查資料 → 顯示結果。

## 我學到的重點

- 輸入框的工作是把資料交給程式記住。
- 按鈕像是在下命令，告訴程式現在開始查。
- 提示訊息不是自己出現的，是程式判斷後才顯示。
- 顯示照片和顯示錯誤，都是根據查詢結果決定的。
按 Ctrl + S 存檔。

README 也是同樣做法
直接點左邊現有的 README.md，把內容改掉就好，不用新增。

如果你要，我下一則可以直接教你 怎麼改 README.md，一步一步照著按。


怎麼改 README.md

在左邊檔案區直接點 README.md 就能改。

步驟
1. 打開 README.md
在左邊 GITHUB-SCOUT 底下找到：

README.md
直接點一下。

2. 全部刪掉
打開後按：

Ctrl + A
再按：

Backspace
這樣就把原本內容清空。

3. 貼上這份內容
# GitHub Scout

這是一個用 Vue 3 製作的小網站。使用者輸入 GitHub 帳號後，可以查詢該使用者的公開資料，包含大頭貼、名稱、簡介與 GitHub 個人頁面。

## 我問 AI 什麼問題來理解程式碼？

我有問 AI 下面這些問題來幫助自己理解：

1. 哪一行程式碼是在記住我輸入的 GitHub 名字？
2. 按下查詢按鈕後，程式是怎麼開始找資料的？
3. 「查無此人」這句話是由哪一段程式碼控制出現的？
4. 為什麼找到資料後，照片和名稱才會顯示出來？

## AI 用了什麼比喻幫我理解？

AI 用了幾個很好懂的比喻：

- 輸入框像把資料放進一個盒子
- 按鈕像開關，按下去就開始做事
- 條件判斷像守門員，決定哪些內容可以出現在畫面上
- 畫面更新像公告欄，資料變了，公告欄也跟著更新

## 功能

- 輸入 GitHub 帳號
- 查詢 GitHub 使用者公開資料
- 顯示大頭貼、名稱、簡介、GitHub 連結
- 空白輸入時提示
- 查不到使用者時提示

## 執行方式

```bash
npm install
npm run dev

---

### 4. 存檔
按：

```text
Ctrl + S
改完後再做這三行
到 PowerShell 輸入：

git add .
git commit -m "Update README and PLAN"
git push
你現在完成後應該會有
左邊檔案區至少看到：

GITHUB-SCOUT
├─ docs
│  └─ PLAN.md
├─ src
│  └─ App.vue
└─ README.md
改完 README.md 後，把畫面貼給我，我幫你確認。


底下的存檔也要複製嗎

不用。

你只要複製 README 內容本身，不要把我後面說明文字一起複製進檔案。

也就是說，貼進 README.md 的內容要從這一行開始：

# GitHub Scout
到這裡結束：

npm run dev
完整應該像這樣：

# GitHub Scout

這是一個用 Vue 3 製作的小網站。使用者輸入 GitHub 帳號後，可以查詢該使用者的公開資料，包含大頭貼、名稱、簡介與 GitHub 個人頁面。

## 我問 AI 什麼問題來理解程式碼？

我有問 AI 下面這些問題來幫助自己理解：

1. 哪一行程式碼是在記住我輸入的 GitHub 名字？
2. 按下查詢按鈕後，程式是怎麼開始找資料的？
3. 「查無此人」這句話是由哪一段程式碼控制出現的？
4. 為什麼找到資料後，照片和名稱才會顯示出來？

## AI 用了什麼比喻幫我理解？

AI 用了幾個很好懂的比喻：

- 輸入框像把資料放進一個盒子
- 按鈕像開關，按下去就開始做事
- 條件判斷像守門員，決定哪些內容可以出現在畫面上
- 畫面更新像公告欄，資料變了，公告欄也跟著更新

## 功能

- 輸入 GitHub 帳號
- 查詢 GitHub 使用者公開資料
- 顯示大頭貼、名稱、簡介、GitHub 連結
- 空白輸入時提示
- 查不到使用者時提示

## 執行方式

```bash
npm install
npm run dev

## 不要複製的東西
這些不要放進 `README.md`：

- 我說的「按 Ctrl + S」
- 我說的「到 PowerShell 輸入 git add .」
- 我說的步驟說明文字

## 你現在只要做
1. 把上面那段 README 內容貼進 `README.md`
2. 按 `Ctrl + S`

存好後再去 PowerShell 輸入：

```powershell
git add .
git commit -m "Update README and PLAN"
git push
如果你不確定你有沒有貼錯，貼一張 README.md 畫面給我，我幫你看。


已上傳的圖像

有，這樣方向是對的，而且你已經改成功大部分了。

但我看你的 README.md 下面還沒完整貼完，目前只看到：

標題

問題

比喻

功能

你還要再補最後一段：

請在 README.md 最下面補上這段
## 執行方式

```bash
npm install
npm run dev

---

## 你現在要做的事

### 1. 把下面這段補到最底下

```md
## 執行方式

```bash
npm install
npm run dev

### 2. 按存檔
按：

```text
Ctrl + S
右下角那個跳出來的提示
它在問你要不要裝 Vue 的延伸套件。
現在先不用理它，直接關掉或放著都可以，不影響作業。

然後再確認一個檔案
你還要有：

docs/PLAN.md
如果還沒建，現在去建。

內容貼這份：

# GitHub Scout Plan

這個小網站的流程，可以想成「查名字找人」：

1. 使用者先在輸入框打入 GitHub 帳號。
2. 網頁先把這個名字記住，像把紙條放進小盒子裡。
3. 使用者按下查詢按鈕。
4. 程式先檢查有沒有輸入內容。
5. 如果是空的，就顯示「請先輸入 GitHub 帳號」。
6. 如果有輸入，程式就去 GitHub 找這個使用者的公開資料。
7. 等資料回來後，畫面決定要顯示什麼。
8. 如果找到人，就顯示照片、名稱、簡介和 GitHub 連結。
9. 如果找不到人，就顯示「查無此人」。
10. 所以整體流程就是：輸入 → 按按鈕 → 檢查 → 查資料 → 顯示結果。

## 我學到的重點

- 輸入框的工作是把資料交給程式記住。
- 按鈕像是在下命令，告訴程式現在開始查。
- 提示訊息不是自己出現的，是程式判斷後才顯示。
- 顯示照片和顯示錯誤，都是根據查詢結果決定的。
全部完成後
去 PowerShell 輸入：

git add .
git commit -m "Complete assignment files"
git push
你現在離完成只差一小步。
補完 README.md 最後那段，然後把 docs/PLAN.md 建好，再貼一張左邊檔案樹給我。


已上傳的圖像

已思考 7s
差一個結尾。

你現在已經寫對前半段了，但 bash 程式區塊還沒關起來。
請在 npm run dev 的下一行再補上：


也就是整段要長這樣：

```md
## 執行方式

```bash
npm install
npm run dev

## 你現在做
1. 在 `npm run dev` 下一行輸入三個反引號：
```text