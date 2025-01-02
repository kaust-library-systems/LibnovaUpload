# LibnovaUpload

Upload some troublemakers to Libnova

## Items to Upload

| ID                                                                                  | Unzipped in Data Waha?          | created new SIP? | December 2024 Priority | Note                                                           |
| ----------------------------------------------------------------------------------- | ------------------------------- | ---------------- | ---------------------- | -------------------------------------------------------------- |
| 013_002_0024                                                                        | re-extract using Docker         |                  | High                   | Not Found in Datawaha, Preservica AWS or FRED                  |
| 013_002_0029                                                                        | re-extract using Docker         |                  | High                   | Not Found in Datawaha, Preservica AWS or FRED                  |
| 001_002_0001                                                                        | yes (zips removed)              | base path error  | Medium                 | New bag in E:\LibnovaUpload                                    |
| 002_ADMINISTRATION                                                                  | yes (zips removed)              | base path error  | Medium                 | New bag in E:\LibnovaUpload                                    |
| 003*CONFERENCES_WORKSHOPS_EVENTS -<br> Winter_Enrichment_Program_WEP*-\_web_archive | re-extract using Docker         | base path error  | Medium                 | /mnt/datawaha/preservica/work/003_CONFERENCES_WORKSHOPS_EVENTS <br> E:\LibnovaUpload\003_CONFERENCES_WORKSHOPS_EVENTS|
| 003                                                                                 | yes (zips removed)              | base path error  | Medium                 |
| 003_003                                                                             | re-extract using Docker         | base path error  | Medium                 |
| 004                                                                                 | yes (zips removed)              | base path error  | Medium                 |
| 004_002                                                                             | re-extract using Docker         | base path error  | Medium                 |
| 004_006                                                                             | yes (zips removed)              | base path error  | Medium                 |
| 004_012                                                                             | re-extract using Docker         | base path error  | Medium                 |
| 005                                                                                 | yes (zips removed)              | base path error  | Medium                 |
| 005_005                                                                             | re-extract using Docker         | base path error  | Medium                 |
| 005_006                                                                             | re-extract using Docker         | base path error  | Medium                 |
| 007                                                                                 | yes (zips removed)              | base path error  | Medium                 |
| 007_001                                                                             | re-extract using Docker         | base path error  | Medium                 |
| 007_002                                                                             | re-extract using Docker         | base path error  | Medium                 |
| 008                                                                                 | yes (zips removed)              | base path error  | Medium                 |
| 008_001_web_archive                                                                 | try zipping using Docker/bagger | base path error  | Medium                 |
| 009_001_0010                                                                        |                                 | failed Upload    | Medium                 |
| 009_001_0017                                                                        | re-extract using Docker         | base path error  | Medium                 |
| 009_001_0018                                                                        | re-extract using Docker         | base path error  | Medium                 |
| 010                                                                                 | base path error (SIP)           |                  | Medium                 |

## BagIt Container

The procedure:

1. Create the [BagIt container](https://github.com/kaust-library/clamdock?tab=readme-ov-file#bagit).
1. Create the file with the information of the bag.
1. Run the container.

File with the details for the Bag

```
PS E:\LibnovaUpload> cat .\001_002_0001_env.txt
SOURCE_ORGANIZATION="KAUST"
EXTERNAL_IDENTIFIER="001_002_0001"
INTERNAL_SENDER_DESCRIPTION="internal description"
TITLE="001_002_0001"
DATE_START="2024-12-29"
RECORD_CREATORS="KAUST_Library"
RECORD_TYPE="rec_type"
EXTEND_SIZE="123456"
SUBJECTS="Subject"
OFFICE="Office"
PS E:\LibnovaUpload>
```

Docker run to create the container

```
PS E:\LibnovaUpload\001_002_0001> ls


    Directory: E:\LibnovaUpload\001_002_0001


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         10/4/2021  11:08 AM                002_EMERGENCY_OPERATIONS_CENTER_CORONA_CRISIS_MANAGEMENT_TEAM


PS E:\LibnovaUpload\001_002_0001>
PS E:\LibnovaUpload\001_002_0001> pwd

Path
----
E:\LibnovaUpload\001_002_0001


PS E:\LibnovaUpload\001_002_0001>
PS E:\LibnovaUpload\001_002_0001> docker run -it --rm --env-file ../001_002_0001_env.txt `
>> -v "E:\LibnovaUpload\001_002_0001:/mydir" `
>> --name 001_002_0001 mybagit bagit.py --contact-name 'Eamon' /mydir
PS E:\LibnovaUpload\001_002_0001> ls


    Directory: E:\LibnovaUpload\001_002_0001


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
da----        12/29/2024   3:17 PM                data
-a----        12/29/2024   3:18 PM            421 bag-info.txt
-a----        12/29/2024   3:18 PM             55 bagit.txt
-a----        12/29/2024   3:18 PM           7003 manifest-sha256.txt
-a----        12/29/2024   3:18 PM            238 tagmanifest-sha256.txt


PS E:\LibnovaUpload\001_002_0001>
```
