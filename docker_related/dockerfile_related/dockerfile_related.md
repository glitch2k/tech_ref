# **WORKFLOW TO CREATE A *"dockerfile"* TO CREATE A CUSTOM IMAGE**

  1.  identify the base image to create the custom igame
  2.  update the base kernel and upgrade all packages
  2.  create a directory that will be the app working directory
  3.  establish the ***"working diectory"***
  4.  create ***".dockerignore"*** file and poppulate it with files and
      directory you do not want to be copied when using the ***"COPY"***
      dockerfile instruction
  4.  copy all relative files, directories & source codes to the
      working directory
  5.  set any required ***"environment variables"*** that must be used
      within the image
  6.  expose any ports that must be open when a container is created
      from this image
  7.  create the user acct that must be used by the container to run
      the app
  8.  instruct the container to use the user acct created above to
      run the app in the container
  8.  use the ***"ENTRY"*** instruction to tell docker what kernel
      command to start the container with
  8.  use the ***"CMD"*** instruction to pass the arguments to the
      ***"ENTRY"*** instruction kernel command if needed      