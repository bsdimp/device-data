# CAM drivers in FreeBSD over time

Status is my extremely preliminary determination about keep / toss on
all these drivers based on recent use.  Rough retirement criteria:
fewer than 5 reported users on FreeBSD 10 or newer, with a few
exceptions for hardware that is known to work or used to be super
popular or both and comes close to the threshold. This is about 0.5%
of the machines reported. Also, drivers committed in the last 5 years
are also retained.

Status: *early discussion DRAFT*

| Driver | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| aac | 6 | 9 | 1 | 1 | 0 | 3 | 0 | 0 | 1 | likely retire |
| aacraid | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | likely retire |
| adv | 0 | 3 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| adw | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| aha | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| ahc | 31 | 21 | 6 | 0 | 0 | 0 | 0 | 1 | 2 | likely remains |
| ahci | 0 | 0 | 0 | 0 | 5 | 32 | 88 | 369 | 105 | remains |
| ahd | 1 | 3 | 0 | 0 | 0 | 0 | 0 | 3 | 0 | retire |
| aic | 1 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| amr | 4 | 3 | 1 | 0 | 0 | 0 | 0 | 1 | 0 | retire |
| ata | 127 | 208 | 68 | 43 | 42 | 22 | 71 | 110 | 20 | remains |
| bt | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| ciss | 3 | 5 | 2 | 4 | 0 | 3 | 3 | 7 | 1 | remains |
| dpt | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| esp | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| fsl | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains |
| hpt27xx | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | maybe remains (2011) |
| hptiop | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (2013) |
| hptmv | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | likely retire (2005) |
| hptnr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (2013) |
| hptrr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | remains (2012) |
| ida | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| iir | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | retire |
| ips | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| iscsi | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (parsing glitch?) |
| isp | 2 | 2 | 0 | 0 | 3 | 1 | 0 | 2 | 3 | remains |
| mlx | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| mly | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| mpr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 9 | 3 | remains |
| mps | 0 | 0 | 0 | 0 | 1 | 2 | 9 | 24 | 8 | remains |
| mpt | 3 | 2 | 4 | 3 | 2 | 3 | 18 | 13 | 2 | remains |
| mrsas | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | likely remains |
| mvs | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains |
| ncr | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| ncv | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| nsp | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| pms | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (2015) |
| sbp | 3 | 43 | 14 | 3 | 1 | 3 | 1 | 2 | 4 | remains |
| siis | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 4 | 0 | remains |
| smartpqi | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (2017) |
| stg | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| storvsc | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 | remains |
| sym | 5 | 14 | 3 | 0 | 1 | 0 | 1 | 3 | 0 | remains |
| trm | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | retire |
| twa | 0 | 0 | 3 | 2 | 0 | 0 | 0 | 4 | 0 | remains |
| twe | 2 | 3 | 2 | 1 | 0 | 0 | 0 | 1 | 0 | remains |
| tws | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | maybe retire |
| umass | 5 | 15 | 6 | 2 | 7 | 17 | 30 | 83 | 37 | remains |
| virtio | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | remains (parsing glitch?) |
| Data Points | 143 | 226 | 75 | 53 | 57 | 55 | 177 | 513 | 180 | total |
