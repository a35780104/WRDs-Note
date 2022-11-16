# WRDs-Note
This is wrds search code for cylab.

## Wharton網址
通常會去裡面的"Products"找哪個資料庫(在這叫library)可以抓  
https://wrds-www.wharton.upenn.edu/pages/about/data-vendors/sp-global-market-intelligence/

### Example:
"comp_na_daily_all"裡面有很多Tables，裡面應該比較常用的就是  
https://wrds-www.wharton.upenn.edu/data-dictionary/comp_na_daily_all/  
 
 
Table:"funda" , Description:"Merged Fundamental Annual File (funda)"綜合財務報表整合(含)在這個Table。  
https://wrds-www.wharton.upenn.edu/data-dictionary/comp_na_annual_all/funda/  
Table:"co_afnd1" , Description:"Company Annual Item (A-L)"。資產負債表涵蓋的資料都在這個Table。  
https://wrds-www.wharton.upenn.edu/data-dictionary/comp_na_daily_all/co_afnd1/  
Table:"co_afnd2" , Description:"Company Annual Item (M-Z)	"。損益表涵蓋的資料都在這個Table。  
https://wrds-www.wharton.upenn.edu/data-dictionary/comp_na_daily_all/co_afnd2/  
Table:"namesq" , Description:"Name File	"。公司名稱、SIC Code、股票代碼都在這個Table。  
https://wrds-www.wharton.upenn.edu/data-dictionary/comp_na_daily_all/namesq/  

## 欄位資料
欄位資料都在Table裡面可以看  
查看哪些是你需要的欄位  

### Example
https://wrds-www.wharton.upenn.edu/data-dictionary/comp_na_daily_all/namesq/  
Variable Name:"gvkey" Description:"Global Company Key"  
Variable Name:"sic" Description:"Standard Industry Classification Code"  

## Wharton Sample Code  
https://wrds-www.wharton.upenn.edu/documents/1443/wrds_connection.html  

## 操作
安裝包  
```
pip install wrds
```
連線(輸入帳號密碼)  
```
conn = wrds.Connection()
```
查看資料庫(library)清單
```
conn.list_libraries()
```
查看特定library的Table清單
```
conn.list_tables(library='你要的library')
```
獲得資料表
```
company = conn.get_table(library='comp', table='co_afnd1', obs=5)
```
下sql獲得資料表
```
df_sql = conn.raw_sql(sql_query)
```

