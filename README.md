# pg_regress_input
input data for pg_regress test

## build `pg_regress`

ref: https://www.postgresql.org/docs/current/install-make.html

```
cd postgres/
./configure
make
// after success make, pg_regress will locate at src/test/regress/pg_regress

// run pg_regress with temp started pg instance
make check

```

## run `pg_regress` on local `clapdb`

```
src/test/regress/pg_regress --use-existing --dbname=local --host=localhost --port=8888 --schedule=parallel_schedule --user=admin.stdb --max-connections=1 --inputdir=.
```

## input data from postgress

`parallel_schedule`, `sql/`, `data/`, `expected/` are copied from `postgres/src/test/regress/` .

```
$ ll postgres/src/test/regress
total 180K
drwxr-xr-x 2 longqimin longqimin 4.0K Feb 26 18:07 data/
drwxr-xr-x 2 longqimin longqimin 8.0K Feb 26 18:07 expected/
-rw-r--r-- 1 longqimin longqimin 4.4K Feb 26 18:07 GNUmakefile
-rw-r--r-- 1 longqimin longqimin  778 Feb 26 18:07 Makefile
-rw-r--r-- 1 longqimin longqimin 2.1K Feb 26 18:07 meson.build
-rw-r--r-- 1 longqimin longqimin 5.3K Feb 26 18:07 parallel_schedule
-rw-r--r-- 1 longqimin longqimin  68K Feb 26 18:07 pg_regress.c
-rw-r--r-- 1 longqimin longqimin 1.8K Feb 26 18:07 pg_regress.h
-rw-r--r-- 1 longqimin longqimin 3.1K Feb 26 18:07 pg_regress_main.c
-rw-r--r-- 1 longqimin longqimin  159 Feb 26 18:07 README
-rw-r--r-- 1 longqimin longqimin  33K Feb 26 18:07 regress.c
-rwxr-xr-x 1 longqimin longqimin 4.4K Feb 26 18:07 regressplans.sh*
-rw-r--r-- 1 longqimin longqimin  107 Feb 26 18:07 resultmap
drwxr-xr-x 2 longqimin longqimin 8.0K Feb 26 18:07 sql/
```

since `clapdb` is still in-progress and not full compatible with `pg`, we removed some tests to make clapdb pass.
