# GAGTT
GAGTT (Google API Get  Two Token) 是由[Honc](https://blog.honcbb.me/) 安全研究人員開發（非Google 官方所開發)，程式僅協助開發人員獲取『**Refresh_Token**、**Access_Token**』這兩個值方便直接調用應用程序，在Google API 中每次執行調用功能時都必須要有所謂的"授權碼(Authorization code)"，在由這組"授權碼(Authorization code) 去取得"Refresh_Token" 以及"Access_Token" (在這裡access 每次都不同且一定要有它)，也因為"授權碼(Authorization Code)" 有效期非常短(且為隨機) 當應用程序調用時都必須要有上述後兩者的token ，因此必須要重複取得"授權碼(Authorization Code)" 才能獲得後面兩組Token（倘若應用程序，開發人員便未直接透過＂Refresh_Token＂取得＂Access_Token" 話，必須每次執行授權（這裡也產生所謂了UAC) 有些是必須讓使用者自行登入存取返回取得授權碼)，這樣一來增加了開發人員以及使用者使用上的困擾，所以Google 有另外新的更便捷方法（**那就是取得無限期的＂refresh_token＂，這裡除非是人員撤銷權限或者移除了或重置了，這組token 才有可能會失效**) 使用"**refresh_token**" 每次自動重複獲取"**access_token**" 這樣一來讓開發人員在實作方面就簡單方便了許多。

#### 註：雖然Refresh_Token 提供了方便性，但在安全角度上，這組Token 一旦取得必須保護好或者避免外洩(倘若被取得，有可能造成一些安全上的風險(ex.取得訪問應用程式的權限或相關數據)。

![image](https://i.imgur.com/Nui5d0N.jpg)

[![Release](https://img.shields.io/badge/%E7%89%88%E6%9C%AC-V1.2-green)](https://github.com/honcbb-secu/SecVir/releases)

[![Release](https://img.shields.io/badge/%E9%BB%9E%E6%88%91-%E4%B8%8B%E8%BC%89-brightgreen)](https://github.com/honcbb-secu/SecVir/releases/download/V1.2/SecVir.zip)


## Demo

[![ScreenShot](https://i.imgur.com/cdRs9g2.jpg)](https://www.youtube.com/watch?v=6oAhz3h8frE&feature=youtu.be)

## 更新

GAGTT 會不定時更新，日後也會替該程式加上更多功能(敬啟期待！)

## 注意

程式只有協助獲取Token 並非協助創建Google API (憑證)之功能，也不是由Google 官方所開發的工具。

## 支援

**Windows 系統**

## 安全

為了保護軟體安全因而採用**軟體加密保護技術**，所以有些防毒軟體產品會判**GAGTT**為是惡意木馬部分，但同樣可保證是**GAGTT** 絕沒有植入**病毒木馬**及**竊取用戶電腦資訊** 任何情況，如果還是**無法放心(請勿使用)**


## 如何使用？

請將您的"**Client_ID**、**Client_Secret**、**Redirect_URL**、**Code**" 各自輸入後點選"Get" 即可獲取"**Refresh_Token**"," 和第一個的**Access_Token**"。

## 常見問題

* 為什麼開啟程式出現**請先確定是否有連線！** ? 

    → 『因為程式加入了相關版本驗證通知必須與伺服器作連線確認，因此前提開啟程式下必須先開啟網路執行才行』
    
* 為什麼開啟程式出現**程式已有更新！請至作者專案重新下載新版本程式。** ? 

    → 『程式已經有新增功能或修補其他相關錯誤Bug 而衍生出新版本，這時只需至專案重新下載新版本即可』
    
* 為什麼開啟程式出現**無法啟動程序，因為找不到"winhttpcom.dll" 檔案** ? 

    → 『這個錯誤是因為GAGTT 程式本身引用了Microsoft Windows HTTP Services API，必須要有這個檔案才能正確與伺服器驗證並且回傳相關通知訊息，電腦處於兩種情況：
    
    一. 電腦路徑C:\Windows\System32\* 沒有這個winhttpcom.dll檔案，所以須至網路尋找並放置正確路徑即可
    
    二. 電腦雖有這個檔案，但沒有給它正確註冊，可參考[這篇文章](https://dotblogs.com.tw/usice0314/2010/04/07/14442) 修改一下註冊即可』
  
* 我在程式提供的相關密鑰憑證會被知道嗎或被記錄?  
 
  → 『請放心，GAGTT 程式並未紀錄以及擅自儲存這些數據(含傳送)至第三方伺服器，僅與Google Server 作交互（**所以你的敏感數據僅會直接傳送給Google**)。 』
  
* 為什麼點選"Get" 取得後出現"請求過程中出現莫名錯誤xxxxxxxxx 類錯誤?  
 
  → 『請檢查你所輸入的憑證是否都正確。 』
  
  → 『如果Client_ID、Client_Secret、Redirect_URL 都確認沒問題，那可能是產生授權碼地方有誤，請至：**https://accounts.google.com/o/oauth2/v2/auth?client_id=[]&redirect_uri=[]&response_type=code&scope=[]&access_type=offline** 修改後重新獲取"授權碼" 並再次嘗試。 』
  
* 一定要連線才能開啟程式(掃描) ? 
 
  → 『是的，程式掃描所有資訊都需送往Google 系統並取得，然而必須連網才能。 』
