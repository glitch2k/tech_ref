# capture groups related
  * ## use named captured groups
    * ```
          pattern = '(?P<ip_addr>\d+\.\d+\.\d+\.\d+) (?P<dev_name>*)'
      ```
      * ## the above pattern uses 2 capture groups to separate the sub-strings after the match
      * ## the group names are:
        * ## ip_addr
        * ## dev_name