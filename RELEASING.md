# Releasing the dataset

In case of upstream changes in glottography-data:
```shell
cldfbench download cldfbench_queixalos2000linguas.py
```

```shell
cldfbench makecldf cldfbench_queixalos2000linguas.py --glottolog-version v5.1
```

```shell
cldf validate cldf
```

```shell
cldfbench cldfreadme cldfbench_queixalos2000linguas.py
```

```shell
cldfbench zenodo cldfbench_queixalos2000linguas.py
```

```shell
cldfbench readme cldfbench_queixalos2000linguas.py
```
