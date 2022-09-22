# 快速建立你的靜態網站(S3)

![image](https://user-images.githubusercontent.com/103306835/172284892-ede94367-6210-4eee-82c0-6827c34e37d3.png)


# 使用資源(請先至下載並解壓縮)

1.範例網頁資料連結：https://github.com/EISCFCU/AWSCPE-20220816/blob/main/wildrydes-site-master.zip
![image](https://user-images.githubusercontent.com/103306835/184571040-58299072-fc11-45c9-853c-7aaccfe1c9f0.png)

# 實施步驟

![image](https://user-images.githubusercontent.com/103306835/172282245-df7b6c48-5437-4886-9b6b-86295e4ff3b9.png)

# 步驟1：新增S3 Bucket


1.搜尋[S3]

![image](https://user-images.githubusercontent.com/103306835/172282851-47dacda8-4944-4158-9055-e6582adc1564.png)

2.點選[S3]

![image](https://user-images.githubusercontent.com/103306835/172282920-d203c3f1-ec29-41e4-9c33-3170d79aaee1.png)

3.點選[Create bucket]

![image](https://user-images.githubusercontent.com/103306835/172282943-af99edbc-a263-4df4-b157-f84328ca2440.png)

4.輸入Bucket Name

![image](https://user-images.githubusercontent.com/103306835/172282979-c217e597-2bf0-4edc-a8c2-b82eda31e468.png)

5.點選ACLs enabled

![image](https://user-images.githubusercontent.com/103306835/172283009-17a21a22-dac6-48f1-b8e4-b135f6b751ea.png)

6.取消勾選Block all public access

![image](https://user-images.githubusercontent.com/103306835/172283035-f8ca5fe2-3117-49f8-9d84-2eaf918d7e02.png)

7.勾選[I acknowledge..]

![image](https://user-images.githubusercontent.com/103306835/172283061-42307a77-101f-45b4-b785-7cd982280ba0.png)

8.點選[Create bucket]

![image](https://user-images.githubusercontent.com/103306835/172283092-09efccec-4d96-4fd4-b605-944f7e95e0ee.png)

# 步驟2：上傳網頁資料

1.點選新增的Bucket

![image](https://user-images.githubusercontent.com/103306835/172283156-a522afdf-946f-471f-9b98-6babea123592.png)

2.點選[Upload]

![image](https://user-images.githubusercontent.com/103306835/172283180-5a5e2fb4-3569-426e-bd93-f26438c819f5.png)

3.將網站資料拖曳到下方畫面

![image](https://user-images.githubusercontent.com/103306835/172283202-4273e960-2ccc-4d30-a244-96bf7b7f4c22.png)

4.準備上傳

![image](https://user-images.githubusercontent.com/103306835/172283234-89a526b6-6860-423f-bb01-9a91115ba46b.png)

5.點選[Upload]

![image](https://user-images.githubusercontent.com/103306835/172283254-0120b054-dcc8-4edf-a706-721927996a8d.png)

6.等待資料上傳

![image](https://user-images.githubusercontent.com/103306835/172283273-2571ddb9-1edc-44f6-8b6b-ee0cb98682d3.png)

7.成功上傳

![image](https://user-images.githubusercontent.com/103306835/172283298-15f0eaca-5ce0-4b28-a767-2421920a4518.png)

8.點選[Close]

![image](https://user-images.githubusercontent.com/103306835/172283319-c98814f3-5787-40fc-868b-c2a842435526.png)

# 步驟3：設定網站託管

1.點選[Properties]

![image](https://user-images.githubusercontent.com/103306835/172283633-d8ab8874-fb2d-48db-8952-8680ea062e2b.png)

2.點選[Static website hosting] 的[Edit]

![image](https://user-images.githubusercontent.com/103306835/172283664-d12fdd33-5479-4895-932c-196b9bb8dff1.png)

3.勾選[Enable]

![image](https://user-images.githubusercontent.com/103306835/172283741-9a624150-9a8f-4a4b-9193-de6e85be1773.png)

4.輸入index document:Index.html

![image](https://user-images.githubusercontent.com/103306835/172283773-f814d6a0-55fd-44fe-9bdb-2cd60b9b3f93.png)

5.點選[Save changes]

![image](https://user-images.githubusercontent.com/103306835/172283804-36fc8206-6351-4264-a53e-3638644b56ad.png)

6.成功變更

![image](https://user-images.githubusercontent.com/103306835/172283946-2fe72873-bc51-442e-86d9-2036cce276ec.png)

7.網頁網址

![image](https://user-images.githubusercontent.com/103306835/172283995-10a16e50-48bf-432d-92e9-cddb320e646c.png)

# 出現403 Forbidden

![image](https://user-images.githubusercontent.com/103306835/172284063-46195c0c-c5ee-47cd-bcc9-0b41bc2f33aa.png)

# 步驟4：設定對外瀏覽權限

1.點選[Objects]

![image](https://user-images.githubusercontent.com/103306835/172284108-c66c1cb2-c625-440e-8676-b1cd7ab6477a.png)

2.勾選所有物件

![image](https://user-images.githubusercontent.com/103306835/172284138-013a629d-65b5-46e1-ab9b-9df1c21c4653.png)

3.點選[Actions]

![image](https://user-images.githubusercontent.com/103306835/172284177-f5c8f91e-f65e-41af-9065-52d402addd6f.png)

4.點選[Make public using ACL]

![image](https://user-images.githubusercontent.com/103306835/172284220-e73dbcba-3cc0-480e-a858-78034bbfce2f.png)

5.點選[Make public]

![image](https://user-images.githubusercontent.com/103306835/172284248-1234eeaa-5ba0-4c35-98bb-5c57894bfae7.png)

6.變更成功

![image](https://user-images.githubusercontent.com/103306835/172284289-c44eba97-ca8c-4320-8b79-79d437608c9c.png)


# 步驟5：瀏覽你的網頁

1.點選Properties

![image](https://user-images.githubusercontent.com/103306835/172284463-383fc982-06cf-4ad4-b0f0-74059ff4f4ec.png)

2.點選網頁網址

![image](https://user-images.githubusercontent.com/103306835/172284493-a8fbc173-d92f-40de-8bc1-20f1f318e0e6.png)

3.重新瀏覽網頁

![image](https://user-images.githubusercontent.com/103306835/172284524-188e728c-d91d-4961-b3f2-c7434259426c.png)


