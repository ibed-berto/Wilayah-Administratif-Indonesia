# Data Provinsi, Kota/Kabupaten, Kecamatan, dan Kelurahan/Desa di Indonesia
Data ini diambil dari situs [Pemutakhiran MFD dan MBS
Badan Pusat Statistik (http://mfdonline.bps.go.id/)](http://mfdonline.bps.go.id/) pada **11 Januari 2018**.

# Administrative Subdivisions of Indonesia (Provinces, Regencies/Cities, Districts, Villages)
The data were taken from [Central Agency on Statistics (BPS) - MFD and MBS Update (http://mfdonline.bps.go.id/)](http://mfdonline.bps.go.id/) on **11th January 2018**.

The data were `curl`-ed from BPS site:

    curl http://mfdonline.bps.go.id/index.php?link=hasil_pencarian --data "pilihcari=desa&kata_kunci="
    
with `a`, `i`, `u`, `e` and `o` as the keywords.

## Statistics

```
+------+---------------------------+----------------+-----------+----------------+
| Kode | Provinsi                  | Kabupaten/Kota | Kecamatan | Desa/Kelurahan |
+------+---------------------------+----------------+-----------+----------------+
| 11   | ACEH                      |             23 |       289 |           6509 |
| 12   | SUMATERA UTARA            |             33 |       448 |           6102 |
| 13   | SUMATERA BARAT            |             19 |       179 |           1160 |
| 14   | RIAU                      |             12 |       169 |           1876 |
| 15   | JAMBI                     |             11 |       141 |           1562 |
| 16   | SUMATERA SELATAN          |             17 |       236 |           3263 |
| 17   | BENGKULU                  |             10 |       128 |           1515 |
| 18   | LAMPUNG                   |             15 |       228 |           2642 |
| 19   | KEPULAUAN BANGKA BELITUNG |              7 |        47 |            366 |
| 21   | KEPULAUAN RIAU            |              7 |        70 |            395 |
| 31   | DKI JAKARTA               |              6 |        44 |            254 |
| 32   | JAWA BARAT                |             27 |       627 |           5832 |
| 33   | JAWA TENGAH               |             35 |       573 |           8008 |
| 34   | DI YOGYAKARTA             |              5 |        78 |            414 |
| 35   | JAWA TIMUR                |             38 |       666 |           7856 |
| 36   | BANTEN                    |              8 |       155 |           1501 |
| 51   | BALI                      |              9 |        57 |            653 |
| 52   | NUSA TENGGARA BARAT       |             10 |       116 |           1062 |
| 53   | NUSA TENGGARA TIMUR       |             22 |       307 |           3202 |
| 61   | KALIMANTAN BARAT          |             14 |       174 |           2073 |
| 62   | KALIMANTAN TENGAH         |             14 |       136 |           1537 |
| 63   | KALIMANTAN SELATAN        |             13 |       152 |           1971 |
| 64   | KALIMANTAN TIMUR          |             10 |       103 |           1002 |
| 65   | KALIMANTAN UTARA          |              5 |        53 |            466 |
| 71   | SULAWESI UTARA            |             15 |       171 |           1790 |
| 72   | SULAWESI TENGAH           |             13 |       175 |           1953 |
| 73   | SULAWESI SELATAN          |             24 |       307 |           2975 |
| 74   | SULAWESI TENGGARA         |             17 |       222 |           2301 |
| 75   | GORONTALO                 |              6 |        77 |            722 |
| 76   | SULAWESI BARAT            |              6 |        69 |            639 |
| 81   | MALUKU                    |             11 |       118 |           1180 |
| 82   | MALUKU UTARA              |             10 |       116 |           1155 |
| 91   | PAPUA BARAT               |              7 |       111 |           1014 |
+------+---------------------------+----------------+-----------+----------------+
```

*Note*:

There is some entries that not in ASCII format.

```
72  SULAWESI TENGAH 09  KABUPATEN TOJO UNA-UNA  070 TOGEAN  016 TITIRIí POPOLION
94  PAPUA 33  KABUPATEN PUNCAK  042 MAGEÁBUME
```

There is duplicate village id.

```
91  PAPUA BARAT 07  KABUPATEN SORONG  182 WEMAK 005 KAMLIN
91  PAPUA BARAT 07  KABUPATEN SORONG  182 WEMAK 005 KWARI
```

## Generate new data

In order to generate new data:

    cd scripts
    pip install -r requirements.txt
    ./run.sh

We use `mysql` as default database hostname and `root` as default database username, but if you have different database setup on your local machine, you can simply run it with argument:

    ./run -h [my-db-host] -u [my-db-username]

You can also run `docker-compose` (more preferred):

    docker-compose build
    docker-compose up

## License

* The scripts are license under: [MIT](license.md).
* The data (CSV and SQL) are under: [ODBL v1.0](odbl-10.md).
* The source data is attributed to **Badan Pusat Statistik (BPS) Indonesia**.

## Contributing

1. Fork it (https://github.com/edwardsamuel/Wilayah-Administratif-Indonesia/fork).
2. Create your feature branch (`git checkout -b my-new-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin my-new-feature`).
5. Create a new Pull Request.
