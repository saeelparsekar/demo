---
title: Openlabs Explorer
description: Introduction to Openlabs Explorer and its features.
---

### Introduction

Openlabs is an immersive learning platform that provides step-by-step instructions on how to get started with technology.

### Features

- Easy to use
- Provisioned within seconds and ready to explore.
- Content can be fully controlled within the GitHub repo which makes it easy to update/modify the content.
- All the features like terminal, IDE, Application tabs can be enabled using feature flags in the YAML file.
- One-click Install of the stack/operator
- A Readme Panel will have various tutorials to help users set up or play around with the stack.

### Prerequisites

- Public Github repository in pre-defined structure and format
- Credits
- IBM / Google ID for authentication


### UI Layout

To understand the explorer UI, We can divide it into multiple sections:

<image with marked sections>

- ***Header Section***
This section will have branding details on the left which will show a logo and title with a link to your product home page and on the right-hand side it will have some lab / user-specific controls like :
    - ***Timer:*** - Shows the time remaining of your provisioned Instance
    - ***Credentials (Key Icon):*** Will display credentials and other Instance specific information.
    - ***Lab specific controls (: icon):*** Gives you actions to extend, deprovision the instance.
    - ***Readme Panel Control (? icon):*** Allows you to toggle readme panel view
    - ***User Controls:*** Gives access to Credit Manager, Logout / Login actions

- ***Banner Section***
This section will have all the metadata like name, description, categories, the time required, etc. it will also have CTA buttons to either Provision the lab or Install the prerequisite commands. Besides data and CTA, this place can be used for branding your lab by showing a banner and logo of your lab.
This section will also show Tabs like Terminal, IDE, Applications if you have them enabled in your configuration file and you have an instance provisioned.

- ***Commands Section***
This Section will display all the prerequisite commands mentioned in the configuration YAML file. it will also display the status of the command ie, whether the command ran successfully or there was an error or it's still pending execution. if there was an error in the execution of the command same will be shown below the command along with a failure status.

- ***Cover / Into Section***
This section will display a brief intro to the lab. you can enter any information which describes your lab better. it can be some content, image, or even a video.

- ***Readme Panel Section***
This Section will allow you to put a tutorial or a documentation guide that will help the end-user explore or perform certain actions in the context of the lab. this also allows images, videos, gifs, and also it has commands which can be executed or copied onto the terminal with a single click. This section is Draggable and user can drag this section to make it wider or smaller as per convenience 

This concludes the first tutorial. in the next tutorial, we will discuss the Github Repository Structure.