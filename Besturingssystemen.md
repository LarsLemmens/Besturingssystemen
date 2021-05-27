
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
Bytes per cluster * Bytes per FAT

```
512 * 72 = 36864
```


