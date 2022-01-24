- ## how to get remote desktop to work via VNC Viewer
  - go to:
    - ```
        setting -> sharing
      ```
  - toggle the ***sharing*** switch at the top of the window
  - select
    - ```
        screen sharing
      ```
      - a small window will open
  - toggle the ***screen sharing*** switch at the top of the window
  - click on the radio-button for ***Require a password***
  - enter a password
    - this password will be used on the VNC Viewer client when attempting to connect to the host
  - dis-able encryption for remote desktop connection with VNC Viewer by entering the following command at the CLI
    - ```
        gsettings set org.gnome.Vino require-encryption false
      ```
  
---
---

- ## how to dis-able encryption for remote desktop connection with VNC Viewer 
  - enter this following line at the CLI
    - ```
        gsettings set org.gnome.Vino require-encryption false
      ```
  
---
---
    


