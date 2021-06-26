---
title : "Add a File "
description: >
    How to Add a File 
---
#  How to Add a File ?

The following are guides to Add a File  with Git:

#### User interface Method

* You can see the folder in your branch

* Open content folder 

* You can create a new file in wiki folder or infrastructure folder

* Click on plus icon and click on New file as shown in below image

 ![add file](/images/documentation/add-file.PNG)

* Write name of file with file extension .md, as show in below image

 ![add file](/images/documentation/add-file_01.PNG)

#### Cmd Method

* Click on Clone Button on top right side and copy the link as shown in below image 

 ![add file](/images/documentation/add-file_02.PNG)

 * Then in your local machine open the drive which you want to clone the project, right click and click on "git bash here" a window will be open 

* Type in window 
```bash
git clone -b your-branch-name your-cloned-url
```


* To run project on local type in cmd window
```bash
hugo server
```
* After clone the whole project directory is created in your local machine 

* Here is a content folder and a wiki folder in content folder, Make a file or folder which you want in wiki folder. and in file give some file information like, and same file with ,md extention.

```bash
---
title : "File Name  "
description: >
   File Description 
---
```

* After cpmplete your file then open cmd window and write followind commands to commit your file

```bash
Ctrl+c ( press enter key )

git add . ( press enter key )

git commit -m "Short Description of your work"  ( press enter key )

git pull ( pull latist copy of files.  press enter key )

git push  ( press enter key )
```