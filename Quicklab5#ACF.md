

# 情境
逢甲科技自2020年成立，從事雲端資訊應用與資訊系統委外託管服務。
近期黑貓購物拓展通路從電視電話購物至網路購物，委託將現有資訊系統搬遷到雲端。
然而，公司並沒有過多的資訊人員可以協助雲端搬遷。
因此第一階段討論會議，先將將庫存系統部署在AWS雲端上，後續維運交回給黑貓購物資訊人員進行管理。
請協助逢甲科技進行分析、設計與實體的建置。

以下是客戶在會議中提出的需求

1.網站需要24小時穩定對外開放

2.管理者可以異動網站上的庫存資訊，這些庫存資訊將會集中管理

3.公司沒有過多的伺服器(你可以想像是電腦)可以閒置，但網站伺服器要能因應購物人潮流量。需求峰值期間仍然可以保持高性能


# 實作環境：AWS Academy Learner Lab(課程代號：13467)

登入AWS Management Console

![image](https://user-images.githubusercontent.com/103306835/170182604-7e0e16c7-a178-45ab-88eb-8beb8fc69f91.png)

# 實施步驟

![image](https://user-images.githubusercontent.com/103306835/170182628-f2f1dea7-4a79-4689-b6e5-7782266df200.png)


# 任務1：基礎架構實施

目標：進行雲端服務架構的安全性部署

1.基礎架構規劃

![image](https://user-images.githubusercontent.com/103306835/170182776-06044e36-10cf-426c-9a2b-8e48f6902eaf.png)

2.點選[VPC]

![image](https://user-images.githubusercontent.com/103306835/170182820-d701c1fc-ac5e-4e81-bc68-17c5ea1267dd.png)

3.您的VPC

![image](https://user-images.githubusercontent.com/103306835/170182917-989b358f-985c-4acb-9378-cda6e85e02f1.png)

4.點選Work VPC

![image](https://user-images.githubusercontent.com/103306835/170182953-433e8b47-0f49-447d-b270-b6af05c93145.png)

5.改成Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170182979-2d5bf837-7d4b-498a-ba86-5cd164a82b72.png)

6.點選[儲存]

![image](https://user-images.githubusercontent.com/103306835/170182998-88beb920-9faa-44ef-bd49-4824bd9f2816.png)

7.成功更改VPC

![image](https://user-images.githubusercontent.com/103306835/170183208-e9604936-944c-49f4-97fe-b4caedd263ba.png)

8.點選[子網路]

![image](https://user-images.githubusercontent.com/103306835/170183252-7bf9e9a6-cef2-4332-8afc-8001796b7f5b.png)

9.選擇Work Public Subnet

![image](https://user-images.githubusercontent.com/103306835/170183522-145b7351-b587-44f3-be77-fb5cd95e5acd.png)

10.更名為Public Subnet1 並點選儲存

![image](https://user-images.githubusercontent.com/103306835/170183591-97e9de77-ef10-4b2c-a8e7-bfee51caf42c.png)

11.更名成功

![image](https://user-images.githubusercontent.com/103306835/170183623-685612bb-b733-4bf2-b3d0-b370b4ef0c65.png)

12.點選[建立子網路]

![image](https://user-images.githubusercontent.com/103306835/170183726-4f1d9898-465a-4503-b883-aa99c4686b49.png)

13.選擇Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170183753-aab3d636-957d-48b8-a3f4-2cc6f3cb2e6a.png)

14.輸入子網路名稱/可用區域/IPV4 CIDR區塊 Public subnet2(10.0.2.0/24 ；us-east-1b)

![image](https://user-images.githubusercontent.com/103306835/170183812-357d17a6-37e4-408e-8ac6-5942ff70cb92.png)

15.點選[新增子網路]

![image](https://user-images.githubusercontent.com/103306835/170183880-9f1b290b-7b16-48bd-be72-df3af9021d46.png)

16.輸入子網路名稱/可用區域/IPV4 CIDR區塊 Private subnet1(10.0.1.0/24;us-east-1a)

![image](https://user-images.githubusercontent.com/103306835/170184205-e7f8fb62-2a05-4a0f-9f91-bc7bd8d6a03b.png)

17.點選[新增子網路]

![image](https://user-images.githubusercontent.com/103306835/170184290-7336be2a-13d7-4533-9421-812606442fad.png)

18.輸入子網路名稱/可用區域/IPV4 CIDR區塊 Private subnet2(10.0.3.0/24；us-east-1b)

![image](https://user-images.githubusercontent.com/103306835/170184406-58ae1c27-8e32-4cb4-9234-36cbf3e97a2c.png)

19.點選[建立子網路]

![image](https://user-images.githubusercontent.com/103306835/170185203-91df4c1d-eb2d-47c9-93c6-ab40607720f7.png)

20.正在建立子網絡…

![image](https://user-images.githubusercontent.com/103306835/170185248-9f15eca0-4c96-43aa-ba83-22be7bef17af.png)

21.成功新增子網路

![image](https://user-images.githubusercontent.com/103306835/170185441-c0c4daf9-ff77-47c3-acd3-3c66e6c7669c.png)

22.勾選Public Subnet1

![image](https://user-images.githubusercontent.com/103306835/170185558-3abd396c-3a4a-4748-aa09-79a2e32ee7f3.png)

23.點選[動作]

![image](https://user-images.githubusercontent.com/103306835/170185603-5d820cf9-631f-4fbb-b903-388ec03f5cbf.png)

24.點選[編輯子網路設定]

![image](https://user-images.githubusercontent.com/103306835/170185697-70777349-f444-43e7-b986-2472a27ce64c.png)

25.勾選[啟用….]

![image](https://user-images.githubusercontent.com/103306835/170185728-aadba0d5-abdb-4d1a-8ac4-c5e2aeae6f88.png)

26.點選[儲存]

![image](https://user-images.githubusercontent.com/103306835/170185800-2c9a8b84-5d65-4c21-99a9-500dbb27170a.png)

27.完成更新

![image](https://user-images.githubusercontent.com/103306835/170185828-1d754fde-9186-425a-8e46-da1796e5a9dd.png)

28.請參考Public Subnet1 Auto-ip設定進行Public Subnet2 Auto-ip設定

![image](https://user-images.githubusercontent.com/103306835/170185988-2dd41613-a0bd-43a9-aa45-a3bbd321c35e.png)

# 任務2：架設網站伺服器

目標：建立網站伺服器(作業系統：Linux)，並直接部署網站在上面。

1.點選EC2

![image](https://user-images.githubusercontent.com/103306835/170186206-f1c26900-8ea0-4963-8bd7-ada6bb7d4f3a.png)

2.點選[執行個體]

![image](https://user-images.githubusercontent.com/103306835/170186248-faf05b5c-a09b-488a-82f3-14a65c83a67b.png)

3.點選[啟動執行個體]

![image](https://user-images.githubusercontent.com/103306835/170186283-eb03dc7e-612d-4322-ba7c-045abd619d99.png)

4.名稱：WebServer

![image](https://user-images.githubusercontent.com/103306835/170186309-8297d053-6bdd-4631-aae0-2fb3ae6caab6.png)

5.作業系統點選[Amazon Linux]

![image](https://user-images.githubusercontent.com/103306835/170186553-113efbbc-6dc0-4669-a00a-226bdb85feae.png)

6.選擇預設金鑰：vockey

![image](https://user-images.githubusercontent.com/103306835/170186582-e09acb70-0071-4e3b-b098-c20766d709f7.png)

7.點選[編輯]

![image](https://user-images.githubusercontent.com/103306835/170186645-3b8fb8d7-d498-46ad-b8f3-4ce6354783a5.png)

8.選擇Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170186677-e5b5a724-bd98-4979-9dbc-e1571037f00b.png)

9.選擇在us-east-1a的子網

![image](https://user-images.githubusercontent.com/103306835/170186708-9804217a-b67e-4d00-8ed7-0bb2d8fffc1d.png)

10.選擇建立安全群組

![image](https://user-images.githubusercontent.com/103306835/170186743-fc15b34d-5436-4b47-adbe-59072e1c3093.png)

11.命名為WebServer

![image](https://user-images.githubusercontent.com/103306835/170186790-649ceea0-68cd-46cd-8c64-75de035249cb.png)

12.選擇SSH類型 來源：0.0.0.0/0

![image](https://user-images.githubusercontent.com/103306835/170186822-41f3745f-3ea4-48d7-938f-95bbef1ad92f.png)

13.點選[Add security group rule]

![image](https://user-images.githubusercontent.com/103306835/170186872-91de4621-814c-4ed2-96ed-4318f1c0e3f5.png)

14.選擇HTTP(瀏覽器) 來源：0.0.0.0/0

![image](https://user-images.githubusercontent.com/103306835/170187076-5a3478b8-ab2f-4cb3-bc15-8bbd05a5f113.png)

15.展開[進階詳細資訊]

![image](https://user-images.githubusercontent.com/103306835/170187099-0ff21ca5-82ef-49ef-ac21-cb52867b58e8.png)

16.選擇IAM 

![image](https://user-images.githubusercontent.com/103306835/170187212-2497561a-d94c-4ae4-a541-0fe52eba25ea.png)

17.LabInstanceProfile

![image](https://user-images.githubusercontent.com/103306835/170187246-a5b6de41-be5b-4cc7-8cff-0f6a72c29eac.png)

18.貼上Userdata資料

![image](https://user-images.githubusercontent.com/103306835/170187278-7eaf4d75-6723-4b85-9f1c-3a4fb3416448.png)

```

#!/bin/bash
# Install Apache Web Server and PHP
yum install httpd mysql -y
amazon-linux-extras install -y php7.2
# Download Lab files
wget https://fcucclabcode.s3.amazonaws.com/lab-app.zip
unzip lab-app.zip -d /var/www/html/
# Download and install the AWS SDK for PHP
wget https://github.com/aws/aws-sdk-php/releases/download/3.62.3/aws.zip
unzip aws -d /var/www/html
# Turn on web server and ensure running on reboot
service httpd start
chkconfig httpd on
```


19.點選[建立執行個體]

![image](https://user-images.githubusercontent.com/103306835/170187346-8f833455-3c83-4d2c-bf93-48399ec3c8fc.png)

20.點選[檢視所有執行個體]

![image](https://user-images.githubusercontent.com/103306835/170187403-f69511d7-3064-47e9-9ece-a4791e19d1ea.png)

21.重新整理

![image](https://user-images.githubusercontent.com/103306835/170187474-881d3a9a-17fd-49d8-929e-701a648eee19.png)

22.出現新增的伺服器

![image](https://user-images.githubusercontent.com/103306835/170187513-4b6b54ed-c138-4eef-b2e7-3bef22ed7c28.png)

23.更新狀態

![image](https://user-images.githubusercontent.com/103306835/170187538-222e6306-e0b4-4864-a138-40abd4d22354.png)

24.發現2/2項檢查通過

![image](https://user-images.githubusercontent.com/103306835/170191630-19ae7d9f-7c5d-4d5a-8cdd-58f40732dd2d.png)


25.勾選WebServer伺服器

![image](https://user-images.githubusercontent.com/103306835/170192288-1c7fd8c2-2bf8-424b-8828-b2d75ba0d180.png)


26.在Details頁籤 複製 IPv4 address

![image](https://user-images.githubusercontent.com/103306835/170192331-d2ffd7a4-156e-4b95-8719-6ab845dce01e.png)


27.開啟無痕

![image](https://user-images.githubusercontent.com/103306835/170192396-61d55c37-fe2a-46b8-bc36-cd1efedd4f95.png)


28.將IPv4 address 貼到無痕

![image](https://user-images.githubusercontent.com/103306835/170192434-c1e7a0df-7c00-47d0-8481-9bf8a797c339.png)


29.任務2結果示意圖

![image](https://user-images.githubusercontent.com/103306835/170192472-e5140600-b4b5-4afa-84e3-ca64168a7899.png)


30.實施架構

![image](https://user-images.githubusercontent.com/103306835/170192521-2c8e66a6-c640-4a5a-a09b-5e6ca66d553f.png)


# 任務3：建立資料庫服務器

目標：建立網站所需的資料庫服務。

1.點選[安全群組]

![image](https://user-images.githubusercontent.com/103306835/170192635-cf24cef4-6103-43e4-83ef-a58453726371.png)

2.點選[建立安全群組]

![image](https://user-images.githubusercontent.com/103306835/170192752-4502ebfb-5567-4403-b3d7-6e680f557b58.png)

3.輸入安全群組名稱與描述

![image](https://user-images.githubusercontent.com/103306835/170192804-183930f2-07a5-402e-9461-438778b9083f.png)


4.選擇Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170192842-028611e0-f9f4-4897-82ac-3a3bb3e71e64.png)

5.設定傳入規則

![image](https://user-images.githubusercontent.com/103306835/170193312-db6e0cba-2813-4a27-a0bb-976ed4c621f6.png)


6.點選[建立安全群組]

![image](https://user-images.githubusercontent.com/103306835/170193335-c522b0b5-d1b0-432f-9ea3-a31df3b7330b.png)


7.成功建立安全群組

![image](https://user-images.githubusercontent.com/103306835/170193351-8c9285a0-c287-4e9b-8e4a-85f6bef59b5c.png)


8.搜尋RDS 並點選RDS

![image](https://user-images.githubusercontent.com/103306835/170193376-91aae952-685c-473c-b86d-c792d3fef3d1.png)


9.點選子網路群組

![image](https://user-images.githubusercontent.com/103306835/170193421-80f76c4a-d6c4-41d4-bfb9-653ecb8a60af.png)


10.點選[建立資料庫子網路群組]

![image](https://user-images.githubusercontent.com/103306835/170193484-ef2225e5-e4aa-432c-9a9f-73e3dcd27675.png)

11.設定名稱、描述與VPC

![image](https://user-images.githubusercontent.com/103306835/170193506-c261ba28-dd7d-48a7-88fa-a85ea30b00fe.png)


12.設定可用區1a、1b(子網路10.0.1.0/24、10.0.3.0/24)

![image](https://user-images.githubusercontent.com/103306835/170193558-f52c7bea-55c7-4031-b389-bd16a96c3b75.png)


13.點選[建立]

![image](https://user-images.githubusercontent.com/103306835/170193572-78d8ad72-371f-4040-a581-60f7edd81295.png)


14.點選資料庫

![image](https://user-images.githubusercontent.com/103306835/170193703-4c1c7946-0b11-4b33-9e0f-f3c162acb3fb.png)


15.點選[建立資料庫]

![image](https://user-images.githubusercontent.com/103306835/170193744-c52625be-e6fc-484f-86fb-c6d740f074ad.png)


16.選擇MYSQL

![image](https://user-images.githubusercontent.com/103306835/170193798-ae872875-ae6b-432f-a025-09668a2822cd.png)


17.選擇免費方案

![image](https://user-images.githubusercontent.com/103306835/170193841-471b4e51-dbe9-4d8c-be66-4357256b8122.png)

18.資料庫名稱與帳密設定

![image](https://user-images.githubusercontent.com/103306835/170194025-8f8cd551-a395-4fd6-8e26-03832a66a46a.png)

19.選擇爆量類別

![image](https://user-images.githubusercontent.com/103306835/170194211-7ab18b2e-c6c6-4973-aab1-9034ba9ff9cb.png)

20.選擇Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170194246-e1a4b52e-24cb-49fc-a9d3-115cb18239c6.png)

21.選擇子網路群組：db-subnet-group

![image](https://user-images.githubusercontent.com/103306835/170194541-f677c745-20cf-440c-a437-8758a87a4e88.png)

22.選擇現有的VPC安全群組

![image](https://user-images.githubusercontent.com/103306835/170194587-9cb8f3c5-6422-42f2-98fa-70b66843417e.png)

![image](https://user-images.githubusercontent.com/103306835/170194687-cc3ccdaf-1b38-4127-a895-f18f5e2d0594.png)

23.展開[其他組態]

![image](https://user-images.githubusercontent.com/103306835/170194745-4c1bf253-edfb-43de-ad39-2f03e424468c.png)

24.設定初始資料庫名稱：lab(請務必輸入此名稱)

![image](https://user-images.githubusercontent.com/103306835/170230495-87699833-a85b-4bc5-aecd-eb0f7b029c05.png)

25.點選[建立資料庫]

![image](https://user-images.githubusercontent.com/103306835/170194846-a840b395-8b9c-4ca8-9dfb-1839790f33ad.png)

26.等待資料庫狀態變可用

![image](https://user-images.githubusercontent.com/103306835/170194916-76e36660-07e6-4679-b8b3-3ca215fd1c57.png)

27.回到網頁 設定Endpoint

![image](https://user-images.githubusercontent.com/103306835/170195242-2a8be799-7a2a-4444-9672-811c457286c2.png)

28.點選Save

![image](https://user-images.githubusercontent.com/103306835/170195280-3f0c7a84-4bb6-426f-98c3-3bda71f9ee6a.png)

29.任務3結果顯示

![image](https://user-images.githubusercontent.com/103306835/170195322-461a3d4d-db65-4190-af56-575520070a53.png)

目前實施架構

![image](https://user-images.githubusercontent.com/103306835/170195365-1f593f3f-7679-452f-93cd-6f91f79ce065.png)

# 任務3：建立擴展與水準負載架構

1.點選[動作]

![image](https://user-images.githubusercontent.com/103306835/170195453-ba59e3ae-edb5-4c3d-8830-ceda8efd0fad.png)

2.建立映像

![image](https://user-images.githubusercontent.com/103306835/170195799-cb40f714-e0de-484d-8748-6b904dac1702.png)

3.輸入映像名稱與描述

![image](https://user-images.githubusercontent.com/103306835/170198589-eb738964-e8e9-4e7a-bdef-69da9af5eb3b.png)

4.點選[建立映像]

![image](https://user-images.githubusercontent.com/103306835/170198622-5aef8306-25f3-45d4-80db-df77f627c279.png)

5.成功建立映像

![image](https://user-images.githubusercontent.com/103306835/170198684-bf053e1b-3441-48c0-91ed-a9fd9cce4159.png)

6.搜尋[負載平衡器] 並點選

![image](https://user-images.githubusercontent.com/103306835/170198772-4233dc1f-2168-4def-9d16-c8a77f489ddb.png)

7.點選[建立負載平衡器]

![image](https://user-images.githubusercontent.com/103306835/170200276-badfa08b-e79f-4df8-94b9-a33cd478fb63.png)

8.點選[Application Load Balancer]的[建立]

![image](https://user-images.githubusercontent.com/103306835/170200601-0387a25a-12ad-475c-ac51-75d39b9a181b.png)

9.輸入名稱 LabELB

![image](https://user-images.githubusercontent.com/103306835/170201500-cf0015c9-3209-4b4c-90c1-6e61d06d7111.png)

10.選擇VPC

![image](https://user-images.githubusercontent.com/103306835/170202624-75f55e72-977d-45e4-9f97-5203ea8b16fe.png)

11.選擇AZ與Subnet

![image](https://user-images.githubusercontent.com/103306835/170202661-14dd6710-d606-447d-93a2-c422e0739ed2.png)

12.選擇[WebSecuritygroup]

![image](https://user-images.githubusercontent.com/103306835/170202727-e3c790ad-eecf-4b52-ac9d-10187216d9da.png)

13.點選[建立目標群組]

![image](https://user-images.githubusercontent.com/103306835/170202769-d4836753-ac39-400e-b594-a4b74d1cafbb.png)

14.選擇[執行個體]

![image](https://user-images.githubusercontent.com/103306835/170202824-1c4e5fb3-c86b-4cee-889d-8c3ac650f878.png)

15.設定目標群組名稱：LabGroup

![image](https://user-images.githubusercontent.com/103306835/170202890-9021123e-50a3-4b44-aeab-00c6222e9a09.png)

16.點選[下一步]

![image](https://user-images.githubusercontent.com/103306835/170202932-23fad3cb-54af-4523-8db2-d4640f095f09.png)

17.選擇任務2所建的伺服器(名稱：WebServer)

![image](https://user-images.githubusercontent.com/103306835/170203024-cf22ee80-4552-4689-a196-b445d8665e33.png)

18.點選[建立目標群組]

![image](https://user-images.githubusercontent.com/103306835/170203084-0fcc247f-eb9f-4a60-9afa-70896d87bfac.png)

19.成功建立目標群組

![image](https://user-images.githubusercontent.com/103306835/170203136-2a32864d-78ce-45b4-b4d1-f043e568764d.png)

20.重新整理

![image](https://user-images.githubusercontent.com/103306835/170203222-2ff31a58-876e-4ee1-b79d-8ab617c54111.png)

21.目標群組選擇LabGroup

![image](https://user-images.githubusercontent.com/103306835/170203294-55d61e95-69d4-45be-b4f5-14a22bd3c46d.png)

22.點選[建立負載平衡器]

![image](https://user-images.githubusercontent.com/103306835/170203332-5f1ffd2d-8da8-45fe-9f29-eff6d6a1ea1e.png)

23.點選[檢視負載平衡器]

![image](https://user-images.githubusercontent.com/103306835/170203369-82ef76a8-6a5b-41aa-a050-460229f8b50e.png)

24.點選[啟動組態]

![image](https://user-images.githubusercontent.com/103306835/170203414-394b59cc-1ec9-4e69-860d-d24cb83a17ef.png)

25.點選[建立啟動組態]

![image](https://user-images.githubusercontent.com/103306835/170203445-70bc6446-814f-41a4-8b93-f078a8f8489e.png)

26.輸入名稱與自動擴展的AMI

![image](https://user-images.githubusercontent.com/103306835/170203478-672efb74-db70-40d4-b6a2-60640bf2907f.png)

27.選擇執行個體類型

![image](https://user-images.githubusercontent.com/103306835/170203516-8bf953e2-dbd4-4f1c-ad5a-b25e52d7f447.png)

28.輸入t3.micro

![image](https://user-images.githubusercontent.com/103306835/170203549-d5b362e1-607a-4f86-b3f4-a11e23560b93.png)

29.選取t3.micro 並點選[選擇]

![image](https://user-images.githubusercontent.com/103306835/170203596-a28776d8-490a-4b0f-8492-e8569f34d9ec.png)

30.出現所選的執行個體類型

![image](https://user-images.githubusercontent.com/103306835/170203882-500ae316-baeb-4c9b-b2fc-e230183fa9cb.png)

31.選擇IAM Role：LabInstace

![image](https://user-images.githubusercontent.com/103306835/170203936-ac41d090-df44-4e58-a3f7-b2367a52431e.png)

32.勾選監控

![image](https://user-images.githubusercontent.com/103306835/170203966-6ac2941a-d9a3-455b-9ac9-eea3197f3b03.png)

33.選擇現有的安全群組(Web Security Group)

![image](https://user-images.githubusercontent.com/103306835/170204008-ae601802-c19b-456b-a82d-043aa98bbd5a.png)

34.輸入金鑰對vockey 並勾選[我知道…..]

![image](https://user-images.githubusercontent.com/103306835/170204045-e2632dc7-b827-4cf6-854b-262e29d62ce6.png)

35.點選[建立啟動組態]

![image](https://user-images.githubusercontent.com/103306835/170204367-6ea3716b-b79c-426f-96ae-714e1c6f017f.png)


36.成功建立啟動組態(Auto Scaling)

![image](https://user-images.githubusercontent.com/103306835/170204496-ef4c2fd1-0fc5-4fdf-b927-5f755dc53b8e.png)

37.勾選名稱為LabConfig的啟動組態

![image](https://user-images.githubusercontent.com/103306835/170204655-54260e3b-b43d-49f4-b0b5-daddb8672ada.png)

38.點選[動作]->[建立Auto Scaling群組]

![image](https://user-images.githubusercontent.com/103306835/170204709-1605cf38-5d61-4d46-ae42-e6ef4ca630ed.png)

39.輸入群組名稱Lab Auto Scaling Group

![image](https://user-images.githubusercontent.com/103306835/170204736-95674ede-ef24-40fc-a9bf-2053c7803500.png)

40.點選[下一步]

![image](https://user-images.githubusercontent.com/103306835/170204780-a6018625-a0aa-4817-b1ea-770ecbfbcb96.png)

41.選擇Auto Scaling的VPC

![image](https://user-images.githubusercontent.com/103306835/170204821-ed6fdb5d-3531-4c43-917f-6a82b2bc1255.png)

42.選擇Auto Scaling的自動擴展的子網

![image](https://user-images.githubusercontent.com/103306835/170204917-a02a804a-be3b-4fa2-bf06-555912db15cf.png)

43.點選[下一步]

![image](https://user-images.githubusercontent.com/103306835/170204953-328dbfa2-00db-4532-a216-ee3f2ba4e65c.png)

44.選擇現有的負載平衡器(Load Balancer)(連接Auto Scaling與Load Balancer)

![image](https://user-images.githubusercontent.com/103306835/170205200-d6a0a924-a061-4463-a4dc-486ce56b884e.png)

45.選擇[從您的負載平衡器目標群組中選擇]

![image](https://user-images.githubusercontent.com/103306835/170205263-e57f1184-a9c3-48bb-94c3-ccb1f57275c0.png)

46.選擇[LabGroup]

![image](https://user-images.githubusercontent.com/103306835/170205319-9ef12bfd-ec63-42c1-b81d-5a4a80e93886.png)

47.勾選監控

![image](https://user-images.githubusercontent.com/103306835/170205375-03011aee-3d4e-4cca-8d25-293df48aff3c.png)

48.點選[下一步]

![image](https://user-images.githubusercontent.com/103306835/170205418-b9cf3088-a414-4544-bec3-6be47b09eb51.png)

49.設定自動擴展的EC2上下限

![image](https://user-images.githubusercontent.com/103306835/170205454-8677e258-1b5d-4f2e-8fe5-728c04a3bd24.png)

50.點選[目標追蹤擴展政策]

![image](https://user-images.githubusercontent.com/103306835/170205499-613fed19-1e87-40af-b66f-fea90e36ab7e.png)

51.輸入擴展政策名稱、類型與目標數值 點選[下一步]

![image](https://user-images.githubusercontent.com/103306835/170205549-322d8297-b697-4d5e-9e8a-baaca5ee6f9e.png)

52.點選[下一步]

![image](https://user-images.githubusercontent.com/103306835/170205588-047326e5-6a65-4663-a00e-505164330f8b.png)

53.命名群組名稱Lab Instance

![image](https://user-images.githubusercontent.com/103306835/170205630-df032bf0-10a3-4706-8178-26f84d345624.png)

54.點選[下一步]

![image](https://user-images.githubusercontent.com/103306835/170205674-2509d9ee-8228-4084-babe-9fd2a0181595.png)

55.點選[建立Auto Scaling群組]

![image](https://user-images.githubusercontent.com/103306835/170205750-2413ca26-82bb-4b4f-9c83-08112b0929c7.png)

56.成功建立自動擴展政策

![image](https://user-images.githubusercontent.com/103306835/170205835-efee1d8b-5f70-4a82-9b33-ec619c009576.png)

57.點選[執行個體]

58.此時會多了兩台EC2
59.點選[負載平衡器Load Balancer]

60.勾選LabELB 並複製DNS name

61.另開瀏覽器視窗 並貼上網址

62.出現測試網頁

63.進行流量測試 點選[Load Test]

64.CPU 飆升

65.更新狀態 發現EC2自動擴展(不一定都是四台，有增加即可)

66.任務4結果顯示

# 目前實施架構
