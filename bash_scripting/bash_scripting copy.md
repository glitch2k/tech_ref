  how to print a text to screen
    echo 'hello_world' 
  assign a value to a variable
    var1='hello_world' 
  print a variable value to screen
    echo "$var1" 
    echo "${var1}" 
  print a combination of text & the variable value to screen
    echo "this will display $var1" 
    echo "this will display ${var1}" 
  apping text to a variable
    echo "${var1}ing is fun" 
  NOTE about using ('')
   the shells sees everything inside the '' as is
   so if you have:
      echo '$var1' 
   it will display
      $var1 
   but if you have:
      echo "$var1" 
   it will display the value for the variable $var1
      hello_world 
---

  display UID of current user
    echo "current user id is ${UID}" 
   the variable [UID] is a special variable maintianed by the shell
     to get more info on this variable and other special variables
        man bash 
  save the result of a command to a variable
    USER_NAME=$(id -un) 
   this will save the result of the command id -un to the variable USER_NAME
     the above command will display the current user logged in
  use if statment to verify that the user is root
    
        if [[ "${UID}" -eq 0 ]]
        then
          echo 'you are root.'
        else
          echo 'you are NOT root.'
        fi 
    
  compare the values of 2 variables in if statment
   
        UID_TO_COMPARE='0'       
       
        if [[ "${UID}" -eq "${UID_TO_COMPARE}" ]] 
        # if the value of variable ${UID} is equal to the value of variable ${UID_TO_COMPARE}
        then
          echo 'you are root.'
        else
          echo 'you are not root.'
        fi 
    

  return a non 0 exit code if a condition fails
   
        UID_TO_COMPARE='0'       
       
        if [[ "${UID}" -eq "${UID_TO_COMPARE}" ]] 
        # if the value of variable ${UID} is equal to the value of variable ${UID_TO_COMPARE}
        then
          echo 'you are root.'
        else
          echo 'you are not root.'
          exit 1 
          # returns an exit code of 1
        fi 
    
    NOTE
     to get a list of exit code for the failed execution of a command or built-in function:
        man [command | function] 
       search for exit
          / exit 

  verify if the last command execution was successful
   
        VALUE_RESULT_OF_LAST_CMD=$()
        
        if [[ "${?} -ne 0 ]]
        # if the last command exited with a code that was NOT 0 then it failed
        # if the last commanded execution failed display the text in the "then" section
        then
          echo 'the last command did NOT execute successfully'
        else
          echo 'the last command executed successfully'
    
   the special variable ${?} will store the exit code of the most recent command or function execution
  



  

