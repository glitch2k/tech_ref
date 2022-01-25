## deploy a standard nginx web-server withthe ability to change the static content on the fly while the container is running
  - test the TU on local host
    - create a ***Dockerfile*** file to create the package
      - image: 
        - std nginx image
      - volume:
        - named volume: 
          - web_static_content
        - location on container to map volume:
          - /usr/share/nginx/html:ro
      - exposed port on container
        - 80
      - access port from web broswer
        - 8888
    - Dockerfile to create the custom nginx image:
      - ```
          FROM nginx

          # make the working directory the default loaction where nginx saves its html files
          WORKDIR /usr/share/nginx/html

          # copy a custom "index.html" file to the working directory of the image
          COPY ./index.html .

          # expose port "80" on the container made from this image
          EXPOSE 80 
        ```

  - create a github actions file and save it in this path in the local branch repo
    - ```
        branch-parent-dir/.github/workflows/workflow-file.yml
      ```
    - github action file for this requirement
      - ```yaml
          # the "name" top-level key will give the workflow a logical name
          name: Custom Nginx Web Server Workflow

          # the "on" top-level key will specifies "on" what github operation & "on" which branch will trigger this workflow
          # in this example, this workflow will be triggered on a "push" to the "dev" branch
          on:
            push:
              branches: [ dev ]
            
          # the "jobs" top-level key will hold the specification of the jobs & actions that will be done when this flow is triggered
          jobs:

            # this key specifies a logical name for this jobs
            # in this example this job is intended to build a docker image & deploy it to a private "dockerhub" repo
            build-deploy:

              # the "runs-on" key specifies the host within github that will be running this workflow
              # in this example, the workflow will be ran on a host with the latest "ubuntu" operating system
              runs-on: ubuntu-latest

              # the "steps" key specifies each action that will be performed in the workflow
              # it will be a yml list, with item holding specification of one action
              # in this example, the "steps" key contains 2 items/actions
              #...the 1st action is to checkout the code from the repo into the host github is using to run this workflow
              #...the 2nd action is to build the docker image & deploy the image to a dockerhub repo specied with the key:value objects in the list item
              steps:

              - name: check-out code from repo
                uses: actions/checkout@v2
              
              - name: build and deploy docker image to dockerhub
                uses: mr-smithers-excellent/docker-build-push@v5
                with:
                  image: glitch2k/zero_fox_layer
                  registry: docker.io
                  username: ${{ secrets.DOCKER_USERNAME }}
                  password: ${{ secrets.DOCKER_PASSWORD }}
        ```



  
---
---




