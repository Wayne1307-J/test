1.放置在src文件下的配置文件druid.properties:
driverClassName=com.mysql.jdbc.Driver
url=jdbc:mysql://127.0.0.1:3306/数据库名
username=root
password=root
initialSize=5
maxActive=10
maxWait=3000
2.各个函数及功能（注：返回值均为boolean，若为true则代表操作成功）
Reader：
ReaderLogin(String reader_id,String passoword);//reader的登陆
ChangeState(String reader_id,Boolean flag);//修改用户在线状态
ReaderLogout(String reader_id); //reader登出
reader个人信息的修改：
NameModify(String Reader_ID,String N_name);//修改用户名
E_mailModify(String Reader_ID,String N_Email);//修改邮箱
PasswordModify(String Reader_ID,String N_Password);//修改密码
FindPassword（String reader_id，String e_mail）；//reader通过邮箱找回密码


Librarian：
LibrLogin(String libr_id,String passoword;//librarian的登陆
ChangeState(String libr_id,Boolean flag);//修改用户在线状态
LibrLogout(String libr_id);     //librarian的登出
LNameModify(String Libr_ID,String N_Name);//librarian对自己个人信息的修改
LPasswordModify(String Libr_ID,String N_Password);//修改密码
FindPassword(String reader_id,String e_mail)；//找回reader的密码
 ReaderRegister(String READER_ID,String name,String E_mail);//reader账户注册
DeleteReader(String Reader_ID);//删除reader账户
NameModify(String Reader_ID,String N_name);//修改读者用户名
E_mailModify(String Reader_ID,String N_Email);//修改读者邮箱
PasswordModify(String Reader_ID,String N_Password);//修改读者密码
 
 Admin：
  AdminLogin(String admin_id,String passoword)；//admin登陆
  ChangeState(String admin_id,Boolean flag)； //修改在线状态
  AdminLogout(String admin_id)；//登出
  LibrRegister(String Libr_ID,String name)；//注册Librarian
  AdminRegister(String Admin_ID,String name,String password)；//admin注册
  APasswordModify(String admin_id,String password) ；//admin修改自己的密码
  DeleteLibr(String Libr_ID)；//删除Librarian用户
  LPasswordModify(String Libr_ID,String N_Password)；//修改librarian信息
  LNameModify(String Libr_ID,String N_Name) ；
  FindLPassword(String Libr_ID)；//超管帮助librarian找回密码


Book：
SearchBook（String str）；//输入任意关键词查询书籍，返回书籍的完整信息
EditLocation(String location,int book_id)；//修改书籍的位置
EditBook_Name(String book_name,int book_id)；//修改书籍的名字
EditPrice(BigDecimal price, int book_id)；//修改书籍的价格
EditCategory(String category, int book_id)；//编辑书籍类别
InsertBook(String B_Name,String author,String location,BigDecimal price )；//插入一本新的书籍
DeleteBook(String Libr_ID,intBook_ID,StringBook_Name)；//删除书籍，并将删除信息加入book_deleted中
InsertBookDeleted(String Libr_ID,int Book_ID,String Book_Name)；//将删除信息加入book_deleted中

  
  
