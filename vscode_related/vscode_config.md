# how to set tab space for a file type
  - enter command palette by
    - **ctrl + shift + p**
  - type
    - ***Configure Language Specific Settings***
  - select the appropriate file type
    - ***markdown***
  - a json config fie will appear
  - search in that file for that file type section
    - ***"[markdown]"***
---
## NOTE:
  - if that file type section does not exist, then you have to creat a section for that file type
---

  - create or modify the **markdown** section of the json file to look like this
    - ```
        "[markdown]": {        
        "editor.wordWrap": "on",
        "editor.quickSuggestions": false,
        "editor.tabSize": 2
        }
      ```
    - this line of code will be placed in the first section of the **json** file
  - before closing the json file, test the modified setting
  - if the setting is good, then close the json config file