### Build a Website using Amazon EC2 with LAMP
##### 說明：  
在完成第 2 堂雲端服務課程後，藉由 Linux 2 虛擬機完成安裝，並成功啟動網頁伺服器與資料庫伺服器的功能。

##### YouTube：  
* [Install a LAMP web server on Amazon Linux 2](https://youtu.be/gRz443boolo)
* [Secure the database server](https://youtu.be/TzmEQj3U3O4)

**STEP 1**  
至Amazon EC2申請主機（作業系統為Linux2，也可選Ubuntu）  
![image]( https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4af34e56-88ac-4e5a-992e-d3f71c83117f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T031348Z&X-Amz-Expires=86400&X-Amz-Signature=6fe0f4bbaa0ab2c216e3549469b8d822bb0aa3d96df7640fb4f5e994fce093c0&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")  


**STEP 2**  
連線至Amazon主機
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/426a50fc-5974-4a08-bdb7-1cbf440f02c9/.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T031359Z&X-Amz-Expires=86400&X-Amz-Signature=1d3cfe316ba153c07dae7d6853ef8f2e4cb4cd50990f2082a2ed6e4de3444dc7&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D".png")

**STEP 3**  
使用SSH連線方式
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/d4d3b4d2-5936-4255-8856-ba41fb9acb85/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T031852Z&X-Amz-Expires=86400&X-Amz-Signature=d84987a6f402451165dbbfab0a5341ed6b6d970225e588ad5e219e38d6482e81&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5cd87f62-fc2c-4d2b-8e4c-ec058c11c1d0/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T032517Z&X-Amz-Expires=86400&X-Amz-Signature=24be0c1c498063df273c4676344fdfc57bc17ce2f8aa1ebbb3ec4d7b5e1a6af7&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")
###### LAMP → 灌至電腦，可同時擁有Web Server、Database Server
###### L ：Linux
###### A：Apache（Web Server）
###### M：My SQL（Database）
###### P：php、python（程式語言）
[Install a LAMP web server on Amazon Linux 2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-lamp-amazon-linux-2.html)  

[Install LAMP (Linux, Apache, MySql & PHP) on AWS EC2 with Ubuntu 18.04](https://usefulangle.com/post/96/aws-ec2-install-linux-apache-mysql-php-phpmyadmin-lamp-stack-ubuntu-18-04)  
##### 之所以可透過SSH方式連線是因為傳入規則（Inbound rules）有將SSH服務打開
    甚麼是SSH？   
    SSH是Secure SHell protocol的簡寫，經由將連線的封包加密的技術，進行資料的傳遞。  
    -參考資料  
    http://linux.vbird.org/linux_server/zspace/new0310telnetssh.php#ssh - SSH伺服器
    https://jennycodes.me/posts/security-ssh - 你該知道所有關於 SSH 的那些事
      
 
**STEP 4**
至安全群組，將http服務打開
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/265c320d-a684-4225-a16a-652aa5bef40e/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T032700Z&X-Amz-Expires=86400&X-Amz-Signature=0bc9a9032b3acc8a42372c2650d4683fed11606ab7d748e4f2394dfb4e187df1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")  
    
    
**STEP 5**  
開啟後設定文件權限
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/ea981441-fe83-404e-b5a0-26843fbefeea/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T032741Z&X-Amz-Expires=86400&X-Amz-Signature=4414654c863b80a025c2ab94ec9570e020d433db2ddbd67deee99b130d62b5b4&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5694e99f-88fd-4d3c-bc17-b977042f57b4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T032811Z&X-Amz-Expires=86400&X-Amz-Signature=20bff2a5139ae5aecf485bf9d65e9abe4e6b38b178cb537541fbf8de26b4c3ff&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")  

至虛擬機查看網頁
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/56703595-2b10-46ed-a0df-4434afff2190/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T032849Z&X-Amz-Expires=86400&X-Amz-Signature=af287b9baeaf87f77b696fc59332980158f9b4ba0cb77271d6ad8e33d9d2d61e&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")  
Web Server正常開啟

**STEP 6**  
接續架設Database Server
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/f5625394-9b9e-4e56-86bc-e0373c0afea3/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T033045Z&X-Amz-Expires=86400&X-Amz-Signature=21395b4a73d8be6a1e562a26a3d009b996aa5d478db289159ac0634754cbd473&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")
[How To Install Apache On Ubuntu 18.04](https://phoenixnap.com/kb/how-to-install-apache-web-server-on-ubuntu-18-04)  
  
  
架設好Database Server，安裝phpMyAdmin，視覺化資料庫，方便查看  
進入phpMyAdmin介面
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7efd9c03-b57d-406e-8579-4ffc9cb14e31/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T033208Z&X-Amz-Expires=86400&X-Amz-Signature=f08401c975bcb442a5a7910afe89a9386386532213b5ff15c87c3347a5a30a7c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")  
![image](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/9c94a3d6-b89d-44c1-9fff-8b53c49a3c4a/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210322%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210322T033231Z&X-Amz-Expires=86400&X-Amz-Signature=3b7a4b7e9ae21216686e0684c06f5129972593f701d7307643bae859756aa7a9&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D"Untitled.png")
Database Server架設成功
