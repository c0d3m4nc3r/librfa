# librfa

**librfa** is a lightweight open-source C library (with C++ compatibility) that provides an API for working with **RFA archives** used in *Battlefield 1942* and *Battlefield Vietnam*.  

Currently, the library supports:
- Opening and closing RFA archives
- Retrieving the number of files in an archive
- Accessing file entries by name or index
- Checking if a file exists
- Extracting files by name or index into memory

## API Overview
```c
bool RFA_Init(void);
void RFA_Shutdown(void);

RFA_Archive* RFA_Open(const char* path);
void RFA_Close(RFA_Archive* archive);

size_t RFA_GetFileCount(RFA_Archive* archive);

RFA_FileEntry* RFA_GetEntryByName(RFA_Archive* archive, const char* name);
RFA_FileEntry* RFA_GetEntryByIndex(RFA_Archive* archive, size_t index);

bool RFA_FileExists(RFA_Archive* archive, const char* name);

int RFA_ExtractFile(RFA_Archive* archive, const char* name, void** data, size_t* size);
int RFA_ExtractFileByIndex(RFA_Archive* archive, size_t index, void** data, size_t* size);
```

## Planned Features

Future versions will add support for archive creation and modification:

RFA_Create — create a new archive

RFA_Save — save an archive to disk

RFA_AddFile — add files to an archive

RFA_RemoveFile — remove files from an archive

## License

GPLv3 — librfa is distributed under the GNU General Public License v3. You are free to use, modify, and redistribute it under the terms of this license.
