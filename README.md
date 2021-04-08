# YOLO_AutoMark  
語言：python  
程式最後修改時間：2020/08/24  
  
一個人手動一張一張標記太慢  
一次標記大量圖片還可能標記錯誤  
於是想到此方法可以快速、大量的自動標記圖片  
  
首先，使用labelImg手動標記圖片，約100張  
觀察標記完產生的xml檔，並用python產生相同格式的xml檔  
![img](https://github.com/WhiteEyeYan/YOLO_AutoMark/blob/main/README_img/xml_format.jpg)  
  
利用少量的圖片，先訓練出一個可以大致判讀物件位置及label的weights，利用此weights去標記還未標記的圖片  
觀察YOLO回傳值可發現回傳值有找到的物件名稱、中心座標、長寬，利用中心座標及長寬可計算出xml要的x, y的min及max  
按照labelImg的規則產生出該圖片的xml，完成後再打開labelImg檢查位置及label是否正確  
  
檢查label是否正確  
![img](https://github.com/WhiteEyeYan/YOLO_AutoMark/blob/main/README_img/checkLabel.jpg)
