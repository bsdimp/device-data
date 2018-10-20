# CAM drivers in FreeBSD over time

Status is my extremely preliminary determination about keep / toss on
all these drivers based on recent use.  Rough retirement criteria:
fewer than 5 reported users on FreeBSD 10 or newer, with a few
exceptions for hardware that is known to work or used to be super
popular or both and comes close to the threshold. This is about 0.5%
of the machines reported. Also, drivers committed in the last 5 years
are also retained. Some binary-only drivers that failed to get good
uptake have been placed on the retire list due to no post-commit
vendor involvement.

Note: FreeBSD 13 data not yet included (5 data points). That will be
fixed shortly. Data is as of 21:30:00 UTC 2018-10-20.

Status: *early discussion DRAFT*

| Driver | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| aac | 6 | 9 | 1 | 1 | 0 | 3 | 0 | 0 | 1 | maybe retain if more users show up |
| aacraid | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | retain (still modern and vendor supported) |
| adv | 0 | 3 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| adw | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| aha | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| ahc | 31 | 21 | 6 | 0 | 0 | 0 | 0 | 1 | 2 | likely remains, though mpt works much better |
| ahci | 0 | 0 | 0 | 0 | 5 | 32 | 88 | 381 | 109 | remains |
| ahd | 1 | 3 | 0 | 0 | 0 | 0 | 0 | 3 | 0 | retire (driver has known issues, should update to a MPT card) |
| aic | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| amr | 4 | 3 | 1 | 0 | 0 | 0 | 0 | 1 | 0 | retire unless more users show up |
| ata | 127 | 208 | 68 | 43 | 42 | 22 | 71 | 116 | 21 | remains (ppopular in VM setups lately) |
| bt | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| ciss | 3 | 5 | 2 | 4 | 0 | 3 | 3 | 8 | 1 | remains |
| dpt | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| esp | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| fsl | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (powerpc) |
| hpt27xx | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire (shovel ware by vendor with binary blobs only) |
| hptiop | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire (shovel ware by vendor with binary blobs only) |
| hptmv | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire (shovel ware by vendor with binary blobs only) |
| hptnr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire (shovel ware by vendor with binary blobs only) |
| hptrr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | retire (shovel ware by vendor with binary blobs only) |
| ida | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| iir | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | retire |
| ips | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| isci | 0 | 0 | 0 | 0 | 0 | 2 | 9 | 11 | 2 | remains |
| isp | 2 | 2 | 0 | 0 | 3 | 1 | 0 | 2 | 3 | remains |
| mlx | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| mly | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| mpr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 9 | 3 | remains |
| mps | 0 | 0 | 0 | 0 | 1 | 2 | 9 | 28 | 8 | remains |
| mpt | 3 | 2 | 4 | 3 | 2 | 3 | 18 | 14 | 2 | remains |
| mrsas | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | remains (more known usage than this data indicates) |
| mvs | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (2015) as used by many marvel SoC arrangements |
| ncr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| ncv | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| nsp | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| pms | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | likely to be retired (relevance has passed) |
| sbp | 3 | 43 | 14 | 3 | 1 | 3 | 1 | 2 | 5 | remains |
| siis | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 4 | 0 | likely remains (older card relevant in the mid 00's, but super popular and apparently still in use) |
| smartpqi | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (2017 successor to ciss, has known users) |
| stg | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| storvsc | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 | remains (has lots of known users) |
| sym | 5 | 14 | 3 | 0 | 1 | 0 | 1 | 3 | 0 | remains (should transition to mpt card, but things work well enough to retain) |
| trm | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| twa | 0 | 0 | 3 | 2 | 0 | 0 | 0 | 4 | 0 | remains (popular late 90s, still in use) |
| twe | 2 | 3 | 2 | 1 | 0 | 0 | 0 | 1 | 0 | maybe remains (popular 90's, maybe still in use) |
| tws | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire (too old to be relevant) |
| umass | 5 | 15 | 6 | 2 | 7 | 17 | 30 | 86 | 39 | remains |
| virtio | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (parsing glitch underrepsents use) |
| Data Points | 143 | 226 | 75 | 53 | 57 | 55 | 177 | 530 | 186 | total |

Note: The NYCBUG data is very sparse prior to 10.x due to uneven submissions. Also, the 12.x data skews to developer favorites or the experimental due to the nature of -CURRENT. Data in general does not include large deployments.
