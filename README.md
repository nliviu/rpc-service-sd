# RPC Service SD

## RPC
- `SD.GetMountPoint` - returns the mount point of the SD.
```
mos --port <serial/ws/mqtt> call SD.GetMountPoint
{
  "mount_point": "/sd"
}
```

- `SD.List` - lists the contents of the SD.
```
mos --port <serial/ws/mqtt> call SD.List
[
  {
    "name": "TEST",
    "size": 0,
    "directory": false
  },
  {
    "name": "FS",
    "size": 394,
    "directory": true
  },
  {
    "name": "TEST.PY",
    "size": 197,
    "directory": false
  }
]
```

- `SD.Mkdir` - makes a directory.
```
mos --port <serial/ws/mqtt> call SD.Mkdir '{"path": "new_dir"}'
{
  "Created": "/sd/new_dir"
}
```
- `SD.Info` - returns information about the mounted SD card
```
mos --port <serial/ws/mqtt> call SD.Info
{
  "Name": "SC16G",
  "Type": "SDHC/SDXC",
  "Speed": "default speed",
  "Size": 15193,
  "SizeUnit": "MB",
  "CSD": {
    "ver": 1,
    "sector_size": 512,
    "capacity": 31116288,
    "read_bl_len": 9
  },
  "SCR": {
    "sd_spec": 2,
    "bus_width": 5
  }
}
```

- `SD.Size` - returns the size of the SD in bytes.
```
mos --port <serial/ws/mqtt> call SD.Size
{
  "sd_size": 15931539456
}
```

- `SD.Used` - returns the used number of bytes
```
mos --port <serial/ws/mqtt> call SD.Used
{
  "sd_used": 591
}
```

- `SD.Free` - returns the free number of bytes
```
mos --port <serial/ws/mqtt> call SD.Free
{
  "sd_free": 15931538865
}
```

If [RPC Service - Filesystem](https://github.com/mongoose-os-libs/rpc-service-fs) is included in the build, most of its functions are available, too.

