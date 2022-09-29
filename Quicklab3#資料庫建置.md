#  Lab 雲端資料庫實作（RDS）

建立雲端資料庫(MySQLDB)

# 預期實施架構

![image](https://user-images.githubusercontent.com/103306835/163801264-6e21b6ee-5fd6-4d29-9299-ce325e50b463.png)


# 實施步驟

![image](https://user-images.githubusercontent.com/103306835/174926615-7b29f3b1-3db5-412d-a479-1b06fdd59d37.png)

# Step1:建立雲端資料庫的Security group

1-1.點選左側的Security Group

![image](https://user-images.githubusercontent.com/103306835/184651053-52c5d6c3-846f-4873-9bf1-ece6e3107416.png)

1-2.點選[Create Security group]

![image](https://user-images.githubusercontent.com/103306835/184651242-27c939a0-455e-43c7-894e-a6717dd7da54.png)

1-3.Security Group Name=db-sg;Description=database security group;選擇預設的VPC

![image](https://user-images.githubusercontent.com/103306835/184651696-cb8df758-c71b-47f2-8146-ebb9c0a6fdc4.png)

1-4.點選[Add Rule]

![image](https://user-images.githubusercontent.com/103306835/184651894-1ce8923e-9534-4fb6-b190-f370501690cb.png)

1-5.Type選Mysql；Source選擇web-sg

![image](https://user-images.githubusercontent.com/103306835/192962911-aa708a77-4050-497c-a064-30f912699a80.png)

1-6.點選[Create Security Group]

![image](https://user-images.githubusercontent.com/103306835/184652100-08e885ae-a0c7-4d13-97bb-3bc609212aec.png)


# Step2:建立雲端資料庫

2-1.選擇 Databases->點擊 Create database

![image](https://user-images.githubusercontent.com/103306835/166851850-0ac75d84-0c5a-4100-980c-594c16f98359.png)

2-2.選擇 MySQL

![image](https://user-images.githubusercontent.com/103306835/166851863-0d74cad0-fafa-46d9-93ed-97875242100f.png)

2-3.選擇Free Tier

![image](https://user-images.githubusercontent.com/103306835/166851891-d4bdc05f-55ae-41f1-ae49-ef24dd1a9894.png)

2-4.設定資料庫

'''
DB instance identifier ：lab-db
Master username：main
Master password：lab-password
Confirm password：lab-password
'''

![image](https://user-images.githubusercontent.com/103306835/166851904-f63ad32d-8a37-4119-92ec-c4d562fa20e9.png)

2-5.Burstable classes (includes t classes)->選擇 db.t3.micro

![image](https://user-images.githubusercontent.com/103306835/166851986-10cbb5d4-3c2b-46c4-9d6b-9f68a8c4ef50.png)

2-6.Storage type：General Purpose (SSD)->Allocated storage：20

![image](https://user-images.githubusercontent.com/103306835/166852007-4323f0ce-6fc9-4889-8e67-e156baf38cf7.png)

2-7.Virtual Private Cloud (VPC)：Defalt VPC

![image](https://user-images.githubusercontent.com/103306835/166852047-11c77aaf-9349-4d51-bad4-39e8d06a38ff.png)

2-8.DB Security Group (資料庫安全組)->選擇db-sg

![image](https://user-images.githubusercontent.com/103306835/184650770-926f3c1e-3ec3-4112-ab64-366566bd1779.png)

2-9.選擇us-east-1a

![image](https://user-images.githubusercontent.com/103306835/184650794-8848b88b-5277-4265-a0ee-c38d90b26c2e.png)


2-10.展開  Additional configuration (其他配置)->Initial database name：lab

![image](https://user-images.githubusercontent.com/103306835/166852134-8c733217-343b-47f2-a461-3578545457c7.png)

2-11.資料庫備份監控設定

取消選取 Enable automatic backups (啟用自動備份)

取消選取 Enable Enhanced monitoring (啟用增強監控)

2-11.點擊 Create database (創建數據庫)

![image](https://user-images.githubusercontent.com/103306835/166852184-a3222568-0874-4fec-a350-eed970b6293c.png)


直到狀態變為Modifying（正在修改）或 Available（可用）
