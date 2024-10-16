# How to Install and Configure the webMethods API Gateway on Linux


Before we begin, we need to do following:
1. Download the installer from this [link](https://github.com/ikromnurrohim/webmethods-api-gateway-guide/blob/master/installer/SoftwareAGInstaller20240105-Linux_x86_64.bin)
2. Have an account to download or install product of webmethods product, if you don't have one, please register [here](https://empower.softwareag.com/register/)
3. Have a Linux machine and access to SSH Console


### Installation
Open your linux SSH Console then put the installer file to directory **/home/$user** after that we need to create a directory to store our installation, in this case we want to install api gateway on directory **/opt/apigw** if you don't have created that folder before please run command 
```bash 
mkdir /opt/apigw 
```
after creation directory we need to change permission the installer file to be executeable with this command 
```bash
chmod +x SoftwareAGInstaller20240105-Linux_x86_64.bin
```
then if the file permission been change to be executeable we need to run this file using this command
```bash
sh SoftwareAGInstaller20240105-Linux_x86_64.bin -console
```


After that we need to Enter [N]

![2024-10-16_20-50](https://github.com/user-attachments/assets/4c903602-4ecf-49f7-bab4-58d4498269ab)

then Enter [N] twice and fill the username and password that you been registered on softwareag empower then Enter [N] \
Select release to install, in this case we select 1 to install webMethods 10.15

![2024-10-16_20-52](https://github.com/user-attachments/assets/0d06e287-13b5-4853-a9f0-9e4f032ddd89)

fill the Installation directory in this case **/opt/apigw** \
fill the Hostname or IP Address to be your IP or **localhost** if you installing on local machine, cause I'm install in local machine I fill **localhost** 

![2024-10-16_21-00_1](https://github.com/user-attachments/assets/22d031e3-8fb8-41bb-84c5-de141f914448)

after that select Enter [N] twice, till the console showing like below screenshot 

![2024-10-16_21-05](https://github.com/user-attachments/assets/0a9b1b86-fbae-4f27-a44f-b7e23eaeda82)

then fill **+** and Enter to Jump to products then after **API Gateway 10.15** show up, fill the number of **API Gateway 10.15** product

![2024-10-16_21-10](https://github.com/user-attachments/assets/7873f76d-5460-476f-9950-f25b426a503e)

after Enter of product number, then will showing the dependencies of that product we should Select, Enter [Y]

![2024-10-16_21-12](https://github.com/user-attachments/assets/713473e2-1456-44fb-b13a-d873594a1265)

after that will be back to the previusly page, then we should Enter [N]

![2024-10-16_21-14](https://github.com/user-attachments/assets/d4c6ad3e-f85e-4186-9ff4-d01358836a92)

after that will showing the language pack to install, it's up to you, but in this case I don't select anything just Enter [N]

![2024-10-16_21-15](https://github.com/user-attachments/assets/654fd0e4-4a02-428e-bff1-f0cf0c2da9cd)

after that we will see the Select Updates will be installed, this up to you but my recomendation if you not have any concern to install in specific fix version, just select All to be install updated product

![2024-10-16_21-16](https://github.com/user-attachments/assets/8be123dc-4009-4acc-b8f1-a8d589202fd2)

in the bottom of this section will be showing the detail of Total Download Size etc, then Enter [N]

![2024-10-16_21-19](https://github.com/user-attachments/assets/0ab9b1e1-31fe-4df6-947e-989b4bfa2b88)

after that we need to fill the default password of Administrator user, then just Enter [N] if you don't wanna required changes on first product login

![2024-10-16_21-22](https://github.com/user-attachments/assets/b191d00e-438d-4c98-895e-d5d1ee884278)

Select No in Use Sudo

![2024-10-16_21-24](https://github.com/user-attachments/assets/fb959ac9-10ef-4313-a5d5-b9bf43d31ef5)

after that, fill the blank with your valid license of API Gateway\
the instance name and port number fill as you want, in this case I use the default instance name and port\
and if you want the API Gateway register as UNIX demon meaning startup automatically when the System startup just fill [T] and Enter [N] \
but in this case I don't wanna my API Gateway startup at first my system startup so I just Enter [N]

![2024-10-16_21-28_1](https://github.com/user-attachments/assets/cdab6418-7ca1-4b56-a41e-86292204e726)

if you have multiple network just fill that and Install package now been selected automatically, in this case we just Enter [N]
![2024-10-16_21-34_1](https://github.com/user-attachments/assets/2fcac5ac-6a4e-49b9-9a70-1288c35eb6f2)

in Intergation Server section, the installer ask me to use which database connection, in this case I use embeded database \
in API Gateway section, the installer ask me to select which port API Gateway UI will be, in this case I use default port \
in API Data Store section, the installer ask me to select which port API Data Store (elasticsearch) will be, in this case I use default port 

![2024-10-16_21-39_1](https://github.com/user-attachments/assets/bc7822c7-8854-46e5-a941-4f145ed2eeb6)

if you plan to use command central for product manager, you should just Enter [N] but in this case I don't wanna use command central, so I just Enter [T] and Enter [N]

![2024-10-16_21-42](https://github.com/user-attachments/assets/8889c95b-eae0-4c71-88ff-c5a1d98595c1)

after that it will be show the product list that ready to install, you just need to Enter [N] and it will be installing

![2024-10-16_21-44](https://github.com/user-attachments/assets/f7f89d54-ee14-43cf-9365-1139b528a617)
![2024-10-16_21-45_1](https://github.com/user-attachments/assets/e290f682-6537-4679-93ea-1c31760d54b9)


