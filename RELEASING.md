# Releasing the dataset

## Recreate the raw data from glottography-data

In case of upstream changes in glottography-data:
```shell
cldfbench download cldfbench_queixalos2000linguas.py
```

## Recreate the CLDF data

```shell
cldfbench makecldf cldfbench_queixalos2000linguas.py --glottolog-version v5.2
cldfbench cldfreadme cldfbench_queixalos2000linguas.py
cldfbench zenodo --communities glottography cldfbench_queixalos2000linguas.py
cldfbench readme cldfbench_queixalos2000linguas.py
```

## Validation

```shell
cldf validate cldf
```

```shell
cldfbench geojson.validate cldf
```

```shell
cldfbench geojson.glottolog_distance cldf --format pipe
```

```shell
cldfbench geojson.glottolog_distance cldf --format tsv | csvformat -t | csvgrep -c Distance -r"^0\.?" -i | csvsort -c Distance | csvcut -c ID,Distance | csvformat -E | termgraph
```

```
guar1292: ▇▇▇▇▇▇▇ 1.06 
guah1255: ▇▇▇▇▇▇▇ 1.10 
ware1255: ▇▇▇▇▇▇▇ 1.17 
kuyu1236: ▇▇▇▇▇▇▇▇ 1.22 
akaw1239: ▇▇▇▇▇▇▇▇ 1.28 
kaya1329: ▇▇▇▇▇▇▇▇▇ 1.34 
para1313: ▇▇▇▇▇▇▇▇▇ 1.35 
shar1245: ▇▇▇▇▇▇▇▇▇ 1.40 
paez1247: ▇▇▇▇▇▇▇▇▇ 1.41 
esee1248: ▇▇▇▇▇▇▇▇▇ 1.42 
yura1255: ▇▇▇▇▇▇▇▇▇ 1.45 
maku1278: ▇▇▇▇▇▇▇▇▇ 1.45 
niva1238: ▇▇▇▇▇▇▇▇▇▇ 1.52 
mand1448: ▇▇▇▇▇▇▇▇▇▇ 1.54 
zoee1240: ▇▇▇▇▇▇▇▇▇▇ 1.54 
curr1243: ▇▇▇▇▇▇▇▇▇▇ 1.62 
krey1238: ▇▇▇▇▇▇▇▇▇▇▇ 1.66 
cane1242: ▇▇▇▇▇▇▇▇▇▇▇ 1.76 
paca1246: ▇▇▇▇▇▇▇▇▇▇▇▇ 1.82 
paus1244: ▇▇▇▇▇▇▇▇▇▇▇▇ 1.82 
arua1261: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.15 
mati1255: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.23 
mori1273: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.39 
ayor1240: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.42 
apia1248: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.63 
saki1248: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.70 
wayo1238: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 3.35 
avac1239: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 3.38 
kari1309: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 3.66 
omag1248: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 3.94 
yine1238: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 4.36 
para1311: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 7.42 
```
