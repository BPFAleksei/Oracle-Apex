# Oracle-Apex

QR-CODE handling sample. This application shows how create and load QR Codes in Oracle Apex.

Installation Steps
--------------------------

1. Download the .zip files of this directory
2. Navigate into Oracle Apex Environment to App Builder -> Import
3. Drag and Drop the .zip file and click next until finish the installation
4. Execute the SQL script into .sql file.
5. Run the application 

QRCode into table
--------------------------
![imagen](https://user-images.githubusercontent.com/32690411/137372227-21e3969d-5f9d-499a-b288-2525ead9b299.png)

Step 1. Create a classic report 

Step 2. Add Column null as QRCODE

Step 3. Create dynamic action for report 

Event: Page Load

Action: Execute Javascript

Code:
```
javascript code
$('.qrcode').each(function(){
	var qrcode = new QRCode($(this).attr('id'),{
	text:$(this).attr('data-qrcode'),
	width:65,
	height:65,
	colorDark:"#000000",
	colorLight:"#ffffff",
	correctLevel: QRCode.CorrectLevel.H
	});
});
```
	

Step 4. Add HTML Expression attribute to column QRCODE 
```
<div id="qr_#ID#" class="qrcode" data-qrcode="QR#ID#"></div>
```
Step 5. upload file as static application files

qrcode.min.js

Step 6. Set in page properties - File URLs

#APP_IMAGES#qrcode.min.js

QR Generator Button
--------------------------
![image](https://user-images.githubusercontent.com/32690411/137411827-f722b6d3-91f0-4ca8-9afe-f5fea02be5e2.png)

QR Scanner
--------------------------
![image](https://user-images.githubusercontent.com/32690411/137414452-786d3e0a-3cc7-4d7b-92e7-fe62aa890b4c.png)

I use a plugin which you can find in
[QR.CODE.SCANNER](https://apex.world/ords/f?p=100:710:10268868638450::::P710_PLG_ID:APEX.QR.CODE.SCANNER)

Online Demo
--------------------------

[View Online Demo](https://apex.oracle.com/pls/apex/sofer_test/r/apexdemo1).

User: demo_user

Password: admin123

