# LVM STORAGE MGMT
- ### Setup a LVM Storage Environment with 3 HDD
  - 3 HDD
  - create 1 Linux LVM partition on each HDD
  - create a Physical Volume (pv)
  - create a Volume Group (vg) with 2 HDD called new_vol_grp
  - create a Logical Volume (lv) with the above vg called new_lgcl_vol
  - format that lv created above with ext4
  - mount the newly created storage to a directory
  - extend the vg by adding the 3rd HDD to the vg
  - extend the lv by increasing the size of the current lv by the added of the 3rd HDD
  
  1. Partition all HDD for use with LVM
      - identify the logical name of the HDD
        ```
        lsblk
        ```
      - partition the HDD with the following consideration
        - No. of partitions
        - Partition type
          - in this example we will be creating:
            - 1 partition on each of the HDD
            - Use **LVM** partition type for each of the HDD with partition code **8e**

        ```
        fdisk /dev/sdb
        ```
        - type **"t"** to change the partition type
        - type **"8e"** to config the the partition type to be **Linux LVM**
        - type **"q"** to save the changes made to the partition table

  2. Config all HDD to be part of a LVM storage solution by creating a **Physical Volume** (pv)
      - syntax
        - **pvcreate [ logical_name_for_partitioned_HDD ... \]**
      ```
      root@ubuntu:# pvcreate /dev/sdb1 /dev/sdc1
      ```
  
  3. Create a **Volume Group** (vg) from the pv created above
      - syntax
        - **vgcreate [ vg_name ] [ logical_name_for_partitioned_HDD ... \]**
      ```
      root@ubuntu:# vgcreate new_vol_grp /dev/sdb1 /dev/sdc1
      ```
  
  4. Create a **Logical Volume** (lv) from the vg create above
      - syntax
        - **lvcreate -L [ size of volume ] -n [ logical_name_for_volume \] [ name_of_vg_used_to_create_lv \]**
      ```
      root@ubuntu:# lvcreate -L 20G -n new_lgcl_vol new_vol_grp
      ```
      - this will create a logical volume with a size of **20GB**
      - its logical name will be **new_lgcl_vol**
      - it will be created from the volume group **new_vol_grp**

  5. Format the lv created above with a file system so data can be saved on it
      - syntax
        - **mkfs.[ file_system ] /dev/[ vg_name ]/[ lv_name ]**
      ```
      root@ubuntu:# mkfs.ext4 /dev/new_lgcl_vol/new_vol_grp
      ```
      - this will format the lv **new_lgcl_vol** with ext4 file system

  6. Test mount the formated lv and save data onto it
      - create a directory to mount new storage
        - syntax
          - **mkdir [ /path/to/mnt/point ]**
      - temperary mount the storage to the directory created above
        - syntax
          - **mount [ storage_logical_name ] [ /path/to/mnt/point ]**
      ```
      # create mount point directory
      root@ubuntu:# mkdir /mnt/new_lvm_storage

      # mount the new lvm storage to the mount point
      root@ubuntu:# mount /dev/new_lgcl_vol /mnt/new_lvm_storage
      ```
      
  7. If the test is SAT, config a permanent mounting solution with the **fstab** file
    
  
  - ```

    ```


---
---

# Reading Linux Man Page


-  **bold text**
   -  type exactly as shown.
-  italic text (underlined text)
   -  replace  with appropriate argument.
-  [-abc]
   -  any or all arguments within [ ] are optional.
-  -a|-b
   -  options  delimited  by | cannot be used together.
-  argument ...
   -  argument is repeatable.
-  [expression] ...
   -  entire expression within [ ] is repeatable.
