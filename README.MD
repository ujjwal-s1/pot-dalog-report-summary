```
pot-[product_code]/
├─ any/                         <--- any libraries, resources, tools, config, docs, libraries for all backends
│  ├                                               
│  ├─ res/
│  ├─ tools/
│  ├─ config/
│  ├─ doc/
│  ├─ lib
│  ├                                               
├─ [b|f]e[x]/                   <--- "b" a backend, "f" for a frontend and "x" is the number starting with 1
│  ├                                 
│  ├─ requirements.txt          <--- for python
│  ├─ lib/                      <--- any library files specific to this service only
│  ├─ run.py                    <--- Docker entrypoint used
│  ├─ res/                      <--- resources files - icons, images
│  ├─ src/                      <--- any other files which are not libraries (which?)
│  ├─ tools/                    <--- scripts of any kind which are used in development but are not required in Production
│  ├─ tests/                    <--- unit tests
│  ├─ config/                   <--- configuration file(s) used during service execution
│  ├─ doc/                      <--- documentation relevant during development process
│  ├                                               
├─ ml[x]/
├─ .gitignore
├─ README.md                    <--- explains in 2-3 words what each backend or frontend does
```

Note:
* each be1..n, fe1..n folder will have a Docker image created
* each service (permanently running process listenting to a port) shall have his own Docker container. Each Docker container can have only one parent process (run.py) and multiple child processes
* each Docker image which doesn't run a service but on demand various scripts shall have all the scripts in the "src" folder ("lib" only for the support libraries)
* [How to use CI Pipeline](https://groupit.atlassian.net/wiki/spaces/PIIO/overview?homepageId=832209167)
* [How to use CD Pipeline](https://groupit.atlassian.net/wiki/spaces/ITDEP/pages/893976577/Deployment+Manual)
