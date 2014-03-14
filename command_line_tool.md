# Foxtel Command Line Tool Documentation

The command line tool has three main functions: 
- List all transfers first time failed.
- Restart single/multiple the transfers.
- Restart all available the transfers.

## Command descriptions
- List all transfers:
```ruby tool.rb list```

After press enter key, we can see the result on the terminal like as:

+----+-------------------------+---------------------+---------------------+-------------+
|                          List all first time failed transfers                          |
+----+-------------------------+---------------------+---------------------+-------------+
| Id | Transaction Id          | Asset Id            | Last Change         | Status      |
+----+-------------------------+---------------------+---------------------+-------------+
| 2  | 20140314081059558172220 | assets_test_000001  | 2014-03-14 08:11:59 | UploadError |
| 3  | 20140314081705535982490 | assets_test_000002  | 2014-03-14 08:18:05 | UploadError |
| 4  | 20140314081915869640244 | assets_test_000003  | 2014-03-14 08:20:16 | UploadError |
| 5  | 20140314082654521402149 | assets_test_000004  | 2014-03-14 08:27:54 | UploadError |
| 6  | 20140314103625239588817 | assets_test_000005  | 2014-03-14 10:39:25 | UploadError |
| 7  | 20140314104220083668214 | assets_test_000006  | 2014-03-14 10:44:20 | UploadError |
+----+-------------------------+---------------------+---------------------+-------------

- Restart single transfer:
```ruby tool.rb restart -type m 2```

The command will restart transfer with id = 2. After press enter key, the transfer will try to
upload video and xml ooyala metadata to Asperea server one time again. If failed, sent status to BCMS, 
update status of asset is error and remove this transfer from out the list.

- Restart multiple transfers:
```ruby tool.rb restart -type m 2,3,4,5```

After press enter key, we will manual restart transfers has id matched 2,3,4 or 5.

- Restart all transfer:
```ruby tool.rb restart -type all```

After press enter key, we will restart all avaiable transfers in the list.

## Other commands

- If you want more informations about the commands, please type: ruby tool.rb -h.
- If you want to check version: ruby tool.rb -v


