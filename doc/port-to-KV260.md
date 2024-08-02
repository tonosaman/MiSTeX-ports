# MiSTeX KV260 porting Memory spec research

## [MiSTer SDRAM XS-DS v3.0 128MB Module](https://misteraddons.com/products/sdram)

~~$60.00~~ &rarr; $40.00 (2024 July Sale)

## [AS4C32M16SB-7TCN](https://www.alliancememory.com/wp-content/uploads/pdf/dram/512M%20SDRAM_%20B%20die_AS4C32M16SB-7TCN-7TIN-6TIN_Rev%201.0%20June%202016.pdf)

| Part Number | Frequency | Package | Temperature | Temp Range |
|-------------|-----------|---------|-------------|------------|
| AS4C32M16SB-7TCN | 143MHz | 54 Pin TSOP II | Commercial | 0°C to 70°C |

## [DIMM](https://atmarkit.itmedia.co.jp/icd/root/27/24175627.html)

| モジュール | チップ | 種別 | 帯域 | クロック | データ幅 |
|-----------|-------|-----|-----|--------|---------|
| PC2700 | DDR-333 | DDR SDRAM | 2.66G bytes/s | 166MHz × 2倍 | 64bit |

## [KV260(Zynq UltraScale+ MPSoC)のバス帯域を調べてみる](https://ryuz.hatenablog.com/entry/2024/07/15/102133)

| |	width | R/W | MHz | ports | MB/s |
|---|----|----|----|----|----|
| APU |	128 |	2 |	533 |	1 |	17,056 |
| RPU |	64 |	2 |	500 |	2 |	16,000 |
| GPU |	128 |	2 |	533 |	1 |	17,056 |
| PL(S_AXI_ACP) |	128 |	2 |	333 |	1 |	10,656 |
| PL(S_AXI_ACE |	128 |	2 |	333 |	1 |	10,656 |
| PL(S_AXI_HPC_FPD) |	128 |	2 |	333 |	2 |	21,312 |
| PL(S_AXI_HP_FPD) |	128 |	2 |	333 |	4 |	42,624 |
| PL(S_AXI_LPD) |	128 |	2 |	333 |	1 |	10,656 |
| 合計 |	|	|	|	|	146,016 |

