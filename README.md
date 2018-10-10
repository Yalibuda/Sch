# 排程說明文件
## 說明
>核心使用二次線性規劃，疊代過程使用隨機限制讓每次線性規劃能有不同的結果。

## 流程


## 基本的輸入與輸出
### Input file
File name | 說明
:---|:---
input.csv| 目前需納入排程的工單, 也包含已經排過的工單
AOI.csv | 各線體的 AOI 機台配置
Line_forbid.csv | 定義哪些線體於何時做生產管制
Line_type.csv | 線體是否為新線體
Carrier.csv | 各料號使用的載具/鋼板
Process_seq.csv | 各料號的製程順序
def/SCH基本參數設定.csv | 定義各廠排程條件的設定, 例如: 工時折扣、AOI 製作時間等

以上輸入的檔案格式均以原排程系統規劃一致。

### Output file
輸入一個 xlsx 檔，包含結果最好的三組解，欄位如下:

欄位名稱 | 說明
:---|:---
MO | 工單名稱或生產管制代號，工單若遇到生產管制或是 EPR 會拆單，並以原工單名 + @ + 數字方式命名
SIDE | 工單對應的面別
PROCESS | 對應的製程名
PN | 料號
DEMAND | 總需求量, 若拆單仍以原數量顯示
REMAIN | 剩餘需求數量, 若拆單仍以原數量顯示
START.DATE | 齊料點
END.DATE | 最晚投入日
PRODUCE.DATE | 已排入的時間
OSP | OSP
WORK.HOUR | 所需總工時(小時)
LATEST.END | 工單完工時間
VAR.NAME | 線性規劃的變數代碼
LINE.STAMP | 投入線體
Remark | 確認投入時間是否晚於最晚投入日
Msg | 排程衝突，例如: 載具/ 人力衝突


