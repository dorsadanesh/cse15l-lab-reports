# Lab Report 5

## grade.sh code:
```
set -e
rm -rf student-submission
git clone $1 student-submission

// check if the correct file has been submitted

if[[ -f student-submission/ListExamples.java]]
then 
    cp TestListExamples.java student-submission
    cp -r lib student-submission
    cp Server.java student-submission
    cp GradeServer.java student-submission
else 
    echo "ListExamples.java not found. Check filename."
    echo "Score is 0."
    exit 1
fi cd student-submission

// compile tests

set +e
javac -cp .:lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java 2> err.txt

if[[$? -eq 0]]
then
    echo "COMPILE SUCCESS"
else 
    echo "COMPILE ERROR"
    echo "Your score is 0."
    exit 1
fi
```
