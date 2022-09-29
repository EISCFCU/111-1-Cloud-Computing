#  Lab 雲端資料庫實作（RDS）

建立雲端資料庫(MySQLDB)


# 預期實施架構

![image](https://user-images.githubusercontent.com/103306835/163801264-6e21b6ee-5fd6-4d29-9299-ce325e50b463.png)

1.選擇 Databases->點擊 Create database

![image](https://user-images.githubusercontent.com/103306835/166851850-0ac75d84-0c5a-4100-980c-594c16f98359.png)

2.選擇 MySQL

![image](https://user-images.githubusercontent.com/103306835/166851863-0d74cad0-fafa-46d9-93ed-97875242100f.png)

3.選擇Free Tier

![image](https://user-images.githubusercontent.com/103306835/166851891-d4bdc05f-55ae-41f1-ae49-ef24dd1a9894.png)

4.設定資料庫

'''
DB instance identifier ：lab-db
Master username：main
Master password：lab-password
Confirm password：lab-password
'''

![image](https://user-images.githubusercontent.com/103306835/166851904-f63ad32d-8a37-4119-92ec-c4d562fa20e9.png)

5.Burstable classes (includes t classes)->選擇 db.t3.micro

![image](https://user-images.githubusercontent.com/103306835/166851986-10cbb5d4-3c2b-46c4-9d6b-9f68a8c4ef50.png)

6.Storage type：General Purpose (SSD)->Allocated storage：20

![image](https://user-images.githubusercontent.com/103306835/166852007-4323f0ce-6fc9-4889-8e67-e156baf38cf7.png)

7.Virtual Private Cloud (VPC)：Defalt VPC

![image](https://user-images.githubusercontent.com/103306835/166852047-11c77aaf-9349-4d51-bad4-39e8d06a38ff.png)

8.DB Security Group (資料庫安全組)->選擇db-sg

![image](https://user-images.githubusercontent.com/103306835/184650770-926f3c1e-3ec3-4112-ab64-366566bd1779.png)

9.選擇us-east-1a

![image](https://user-images.githubusercontent.com/103306835/184650794-8848b88b-5277-4265-a0ee-c38d90b26c2e.png)


10.展開  Additional configuration (其他配置)->Initial database name：lab

![image](https://user-images.githubusercontent.com/103306835/166852134-8c733217-343b-47f2-a461-3578545457c7.png)

11.資料庫備份監控設定

取消選取 Enable automatic backups (啟用自動備份)

取消選取 Enable Enhanced monitoring (啟用增強監控)

12.點擊 Create database (創建數據庫)

![image](https://user-images.githubusercontent.com/103306835/166852184-a3222568-0874-4fec-a350-eed970b6293c.png)


直到狀態變為Modifying（正在修改）或 Available（可用）
