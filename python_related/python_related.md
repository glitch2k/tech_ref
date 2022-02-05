# File Actions Related
  * ##### loop thru each line of a file
	```python
	with open('hostname_to_ip_address_mapping-v1.txt', 'r') as file2:
		for line in file2:
			print(line)
	```
---
---


# Using RegEx in Python
click here [[regex_related]] for more RegEx docs
  * ##### use name capturing groups and value from group
    ```python
	pattern = '(?P<dev_name>.+)\.americantower\.com|\.americantower\.idm'
    string = item['DNS Name']
    match = re.search(pattern, string)
    sub_string = match.group('dev_name')
    sub_string = sub_string.upper()
    ```
---
---

# Python Virtual Environment 
  * ##### how to create a virtual environment
    ```python
    # python3 -m [virtual_environment_name]
    python3 -m zero_fox_layer
    ```
  
  * ##### how to active a virtual environment
    ```python
    # source [virtual_environment_name]/bin/activate
    source zero_fox_layer/bin/activate
    ```
---
---
