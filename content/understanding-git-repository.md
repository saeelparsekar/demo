---
title: Git Repository
description: Guide to git repository structure, format, and files
---

### Introduction

GitHub repository is the primary requirement of the explorer to run. You need to create a ***Public*** repository in GitHub in a predefined structure. Entire content that is seen on the Explorer will be the content you create or put in this GitHub repository.

### Structure of the repository

The user can choose where he wants to create the repository, however, it has to be created with a predefined structure and necessary set of files.

![gitstructure.png](_attachments/gitstructure.png)


### index.yaml

This is the Configuration file that is responsible for rendering the GitHub content onto the explorer application.

The entire configuration file is divided into multiple sections, each section details are described as below:

- **Metadata Section:**

    This section contains all the metadata information like name, description, documentation links, Branding data, etc which will appear in the Banner section of the page.

    - ***Name:*** Name of the Lab
    - ***Description:*** A brief description about the Lab
    - ***Branding:*** Branding of the lab
        - ***logo:*** Brand logo which will appeare on header and banner
        - ***banner:*** Banner image , preferrably of high resolution
        - ***textColor:*** Color of the text which will appeare in banner section
        - ***header:***
            - ***link:*** Link to the title in the header
            - ***text:*** Title text which will appeare in the header
            - ***logo:*** Logo to appeare in the beside title on header
    - ***license:*** Type of licence of the lab
    - ***duration:*** Time required to complete the lab
    - ***categories:*** What the lab is categorised into
    - ***intro:*** File name which will appeare in the cover section of the UI
    - ***documentation:*** Link to the documentation.

- **Commands Section:**

    This section is used to mention any prerequisite commands required to run the lab. 

    - ***commands:***
         - ***name:*** Title, or What the command is for 
           ***cmd:*** The command to be run
           ***cwd:*** Directory in which you want to run the command
           ***stepMessage:*** This will be the message shown on UI while the command is getting executed.

- **Environment Section:**

    This section of the YAML file will have tab-related details which will be shown on the UI once the user has provisioned an Instance.

    - ***environment:***
        ***terminal:***
            ***name:*** Name of the tab which will render terminal.
            ***enabled:*** Show/Hide terminla tab
        ***ide:***
            ***name:*** Name of the tab which will render IDE.
            ***enabled:*** Show/Hide IDE tab
            ***url:*** URL of the IDE , which will be iframed into the tab
        ***application:***
            ***name:*** Name of the tab which will render Application.
            ***url:*** URL of the Application , which will be iframed into the tab
            ***enabled:*** how/Hide Application tab

- **Config Section:**

    This section of the YAML contains information about the type of authentication used, whether to auto-execute the prerequisite commands and what type of Service this lab will use.

    - ***config:***
        ***auth:*** Type of authentication used. ibmId, appId etc
        ***launchBtn:***
            ***buttonLabel:*** Text that will appeare on button that is used tp provision / launch the lab
        ***execCmd:*** 
            ***autoExecute:*** Auto execute prerequisite commands ON/OFF
            ***buttonLabel:*** Button text for CTA used to execute prerequisite commands
    - ***backend:***
        ***service:*** Type of Service

- **Tile Info Section:**

    This section of the YAML will have information to render the ***Readme Panel Section***.

    ***tileInfo:***
    - ***title:*** Title of the tutorial or guide.
      ***description:*** Brief description of the tutorial or guide.
      ***duration:*** Time required to complete the section
      ***content:*** name of the MD file which has the content. this file will be the one inside the ***content*** folder


### Readme.md

This MD file will contain a brief overview of your lab/operator. you can enter some cover data about the lab which will help the user understand the lab better. it supports MD content along with images and videos.

### _images

This folder will contain all your images, videos , logos, etc. you will have to reference the images in your code with ***_images/<imagename-with-extension>***

### content

This Folder will contain all the tutorials or documentation guide files. these files are MD files and they follow a specific format to be rendered within the readme panel.

    Sample File: 

    ```
    ---
    title: Sample MD file   
    description: Sample which shows the format to be used while creating a tutorial or guide MD files
    ---
    
    ### Section 1

    Section one content following MD guidelines

    ### Section 2

    Section two content following MD guidelines

    ```

    <image how content will be shown>

This concludes the tutorial on Git Structure. In the next tutorial, we will explain the process of creating a git repo with all the mentioned guidelines and exploring the same on the Explorer UI.