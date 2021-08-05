# WSO2_IAM_AND_LDAP_Assignment

## 1) Downloading WSO2 IS from https://github.com/wso2/product-is/releases/download/v5.11.0/wso2is-5.11.0.zip

### 1.2) Afterwards save it to a desired location and use the following command to unzip the file

```
unzip wso2is-5.11.0.zip
```

### 1.3) After the unzipping process is complete you will see a new folder called wso2is-5.11.0 . Execute the following to start the WSO2 Identity Server

```
cd wso2is-5.11.0/bin
sudo ./wso2server.sh
```

### 1.4) Once you run the above command give it few minutes to start the WSO2 Identity Server. After few minutes you should see something like this if everything went well and the server is running.

![Screenshot from 2021-08-05 17-25-53](https://user-images.githubusercontent.com/75664650/128346054-4a16ad25-d63f-4f6e-8eb6-0bbb72667bed.png)

### 1.5) You can login to the WSO2 identity server by accessing the URL : ```https://localhost:9443/carbon``` . The default username and password is ```admin```. The login interface should look like this

![Screenshot from 2021-08-05 17-30-14](https://user-images.githubusercontent.com/75664650/128346405-bd4c1cdb-59cb-4de4-9df5-2cef67d958d4.png)

## 2) Downloading Apache Directory Studio from https://directory.apache.org/studio/downloads.html and run it

### 2.1) Download the above mentioned filed to a desired location. Afterwards use the command below to unpack the file in a new terminal window

```
tar -zxvf ApacheDirectoryStudio-2.0.0.v20210717-M17-linux.gtk.x86_64.tar.gz
```

### 2.2) Upon completion you should see a new folder called ApacheDirectoryStudio. To run Apache Directory Studio excute the below commands in the new terminal window

```
cd ApacheDirectoryStudio
sudo ./ApacheDirectoryStudio
```

### 2.3) After successfully executing the above commands Apache Directory Studio should open and it should look like this.

![Screenshot from 2021-08-05 17-40-02](https://user-images.githubusercontent.com/75664650/128347569-76fa8e80-347d-40c3-b0bb-2d0d33244c04.png)

## 3) Connecting Apache LDAP Directory Studio to WSO2 Identity Server's internal LDAP

### 3.1) Open Apache Directory Studio and right click anywhere within the Connections tab in the left hand side bottom and click New Connection . It should look like the screenshot below

![APACHE](https://user-images.githubusercontent.com/75664650/128348405-1c8698ab-f4a5-40c0-a41d-8f68d5285dd6.png)

### 3.2) Afterwards a new windows should open up. Fill in the fields by referring to the screenshot below. 

![Capture](https://user-images.githubusercontent.com/75664650/128348732-e8ea0cf7-0f73-4c26-99cc-ea3da1829d67.PNG)

### 3.3) After filling in the fields like the above screenshot. Click on the Check Network Parameter button and once clicked a new popup should show up and display "The connection was estalished successfully". Now click on Ok and hit next on the main window.

###### WSO2 IS Default LDAP Port number is 10389

### 3.4) Now you will see a new windows. Fill it referring the screenshot below. The password is admin

![Capture1](https://user-images.githubusercontent.com/75664650/128349294-0c451655-c839-4714-8127-0964993db507.PNG)

### 3.5) After filling in the fields like the above screenshot. Click on the Check Authentication button and once clicked a new popup should show up and display "The authentication was successful". Now click on Ok and hit Finish on the main window.

### 3.6) Now we have successfully added WSO2 Identity Server's internal LDAP to Apache Directory Studio and it should look like the screenshot below.

![Screenshot from 2021-08-05 17-57-04](https://user-images.githubusercontent.com/75664650/128349765-3307207e-06fd-468e-892a-e2d631334f72.png)

## 4) Adding a user, a role to the WSO2 IS and update that user profile 

### 4.1) First lets add an User. To do so login to WSO2 IS web interface mentioned in step 1.5. After logging in you should see a list in the left hand side on the browser. Under Users and Roles (1st one) click Add.(I have attached a screenshot below as well.)

![AddingUsers](https://user-images.githubusercontent.com/75664650/128352404-a9205779-0bd3-44a9-90d8-6f0364bb3da6.png)

### 4.2) After following the above step you will be redirected to a new page. Click Add New User. ( I have attached a screenshot as well)

![AddUser1](https://user-images.githubusercontent.com/75664650/128352822-f8cd052b-ebef-40e1-ba91-8ecaa8efea07.png)

### 4.3) Now you will be prompted to enter a Username, Password. Enter any username and password and click Finish. Now we have successfully added a new user.

### 4.4) Now lets add a role. Follow the same step in 4.1) and click Add New Role. (Screenshot Attached below)

![RoleAdd](https://user-images.githubusercontent.com/75664650/128353459-b48a2916-237b-4626-86c8-82b24f192b20.png)

### 4.5) After following the above step you will be prompted to enter a Role Name. Enter any name you wish and click Finish. Now we have successfully added a role.

### 4.6) Now lets assign the newly created user with the newly created role. Click on List under User and Roles which is in the left hand side. (Screenshot attached below)

![List](https://user-images.githubusercontent.com/75664650/128353909-bcdac48c-277a-49df-9498-894a531bf862.png)

### 4.7) After following the above step you will be redirected to a new page. Click on Users. (Screenshot attached below)

![UserAssign](https://user-images.githubusercontent.com/75664650/128354100-bba8fd1c-c66d-4ae7-81d5-26d9940e603d.png)

### 4.8) Now you will be redirected to a new page. In this page you will find two user one is the user admin and the other is the user that you created previously. In order to assign the newly created role to the new user click Assign Roles (Screenshot attached below)

![Role](https://user-images.githubusercontent.com/75664650/128354489-e232461f-617b-4b3c-9bea-14396c29349c.png)

### 4.9) Now you will see a list of roles including the one you created in the previous steps. Tick the newly created role and click Update (Screenshot attached below)

![Update](https://user-images.githubusercontent.com/75664650/128355004-257cd5a3-7543-45a3-99c4-528fc3cc0e76.png)

### Now we have added a new role, created a new user and assigned that new user to the newly created role.

## 5) Observing the changes that happened to the LDAP directory when changes were made to the WSO2 Identity Server user profile.

### Before adding the new role there was only a Group called ou=admin under ou=Groups. After adding the new role (I named it as IAMAssignmet) a new group was added called cn=IAMAssignment to ou=Groups.

### Before adding the new user there was only 3 users (uid=admin, uid=krbtgt,uid=ldap) under ou=Users. After adding the new user (I named it as eshamaaqib) a new user was added called uid=eshamaaqib under Ou=Users.

### I have attached some before and after screenshots below.

![Screenshot from 2021-08-05 18-13-14](https://user-images.githubusercontent.com/75664650/128356579-8a47e19f-dcf6-4b94-ac0a-186be4da24dd.png)

![Screenshot from 2021-08-05 18-49-26](https://user-images.githubusercontent.com/75664650/128356748-c4c98a7a-ade0-43d2-a7f4-7c9180380033.png)

![Screenshot from 2021-08-05 18-52-05](https://user-images.githubusercontent.com/75664650/128357124-883699dd-2016-4c33-ae8f-26884bb22c96.png)

![Screenshot from 2021-08-05 18-53-24](https://user-images.githubusercontent.com/75664650/128357270-c1892ddb-cc22-4777-a13e-ab996cd015e6.png)


## 6) Changing identity server user profile related attributes in the LDAP directory server and observe the changes from WSO2 Identity Server.

### 6.1) Before making changes first I went ahead and added more details of the user (eshamaaqib) by editing the user profile. To do so I went ahead and clicked List under Users and roles in the IS web interface and then clicked on Users then clicked on user profile. Finally you should see something like this. Fill in the fields and click update

![image](https://user-images.githubusercontent.com/75664650/128358548-38fd7c72-3836-4ee8-bd48-6150b609aef3.png)

### 6.2) The user (eshamaaqib) country is set to United States and the email is set to aaqibesham@gmail.com and Im going to change it to Sri Lanka and and change the email to test@test.com. To do so I went to the Apache Directory Studio and click on my user under ou=User. Once clicked you will see few attributes including the country and mail. To modify double click on the attribute and enter the new value (Screenshot attached below)

![editing](https://user-images.githubusercontent.com/75664650/128359297-daf3aa14-b909-432a-8877-35c7ea0e7760.png)

### I have attached some after and before screenshots below.

![Before 1](https://user-images.githubusercontent.com/75664650/128361337-4d20ea60-3f44-4aea-860d-77759b6150d9.png)

![Before 2](https://user-images.githubusercontent.com/75664650/128361358-1c6b3355-910b-4148-b21a-26449f105873.png)

![Before 3](https://user-images.githubusercontent.com/75664650/128361370-2f9f7cfb-dde2-4be4-b9d6-231d7832826f.png)

![After 1](https://user-images.githubusercontent.com/75664650/128361380-1fd19071-bc83-4386-9891-b18527d5179f.png)

![After 2](https://user-images.githubusercontent.com/75664650/128361387-55462429-d0fa-4eaa-9bd1-24afdb63134e.png)

![After 3](https://user-images.githubusercontent.com/75664650/128361395-a7f0eb6e-ad31-4e92-b33a-c1998051baf0.png)

## Screenshots 

### 1. Share an image after login in to the running WSO2 Identity Server

![Screenshot from 2021-08-05 17-11-37](https://user-images.githubusercontent.com/75664650/128412384-65d912bd-474d-4988-9f03-c61d1b7102c5.png)

### 2. Share an image after connecting the Apache Directory server to the WSO2 Identity Server

![Screenshot from 2021-08-05 17-14-29](https://user-images.githubusercontent.com/75664650/128412461-2e27b2bd-abfa-4712-a5b5-364fe1a27836.png)

### 3. Share image of the LDAP directory after updating a user, a role and a user profile from the WSO2 Identity Server.

![Screenshot from 2021-08-05 18-52-05](https://user-images.githubusercontent.com/75664650/128412705-ed9324a4-b28e-4e7f-bd8e-c23c674cad3c.png)








