# __Pgsql-Postal Installation on _`Ubuntu 18.04`___

## __Environmental Requirements__

## __1. Installing the Required Softwares__

```
sudo apt install -y curl autoconf automake libtool pkg-config
```

## __2. Installing _`libpostal`_ on _`Ubuntu 18.04`___

### __Download _`libpostal`___

```
git clone https://github.com/openvenues/libpostal
```

### __Build _`libpostal`___

```
cd libpostal
./bootstrap.sh
./configure --datadir=/home/ubuntu/libpostal/data
make -j4
```

### __Install _`libpostal`___

```
sudo make install
sudo ldconfig
```

## __3. Installing _`pgsql-postal`_ on _`Ubuntu 18.04`___

### __Download _`pgsql-postal`___

```
git clone https://github.com/pramsey/pgsql-postal
```

### __Build _`pgsql-postal`___

```
sudo make
sudo make install
```

### __Add _`postal`_ extension into postgresql__

```
sudo -s -u nominatim
psql

CREATE EXTENSION postal;
\q
```



