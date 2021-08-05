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

### 1.5) You can login to the WSO2 identity server by visiting the URL : ```https://localhost:9443/carbon``` . The default username and password is ```admin```. The login interface should look like this

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

