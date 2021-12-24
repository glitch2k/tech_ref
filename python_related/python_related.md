# file actions related
  * ## loop thru each line of a file
    * ```
          with open('hostname_to_ip_address_mapping-v1.txt', 'r') as file2:
            for line in file2: 
      ```

# using regex in python related
  * ## use name capturing groups and value from group
    * ```
          pattern = '(?P<dev_name>.+)\.americantower\.com|\.americantower\.idm'
          string = item['DNS Name']
          match = re.search(pattern, string)
          sub_string = match.group('dev_name')
          sub_string = sub_string.upper()
      ```

# python virtual environment related
  * ## how to create a virtual environment
    * ```
          python3 -m [virtual_environment_name]
          python3 -m zero_fox_layer
      ```
  
  * ## how to active a virtual environment
    * ```
          source [virtual_environment_name]/bin/activate
          source zero_fox_layer/bin/activate
      ```

  