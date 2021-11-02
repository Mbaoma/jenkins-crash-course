# jenkins-crash-course

This repository contains an introduction to Jenkins.

## Downloading and Installing Jenkins on localhost (Linux - Ubuntu machine)

[Guide](https://www.jenkins.io/doc/book/installing/linux/)

## Setup Git on Jenkins

- From the ```manage Jenkins``` tab, click on ```manage plugins```

![image](https://user-images.githubusercontent.com/49791498/139858284-98a59fae-bb1f-4fe2-a92b-281c59a2cff2.png)

- Search if Git is installed under the ```installed``` tab.

![image](https://user-images.githubusercontent.com/49791498/139858703-d9fcf961-8ce2-4c0b-a41d-af8dbc5178d1.png)

## First Jenkins Job

- Click on ```New item``` or the prompt on the ```Welcome to Jenkins``` page.
![image](https://user-images.githubusercontent.com/49791498/139860898-8235b48d-0d71-4ba6-aee9-a7a569e585c4.png)

- Name your project and for this scenario, click on ```Freestyle Project```; click ```OK```.

![image](https://user-images.githubusercontent.com/49791498/139861447-2a2a335a-dc94-4097-bed7-670bd6c34810.png)

### Configure GitHub repository

- Navigate to ```Manage Jenkins```, click on ```Manage Credentials```.

- Click on ```Jenkins```
![image](https://user-images.githubusercontent.com/49791498/139867921-13312077-c175-414c-b5c9-e45f4cb64a73.png)

- then, ```Global credentials```
![image](https://user-images.githubusercontent.com/49791498/139868181-a4bfeb51-9b95-4fa1-bade-f63425871430.png)

- then, ```Add credentials```
![image](https://user-images.githubusercontent.com/49791498/139868477-df425176-65ad-47c6-bb39-fb0a1e73c100.png)

- Fill out the prompt
![image](https://user-images.githubusercontent.com/49791498/139869194-52fa2058-a754-4ee4-a19f-beb7fd7e09ff.png)

- Navigate to your job and fill the prompt under ```Source Code Management```.
![image](https://user-images.githubusercontent.com/49791498/139870838-0c56f691-44f0-4037-9333-bd53bb4efe79.png)

*Under branch, type in the name of the branch you want to build*.

- Click ```apply``` and ```save```.

- Click ```Build job```, to build the job. The status of the run can be seen under the ```build history``` tab.

![image](https://user-images.githubusercontent.com/49791498/139871062-6fd57da1-270a-4bd5-913b-dc26a30e0090.png)

## Using Jenkins CLI

- Navigate to ```Manage Jenkins```, click on ```Configure security```
![image](https://user-images.githubusercontent.com/49791498/139917805-a7b3d6a0-556b-4a6c-b4c7-166bfe251786.png)

- Enable security
![image](https://user-images.githubusercontent.com/49791498/139929260-50f4023b-8f2e-4dc0-8846-3ed806e939bb.png)

- Click ```Apply``` and ```Save```.

- In your browser, enter the following URL:

```bash
http://localhost:8080/cli/
```

*browser*
![image](https://user-images.githubusercontent.com/49791498/139918661-f624d663-26cf-418d-9362-a12b64f557f0.png)

- On your terminal, navigate to the location of the above file and run the following command

```bash
java -jar jenkins-cli.jar -s http://localhost:8080/ -webSocket help
```

## Running a Job using CLI

- Get the ```build``` command, from the cli command page

![image](https://user-images.githubusercontent.com/49791498/139933032-b9d75550-3a97-42a9-b2d6-a1c3b321e307.png)

- Update the security options
![image](https://user-images.githubusercontent.com/49791498/139917805-a7b3d6a0-556b-4a6c-b4c7-166bfe251786.png)

- ![image](https://user-images.githubusercontent.com/49791498/139940145-68aa19e7-9c2d-43fe-9267-5fe530ce6808.png)
Click ```Apply``` and ```save```.

- To execute your job, run the following command

```bash
java -jar jenkins-cli.jar -s http://localhost:8080/ -webSocket build <job name> [-s] [-v]
```

![image](https://user-images.githubusercontent.com/49791498/139940707-3e44945e-6824-4f63-8f9d-ba350bbc6206.png)


