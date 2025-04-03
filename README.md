# MySQL Docker images

[![](https://img.shields.io/badge/github-bypanel%2Fdocker--mysql-red.svg)](https://github.com/bypanel/docker-mysql "github.com/bypanel/docker-mysql")

**Available Architectures:**  `amd64`, `arm64`

[![](https://img.shields.io/docker/pulls/bypanel/mysql.svg)](https://hub.docker.com/r/bypanel/mysql)

The purpose of this project is to streamline and re-tag the official Docker images for
[MySQL](https://hub.docker.com/_/mysql), [MariaDB](https://hub.docker.com/_/mariadb) and
[Percona](https://hub.docker.com/_/percona) in order to use them for the
**[bypanel](https://github.com/linuxeye/bypanel)** project.

> ##### 🐱 GitHub: [bypanel/docker-mysql](https://github.com/bypanel/docker-mysql)

## 🐋 Available Docker tags

[![](https://img.shields.io/docker/pulls/bypanel/mysql.svg)](https://hub.docker.com/r/bypanel/mysql)

[`mysql-5.5`][tag_mysql-5.5]
[`mysql-5.6`][tag_mysql-5.6]
[`mysql-5.7`][tag_mysql-5.7]
[`mysql-8.0`][tag_mysql-8.0]
[`mysql-8.4`][tag_mysql-8.4]

[`mariadb-5.5`][tag_mariadb-5.5]
[`mariadb-10.0`][tag_mariadb-10.0]
[`mariadb-10.1`][tag_mariadb-10.1]
[`mariadb-10.2`][tag_mariadb-10.2]
[`mariadb-10.3`][tag_mariadb-10.3]
[`mariadb-10.4`][tag_mariadb-10.4]
[`mariadb-10.5`][tag_mariadb-10.5]
[`mariadb-10.6`][tag_mariadb-10.6]
[`mariadb-10.7`][tag_mariadb-10.7]
[`mariadb-10.8`][tag_mariadb-10.8]
[`mariadb-10.9`][tag_mariadb-10.9]
[`mariadb-10.10`][tag_mariadb-10.10]
[`mariadb-10.11`][tag_mariadb-10.11]
[`mariadb-11.4`][tag_mariadb-11.4]

[`percona-5.5`][tag_percona-5.5]
[`percona-5.6`][tag_percona-5.6]
[`percona-5.7`][tag_percona-5.7]
[`percona-8.0`][tag_percona-8.0]


[tag_mysql-5.5]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mysql-5.5
[tag_mysql-5.6]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mysql-5.6
[tag_mysql-5.7]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mysql-5.7
[tag_mysql-8.0]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mysql-8.0
[tag_mysql-8.4]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mysql-8.4

[tag_percona-5.5]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/percona-5.5
[tag_percona-5.6]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/percona-5.6
[tag_percona-5.7]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/percona-5.7
[tag_percona-8.0]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/percona-8.0

[tag_mariadb-5.5]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-5.5
[tag_mariadb-10.0]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.0
[tag_mariadb-10.1]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.1
[tag_mariadb-10.2]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.2
[tag_mariadb-10.3]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.3
[tag_mariadb-10.4]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.4
[tag_mariadb-10.5]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.5
[tag_mariadb-10.6]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.6
[tag_mariadb-10.7]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.7
[tag_mariadb-10.8]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.8
[tag_mariadb-10.9]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.9
[tag_mariadb-10.10]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.10
[tag_mariadb-10.11]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-10.11
[tag_mariadb-11.4]: https://github.com/bypanel/docker-mysql/blob/main/Dockerfiles/mariadb-11.4

```bash
docker pull bypanel/mysql:<docker-tag>
```


## ✰ Additional features

The provided images are purely based on their official counterparts, however they have also been
slightly customized/enhanced additions added:

* An additional \*.cnf config directory is provided: `/etc/mysql/docker-default.d/`. This is necessary as the default config directory already contains \*.cnf files and you might want to keep them and still be able to additionally provide custom files
* MySQL 8.0 and Percona 8.0 by default use a new authentication mechanism which is not (yet) understood by PHP's `mysqli` extension. For those two images, the old authentication mechanism **[`mysql_native_password`](https://dev.mysql.com/doc/refman/8.0/en/native-pluggable-authentication.html)**  has been re-enabled, so you can still use it with your current PHP code.


## ∑ Environment Variables

Same as official Docker images:

* [MySQL](https://hub.docker.com/_/mysql)
* [MariaDB](https://hub.docker.com/_/mariadb)
* [Percona](https://hub.docker.com/_/percona)


## 🖧 Exposed Ports

MySQL listening port `3306`


## 📂 Volumes

The mountpoints for configuration files have been streamlined for all images in this repository.

| Path                           | Description                            |
|--------------------------------|----------------------------------------|
| `/etc/mysql/conf.d`            | Default primary config mountpoint      |
| `/etc/mysql/docker-default.d/` | Additional secondary config mountpoint |


## 🛈 Retagging of official images

The below listed tables show how the official images have been retagged.

#### MySQL

* [DockerHub](https://hub.docker.com/_/mysql)
* [GitHub](https://github.com/docker-library/mysql)

| Original Image and Tag | New Image and Tag              | Available platforms |
|------------------------|--------------------------------|---------------------|
| `mysql:5.5`            | `bypanel/mysql:mysql-5.5`     | `amd64`             |
| `mysql:5.6`            | `bypanel/mysql:mysql-5.6`     | `amd64`             |
| `mysql:5.7`            | `bypanel/mysql:mysql-5.7`     | `amd64`             |
| `mysql:8.0`            | `bypanel/mysql:mysql-8.0`     | `amd64`, `arm64`    |
| `mysql:8.4`            | `bypanel/mysql:mysql-8.4`     | `amd64`, `arm64`    |

#### MariaDB

* [DockerHub](https://hub.docker.com/_/mariadb)
* [GitHub](https://github.com/docker-library/mariadb)

| Original Image and Tag | New Image and Tag              | Available platforms |
|------------------------|--------------------------------|---------------------|
| `mariadb:5.5`          | `bypanel/mysql:mariadb-5.5`   | `amd64`             |
| `mariadb:10.0`         | `bypanel/mysql:mariadb-10.0`  | `amd64`, `arm64`    |
| `mariadb:10.1`         | `bypanel/mysql:mariadb-10.1`  | `amd64`, `arm64`    |
| `mariadb:10.2`         | `bypanel/mysql:mariadb-10.2`  | `amd64`, `arm64`    |
| `mariadb:10.3`         | `bypanel/mysql:mariadb-10.3`  | `amd64`, `arm64`    |
| `mariadb:10.4`         | `bypanel/mysql:mariadb-10.4`  | `amd64`, `arm64`    |
| `mariadb:10.5`         | `bypanel/mysql:mariadb-10.5`  | `amd64`, `arm64`    |
| `mariadb:10.6`         | `bypanel/mysql:mariadb-10.6`  | `amd64`, `arm64`    |
| `mariadb:10.7`         | `bypanel/mysql:mariadb-10.7`  | `amd64`, `arm64`    |
| `mariadb:10.8`         | `bypanel/mysql:mariadb-10.8`  | `amd64`, `arm64`    |
| `mariadb:10.9`         | `bypanel/mysql:mariadb-10.9`  | `amd64`, `arm64`    |
| `mariadb:10.10`        | `bypanel/mysql:mariadb-10.10` | `amd64`, `arm64`    |
| `mariadb:10.11`        | `bypanel/mysql:mariadb-10.11` | `amd64`, `arm64`    |
| `mariadb:11.4`         | `bypanel/mysql:mariadb-11.4`  | `amd64`, `arm64`    |

#### Percona

* [DockerHub](https://hub.docker.com/_/percona)
* [GitHub](https://github.com/docker-library/percona)

| Original Image and Tag | New Image and Tag              | Available platforms |
|------------------------|--------------------------------|---------------------|
| `percona:5.5`          | `bypanel/mysql:percona-5.5`   | `amd64`             |
| `percona:5.6`          | `bypanel/mysql:percona-5.6`   | `amd64`             |
| `percona:5.7`          | `bypanel/mysql:percona-5.7`   | `amd64`             |
| `percona:8.0`          | `bypanel/mysql:percona-8.0`   | `amd64`             |


## 🖤 Sister Projects

Show some love for the following sister projects.

<table>
 <tr>
  <th>🐱 GitHub</th>
  <th>🐋 DockerHub</th>
 </tr>
 <tr>
  <td><a href="https://github.com/bypanel/bypanel"><code>bypanel</code></a></td>
  <td></td>
 </tr>
 <tr>
  <td><a href="https://github.com/bypanel/docker-php-fpm"><code>docker-php-fpm</code></a></td>
  <td><a href="https://hub.docker.com/r/bypanel/php-fpm"><code>bypanel/php-fpm</code></a></td>
 </tr>
 <tr>
  <td><a href="https://github.com/bypanel/docker-mysql"><code>docker-mysql</code></a></td>
  <td><a href="https://hub.docker.com/r/bypanel/mysql"><code>bypanel/mysql</code></a></td>
 </tr>
 <tr>
  <td>
   <a href="https://github.com/bypanel/docker-apache"><code>docker-apache</code></a><br/>
   <a href="https://github.com/bypanel/docker-nginx"><code>docker-nginx</code></a><br/>
   <a href="https://github.com/bypanel/docker-openresty"><code>docker-openresty</code></a>
  </td>
  <td>
   <a href="https://hub.docker.com/r/bypanel/apache"><code>bypanel/apache</code></a><br/>
   <a href="https://hub.docker.com/r/bypanel/nginx"><code>bypanel/nginx</code></a><br/>
   <a href="https://hub.docker.com/r/bypanel/openresty"><code>bypanel/openresty</code></a>
  </td>
 </tr>
</table>

## 🧘 Maintainer

**[@linuxeye](https://github.com/linuxeye)**

I try to keep up with literally **over 100 projects** besides a full-time job.
If my work is making your life easier, consider contributing. 🖤