[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/qPD8ugtn)
# Week 2
  
# HW1 - resolve conflict and PR  
## 前置作業  
* 首先將[frakw/git_practice](https://gitlab.com/frakw/git_practice) fork到我們自己的gitlab(在這邊我的檔案名稱設為**git-practice-lab**)  
* 下載`git_practice.zip`到本機端並解壓縮(檔名需與gitlab設置的檔案名一致)  
* cd到資料夾位置  
* 使用`git remote set-url <remote_name> <new_url>`指定遠程倉庫URL  
* 使用`git pull`將檔案抓下來  
  * 若是在連接gitlab有問題，可以試試看先連接遠端倉庫-> git pull->將pull下來的檔案內容換成git_practice.zip的內容  
  * 若出現權限問題，記得看看是不是ssh問題，ssh config沒有的話需自行建立  
* 使用`git add .`將文件放入暫存區  
  
## 問題  
* git pull後顯示出現conflict  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image1.png" width="500px"><br>  
* 下圖為文件出現conflict的示意圖，點擊上方選項選擇要保留的內容  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image2.png" width="500px"><br>  
  
## 解決方法  
* 修改過後的檔案為下圖  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image3.png" width="500px"><br>  
* commit完之後上傳  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image4.png" width="500px"><br>  
* 發送pull request  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image5.png" width="500px"><br>  
  
# HW3 - use CVAT to label dataset  
## 前置作業  
* 創立[CVAT](https://www.cvat.ai/)的帳號  
* 創建一個project名為**car_segmentation**並把labels加進去(顏色記得更改較容易辨別)  
* 在car_segmentation的project下創建task，並將資料夾`car_segmentation`內的五十張照片放入  
* 完成後點擊Jobs開啟工作頁面  
  
## 使用方法與結果  
* 使用左側的AI工具協助標註圖片  
* 其標註成果如下圖所示，在右側欄位會顯示標註的物件  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image6.png" width="500px"><br>  
* 完成標註後點選左上方Menu下載成**coco 1.0**格式  
* 下載下來的檔名為`car_segmentation_annotations_coco.zip`，內為圖片標註資訊的json檔  
  
