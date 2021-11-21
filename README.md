# Bash-script-calculator
this is a calculator created for a class assignment in the Bash script language created in Linux terminal



#!/bin/bash
#Faisal Musa 002-39-6860
echo "Welcome to Calculator"
answer="yes"
while [ $answer == "yes" ]
do 
echo "Please enter an equation, or cancel to exit the program"
read equation

if [[ $equation =~ [0-9]*\+[0-9]* ]]
then
num1=`echo $equation | awk '{print $1}'`
num2=`echo $equation | awk '{print $3}'`
echo $(($num1+$num2))

elif [[ $equation =~ [0-9]*\-[0-9]* ]]
then
num1=`echo $equation | awk '{print $1}'`
num2=`echo $equation | awk '{print $3}'`
echo $(($num1-$num2))

elif [[ $equation =~ [0-9]*\*[0-9]* ]]
then
num1=`echo $equation | awk '{print $1}'`
num2=`echo $equation | awk '{print $3}'`
echo $(($num1*$num2))

elif [[ $equation =~ [0-9]*\/[0-9]* ]]
then
num1=`echo $equation | awk '{print $1}'`
num2=`echo $equation | awk '{print $3}'`
echo $(($num1/$num2))

elif [[ $equation =~ [0-9]*\%[0-9]* ]]
then
num1=`echo $equation | awk '{print $1}'`
num2=`echo $equation | awk '{print $3}'`
echo $(($num1%$num2))

elif [ $equation == "cancel" ] 
then
answer="no"
echo "This program is over"
elif [ $equation == "clear" ]
then 
clear
echo "Program has been cleared"
else
echo "wrong input, please try again"
fi
done

