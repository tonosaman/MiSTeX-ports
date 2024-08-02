# MiSTeX KV260 porting Memory spec research


- [clash-compilerのCI/CD用Dockerfile](https://github.com/clash-lang/clash-compiler/blob/v1.8.2/.ci/docker/Dockerfile)を元に Devcontainer を構築してVivado に入力する System Verylog ソースコードを出力したい

- [clash-protocols](https://github.com/clash-lang/clash-protocols) を用いた各モジュール間の通信を整理したい


## [MiSTer SDRAM XS-DS v3.0 128MB Module](https://misteraddons.com/products/sdram)

~~$60.00~~ &rarr; $40.00 (2024 July Sale)

## [AS4C32M16SB-7TCN](https://www.alliancememory.com/wp-content/uploads/pdf/dram/512M%20SDRAM_%20B%20die_AS4C32M16SB-7TCN-7TIN-6TIN_Rev%201.0%20June%202016.pdf)

| Part Number | Frequency | Package | Temperature | Temp Range |
|-------------|-----------|---------|-------------|------------|
| AS4C32M16SB-7TCN | 143MHz | 54 Pin TSOP II | Commercial | 0°C to 70°C |

## [DIMM](https://atmarkit.itmedia.co.jp/icd/root/27/24175627.html)

| モジュール | チップ | 種別 | バス帯域 | 転送速度 | データ幅 |
|-----------|-------|-----|-----|--------|---------|
| PC2700 | DDR-333 | DDR SDRAM | 2,666 Mbytes/s | 166MHz × 2倍 | 64bit |
| PC4-25600 | DDR4-3200 | DDR4 SDRAM | 25,600 Mbytes/s | 1,600MHz x 2倍 | 64bit |
| PC4-19200 | DDR4-2400 | DDR4 SDRAM | 19,200 Mbytes/s | 1,200MHz x 2倍 | 64bit |

> Function Overview and Block Diagram > Kria K26 SOM Data Sheet
>
> The K26 SOM leverages the XCK26-SFVC784-2LV-C/I, a cunstom-built Zynq UltraScale+ MPSoC that runs optimally (and exclusively) on the SOM. It provides an embedded processing system (PS) with tightly integrated programmable logic and a rich set of configurable I/O capabilities. The SOM hardware features include:
>
> - Zynq UltraScale+ MPSoC (XCK26 in commercial (C) grade or industrial (I) grade)
> - **4 GB 64-bit wide, 2400 Mb/s memory**

[AR# 73177: Zynq UltraScale+ MPSoC - 最大レートが 2400 Mb/s の場合、3200 Mb/s のスピード グレードの DDR4 デバイスを Zynq MPSoC DDR4 コントローラーで使用する方法](https://support.xilinx.com/s/article/73177)

- Micron x16 DDR4 3200 Mb/s `MT40A512M16LY-062E`

## [KV260(Zynq UltraScale+ MPSoC)のバス帯域を調べてみる](https://ryuz.hatenablog.com/entry/2024/07/15/102133)

| |	width | R/W | MHz | ports | MB/s |
|---|----|----|----|----|----|
| APU |	128 |	2 |	533 |	1 |	17,056 |
| RPU |	64 |	2 |	500 |	2 |	16,000 |
| GPU |	128 |	2 |	533 |	1 |	17,056 |
| PL(S_AXI_ACP) |	128 |	2 |	333 |	1 |	10,656 |
| PL(S_AXI_ACE) |	128 |	2 |	333 |	1 |	10,656 |
| PL(S_AXI_HPC_FPD) |	128 |	2 |	333 |	2 |	21,312 |
| PL(S_AXI_HP_FPD) |	128 |	2 |	333 |	4 |	42,624 |
| PL(S_AXI_LPD) |	128 |	2 |	333 |	1 |	10,656 |
| 合計 |	|	|	|	|	146,016 |
