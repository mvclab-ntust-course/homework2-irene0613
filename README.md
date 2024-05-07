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
* 下圖為文件出現conflict的示意圖  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image2.png" width="500px"><br>  
  
## 解決方法  
* 點擊出現conflict的上方選項選擇要保留的內容後，修改過的檔案為下圖  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image3.png" width="500px"><br>  
* commit完之後上傳  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image4.png" width="500px"><br>  
* 發送pull request  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image5.png" width="500px"><br>  
   
# Classwork 2-1 : Launch static website  
* 由於在命令提示字元無法執行其指令，因此改在**Git Bash**跑->成功  
* 我的問題：按照PPT執行後跑出來的介面內容有誤  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image8.png" width="500px"><br>  
  
# Classwork 2-2 : Launch your first docker app  
* 若是直接跑`glances`的話會在Docker發現三個檔案中只有兩個在Running  
* 在`docker_compose.yml`將**traefik**改成**traefik:v1.7**就可以成功跑三個檔案(感謝**wsl5300**提醒)  
* 可以開啟`http://localhost:8080`但無法開啟`http://localhost:61208`  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image9.png" width="500px"><br>
* 若是單純想要使用Glance的話，可以在命令提示字元輸入以下指令  
  ```  
  docker run -v /var/run/docker.sock:/var/run/docker.sock:ro --pid host -it docker.io/nicolargo/glances
  ```  
  
# HW2 - write Dockerfile and docker-compose.yaml  
## 環境  
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)  
  
## 前置作業  
* 下載並解壓縮`itri-bev.zip`   
* 輸入`python detect.py --view-img --nosave --weights yolov5x.pt --source video/argoverse/argoverse.mp4  --run-liteMono --run-bev --classes 2 5 7`看看跑不跑的了   
* 在下載一系列套件後，若是出現以下問題   
  ```   
  RuntimeError: Attempting to deserialize object on a CUDA device but torch.cuda.is_available() is False. If you are running on a CPU-only machine, please use torch.load with map_location='cpu' to map your storages to the CPU.   
  ```   
  可以嘗試在`detect.py`的第272、273行加入`map_location=torch.device('cpu')`，之後就可以成功執行了！  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image10.png" width="500px"><br>  
<img src="https://github.com/mvclab-ntust-course/homework2-irene0613/blob/main/images/image7.png" width="500px"><br>  
  
## 目前進度  
* 還在嘗試撰寫檔案中  
* 由於在 classwork 發現無法正確連線，因此有嘗試使用 Docker machine 解決，但沒有成功  

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
  
