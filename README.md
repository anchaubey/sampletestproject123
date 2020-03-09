
# sampletestproject123
1) I cloned the initial repo on the local laptop  https://gitlab.com/kagarwal0205/sampleproject.git.


2) Created a repo on github. Made it public repo by checking the option "Anyone can see this repository. You choose who can commit.
".


3) Created a local directory, coiped all the files to that directory. Ran the following commands

i) echo "# sampletestproject123" >> README.md

git init

git add README.md

git commit -m "first commit"

git remote add origin https://github.com/anchaubey/sampletestproject123.git

git push -u origin master



4) path to the Jenkinsfile is https://github.com/anchaubey/maven-web-application/blob/master/Jenkinsfile. It has all the steps to execute the pipeline.

I have made this project paramitrerized so that the user can provide the directory name dynamically.

Every time a user executes the job, they will have to provide the new folder path and the date will be appended.

The post build script to copy the new build is below:-

#!/bin/bash
pwd
NEWDIR=`mkdir -p $DIR-$(date +%H-%M-%S)`
cp -r /var/lib/jenkins/workspace/sample-project/*.jar $NEWDIR/

$DIR is what the user will provide when the job is executed.
