---
title: Filesystem Structure
layout: default
parent: System
---

<style>
    .volume-manager {
        width: 100%;
        max-width: 900px;
        background: #e4e6f7;
        padding: 20px;
        border-radius: 6px;
        box-shadow: 0 4px 12px rgba(0,0,0,0.08);
        border: 1px solid #c9cced;
    }

    .title {
        font-size: 22px;
        font-weight: bold;
        margin-bottom: 15px;
        color: #1a1a1a;
    }

    /* Main horizontal bar containing all partitions */
    .partition-bar {
        display: flex;
        height: 130px;
        border: 1px solid #b4b8e3;
        background-color: #d5d9f5;
        border-radius: 3px;
        overflow: auto;
    }

    /* Common styles for all partitions */
    .partition {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        font-size: 12px;
        color: #333;
        border-right: 1px solid #b4b8e3;
        padding: 10px;
        box-sizing: border-box;
        position: relative;
        text-decoration: none;
        cursor: pointer;
        overflow: unset !important;
    }

    .partition:hover {
        background-color: rgba(255, 255, 255, 0.18);
    }


    /* Proportional flex-basis matching the screenshot scale */
    .p1 { flex: 0 0 10%; }
    .p2 { flex: 0 0 53%; }
    .p3 { flex: 0 0 11%; }
    .p4 { flex: 0 0 11%; }
    
    .free-space { 
        flex: 0 0 15%; 
        border-right: none;
    }

    .partition div {
        margin: 1px 0;
    }

    /* Lock icon style for LUKS partition */
    .lock-icon {
        position: absolute;
        bottom: 8px;
        right: 12px;
        font-size: 14px;
        opacity: 0.7;
    }

    /* Details layout below the diagram */
    .details-section {
        margin-top: 20px;
        font-size: 15px;
    }

    .details-row {
        display: flex;
        margin-bottom: 6px;
    }

    .details-label {
        width: 90px;
        color: #616587;
        text-align: right;
        padding-right: 15px;
    }

    .details-value {
        color: #1a1a1a;
    }
</style>
{: .important}
I have not yet been able to dump the onboard [Spansion Flash](/specs.html)

<div class="volume-manager" markdown="0">
    <div class="title">Volumes: 500GB HDD</div>
    
    <div class="partition-bar">
        <a class="partition p1" href="#partition-hmx_int_stor">
            <div>hmx_int_stor</div>
            <div>/mnt/hd1</div>
            <div>Partition 1</div>
            <div>1.1 GB Ext4</div>
            <div><small>mounted as: hmx_int_stor</small></div>
        </a>
        
        <a class="partition p2" href="#partition-hmx_int_stor1">
            <div>hmx_int_stor</div>
            <div>/mnt/hd2</div>
            <div>Partition 2</div>
            <div>478 GB Ext4</div>
            <div><small>mounted as: hmx_int_stor1</small></div>
        </a>
        
        <a class="partition p3" href="#partition-hmx_int_stor2">
            <div>hmx_int_stor</div>
            <div>Partition 3</div>
            <div>11 GB Ext4</div>
            <div><small>mounted as: hmx_int_stor2</small></div>
        </a>
        
        <a class="partition p4" href="#partition-luks">
            <div>Partition 4</div>
            <div>11 GB LUKS</div>
            <span class="lock-icon">🔒</span>
        </a>
        
        <div class="partition free-space">
            <div>Free Space</div>
            <div>37 MB</div>
        </div>
    </div>
</div>

## Partition 1: hmx_int_stor (/mnt/hd1) {#partition-hmx_int_stor}
```
└── hmx_int_stor
    ├── .cache
    │   ├── program-005d-1987-0028-1195_jpg-0.jpg
    │   ├── [the rest of this folder is EXACTLY the same]
    ├── lost+found
    ├── .recycleBin
    ├── repository
    │   ├── 10.dat
    │   ├── 11.dat
    │   ├── 12.dat
    │   ├── 13.dat
    │   ├── 14.dat
    │   ├── 16.dat
    │   ├── 17.dat
    │   ├── 18.dat
    │   ├── 19.dat
    │   ├── 1.dat
    │   ├── 20.dat
    │   ├── 21.dat
    │   ├── 22.dat
    │   ├── 23.dat
    │   ├── 24.dat
    │   ├── 25.dat
    │   ├── 26.dat
    │   ├── 27.dat
    │   ├── 28.dat
    │   ├── 29.dat
    │   ├── 2.dat
    │   ├── 30.dat
    │   ├── 31.dat
    │   ├── 32.dat
    │   ├── 33.dat
    │   ├── 34.dat
    │   ├── 35.dat
    │   ├── 36.dat
    │   ├── 37.dat
    │   ├── 38.dat
    │   ├── 39.dat
    │   ├── 3.dat
    │   ├── 41.dat
    │   ├── 42.dat
    │   ├── 43.dat
    │   ├── 44.dat
    │   ├── 45.dat
    │   ├── 46.dat
    │   ├── 48.dat
    │   ├── 4.dat
    │   ├── 58.dat
    │   ├── 5.dat
    │   ├── 60.dat
    │   ├── 61.dat
    │   ├── 6.dat
    │   ├── 8.dat
    │   └── 9.dat
    ├── stb_status.xml
    ├── tripleid.xml
    ├── TVTV
    │   ├── DATA (dir)
    │   └── IMAGE (dir)
    └── .umount-proc-info

9 directories, 637 files
```

Notes:
- `.cache` appears to have a cache of images, mostly show frame grabs.
6 directories, 2 files
- The `.dat` files appear to contain EPG data in a proprietary format. I am not publishing them here, if you'd like to probe at them, join the [Discord](/discord.html)
- `.umount-proc-info` is probably the most interesting thing from this dump, and it gets its own page: [umount-proc-info](/system/umount-proc-info.html)

## Partition 2: hmx_int_stor (/mnt/hd2) {#partition-hmx_int_stor1}
```
├── .1496998823.db
├── .cache
│   └── a lot of album art and also more show thumbnails
├── dms_cds.db
├── lost+found
├── Media
│   ├── Download
│   │   └── .DS_Store
│   ├── Music
│   ├── Photo
│   └── Video
├── Recordings
│   └── this holds the recordings
├── .recycleBin
├── .tsr
├── .umma
│   ├── mnt
│   │   └── hd2
│   │       └── Recordings.dat
│   └── version
└── .umount-proc-info

13 directories, 8193 files
```

Notes:
- The `.cache` directory is interesting because it has album art for a lot of music, even though music was never intentionally used on this DVR.
- The `.db` files are SQLite databases.
- [umount-proc-info](/system/umount-proc-info.html)
- The version file says `0.9.6`.
- `Recordings.dat` suggests that this partition is mounted at `/mnt/hd2`, since it holds file paths for the recordings.
- For each recording there is:
    - `.ts`: video streams
    - `.hjs`: unclear
    - `.njs`: unclear
- `Recordings` and `Media` are accessible over SMB.

## Partition 3: hmx_int_stor {#partition-hmx_int_stor2}
```
.
└── hmx_int_stor2
    ├── diskstore
    │   ├── font-store (empty folder)
    │   └── manifest
    ├── download (ISO Media, not as in the disk image format, probably a streamed video of some kind)
    ├── lost+found (empty)
    └── .recycleBin (empty)
```

Nothing interesting here, honestly.

## Partition 4: the LUKS one {#partition-luks}

Probably the rootfs. I do not have the password.