
Raw data GPT


#### How large is the header?
- Kijken naar Header Size (length = 4 dus 2 HEX)

```
- Header Size = 5C000000
- 5C000000 -> HEX MET LENGTH 4 = 5C
- 5C HEX = 92 DECIMAL 
```

#### How large is a single partition entry?
- Kijken naar Size of Single Partition Entry (length = 4 dus 2 HEX)

```
- Size of Single Partition Entry = 80000000
- 80000000 -> HEX MET LENGTH 4 = 80
- 80 HEX = 128 DECIMAL
```

#### How many partition entries are there?
- Kijken naar Partition Entry Count

```
- Partition Entry Count = 80000000
- 80000000 -> HEX MET LENGTH 4 = 80
- 80 HEX = 128 DECIMAL
```

#### How much space do all partition entries require?
- Single partition entry * Partition Entry Count

```
- 128 * 128
- UITKOMST IN DECIMAL
```

#### First usable LBA for partitions?
- Kijken naar First Usable LBA for Partitions

```
- First Usable LBA for Partitions = 2200000000000000
- 2200000000000000 MET LENGTH 8 = 0022
- 22 HEX = 34
```

#### Last usable LBA for partitions?
- Kijken naar Last Usable LBA for Partitions

```
- Last usable LBA for partitions = DE4F000000000000
- DE4F000000000000 MET LENGTH 8 = (0000)4FDE
- 4FDE HEX = 20446 DECIMAL
```

#### Number of blocks available for partitions

```
Last useable LBA - First Usable LBA
```

#### Space in bytes usable for partitions?
- Number of blocks available for partitions * size of block

```
20413 * 512 = 10451456
```

#### What is the address of the first block in the partition?
- First LBA * 512

```
2048 * 512 = 0100000
```

#### How large is the partition in bytes?
- (last LBA - first LBA + 1) * 512

```
(20446-2048 + 1) * 512 = 9420288
```

## BOOT SECTOR

#### Bytes occupied by reserved region
Bytes per cluster * sectors occupied by reserved region

```
512 * 8 = 4096
```

#### Bytes per FAT
Bytes per cluster * Sectors per FAT

```
512 * 72 = 36864
```

#### Size of root directory in bytes?
- (last LBA - first LBA + 1) * 512

```
(20446-2048 + 1) * 512 = 9420288
```

#### Size of root directory in bytes
- Aantal bytes (32 bytes) * 512

```
32 * 512 = 16384
```

#### Address of first FAT
- "The first FAT directly follows the reserved region."
```
er zijn 8 sectoren reserved
die zijn elk 0x0200 lang
en dan uw startadres is 0x0100000
8 x 0x0200 is 0x1000
0x0100000 + 0x1000 = 0x101000
```

#### Address of root directory
First FAT adres + (aantal FATs * BytesPerFAT)

```
101000 + (2 * 36864) HEX = 113000
```

#### Address of data region
rootDirectoryAddress + rootDirectorySize;

```
113000 + 16384 = 117000
```

# Deze zijn van extra oefening 1 maar zelfde principe voor allemaal

#### Cluster Chain (file4.dat)
First FAT address + First cluster * 2

```
100800 (HEX) + 6995 (36A6 IN HEX) * 2 =  0x0103EA6
```
&rarr; Op dat adres staat volgende getal in cluster chain (little endian omzetten)

#### File contents (file4.dat)
Start of region data + (laatste van cluster chain - 2) + cluster size

```
108000 (HEX) + (3439 - 2) (DEC) * 2048
```
&rarr; laatste 4 bytes nemen van file content

