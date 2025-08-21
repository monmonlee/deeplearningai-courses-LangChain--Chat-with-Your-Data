#### LangChain 的分層設計
* LangChain Loader (高層抽象) + 底層工具 (具體實作) = 完整功能

* 範例：
    ```bash
    PDF:     PyPDFLoader     + pypdf           = PDF文檔載入
    YouTube: GenericLoader   + ffmpeg          = 音檔轉文字  
    URLs:    WebBaseLoader   + beautifulsoup4  = 網頁爬蟲
    CSV:     CSVLoader       + pandas          = 表格處理
    Excel:   ExcelLoader     + openpyxl        = Excel處理
    ```
* 設計目的：
    * 開發者友善：為不需要重新學底層套件的語法，只需安裝就好，例如不需要了解 beautifulsoup4 的語法就可以執行，只需要學習 LangChain 的統一介面：
    ```python
    from langchain.document_loaders import WebBaseLoader 
    docs = WebBaseLoader(url).load() 
    ```
    * 一致性的使用：每一個loader轉換介面都大同小異，方便處理
* 其他常見例子：
    ```bash
    matplotlib + numpy    = 繪圖功能
    pandas + numpy        = 資料分析  
    scikit-learn + numpy  = 機器學習
    requests + urllib3    = HTTP 請求
    ```
