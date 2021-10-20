Openlabs is a immersive learning platform which provides step by step instructions on how to get started with technology.

You can try out our amazing stuff [here](https://openlabs-explorer-dev.mybluemix.net/explorer?g=openlabs-explorer/mariadb-operator).


### Steps

-   Clone the following repository: https://github.ibm.com/openlabs-explorer/demo

-   Modify the values in the index.yaml to match your branding and need.

-   Detailed file instructions for the files referenced in the index.yaml will be present in the /content/ directory.

### Structure

![Structure](_images/structure.png 'Structure')

### Configuration file (index.yaml)

**Branding Information**

```
name: Openlabs Demo
description: Easy to ease imersive learning platform.
branding:
    logo: _images/logo.png
    banner: _images/banner.png
    textColor: '#012748'
    header:
        link: https://developer.ibm.com/openlabs/demo
        text: IBM Openlabs
        logo: _images/logo.png
license: MIT
duration: 1 hour
categories:
    - Learning
intro: README.md
documentation: https://github.com/openlabs-explorer/demo/blob/main/README.md
```

-   name: Name of the solution / product
-   description: Good description for your product/solution
-   branding: It has key ,value pairs which you can provide for customizing the page as per branding.
-   documentation: Click to your documentation page
-   intro: Name of the markdown page which is used for the Overview section.

**Commands**

```
commands:
    - name: Clone Template
      cmd: git clone https://github.com/openlabs-explorer/demo.git
      cwd: /home/student/projects
      stepMessage: Cloning repository ....
```

Commands is a list so you can provide multiple commands. Commands will be executed in order.

-   name: Name for the Step
-   cmd: Command that needs to be executed
-   cwd: Current working directory (If not provided, it will default it to the default location i.e HOME)
-   stepMessage: Realtime message that we wan't the user to see while the installation is in progress.
