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