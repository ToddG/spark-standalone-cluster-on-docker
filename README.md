# Apache Spark Standalone Cluster on Docker
> Build your own Apache Spark Standalone cluster with a JupyterLab interface on Docker :zap:

This project gives you an out-of-the-box **Apache Spark** cluster with a **JupyterLab** interface and a simulated **Apache Hadoop Distributed File System**, all built on top of **Docker**. Learn Apache Spark through its Python API, **PySpark**, by running the [Jupyter notebooks](build/workspace/pyspark.ipynb) with examples on how to read, process and write data.

<p align="center"><img src="docs/image/cluster-architecture.png"></p>

![jupyterlab-latest-version](https://img.shields.io/docker/v/andreper/jupyterlab/2.1.4-spark-3.0.0?color=green&label=jupyterlab-latest)
![spark-latest-version](https://img.shields.io/docker/v/andreper/spark-master/3.0.0?color=yellowgreen&label=spark-latest)
![repository-license](https://img.shields.io/github/license/andre-marcos-perez/spark-cluster-on-docker?color=yellow)

## Contents

- [Quick Start](#quick-start)
- [Tech Stack Version](#tech-stack-version)
- [Contributing](#contributing)
- [Contributors](#contributors)
- [Links](#links)

## <a name="quick-start"></a>Quick Start

### Cluster overview

| Application                | URL                                      | Description                                                |
| -------------------------- | ---------------------------------------- | ---------------------------------------------------------- |
| **JupyterLab**             | [localhost:8888](http://localhost:8888/) | Cluster interface with PySpark built-in notebook           |
| **Apache Spark Master**    | [localhost:8080](http://localhost:8080/) | Spark Master node                                          |
| **Apache Spark Worker I**  | [localhost:8081](http://localhost:8081/) | Spark Worker node with 1 core and 512m of memory (default) |
| **Apache Spark Worker II** | [localhost:8082](http://localhost:8082/) | Spark Worker node with 1 core and 512m of memory (default) |

### Build from DockerHub

1. Install [Docker and Docker Compose](https://docs.docker.com/get-docker/), check **infra** [supported versions](#tech-stack-version);
2. Download the source code or clone the repository;
3. Edit the [docker compose](docker-compose.yml) file with your favorite tech stack version, check **apps** [supported versions](#tech-stack-version);
4. Build the cluster;

```bash
docker-compose up
```

5. Run Apache Spark code using the provided [Jupyter notebook](build/workspace/pyspark.ipynb) with PySpark examples.

### Build from your local machine

> **Note**: Local build is currently only supported on Linux OS distributions.

1. Install [Docker and Docker Compose](https://docs.docker.com/get-docker/), check **infra** [supported versions](#tech-stack-version);
2. Download the source code or clone the repository;
3. Move to the build directory;

```bash
cd build
```

4. Edit the [build.yml](build/build.yml) file with your favorite tech stack version;
5. Match those version on the [docker compose](build/docker-compose.yml) file;
6. Make the build script executable;

```bash
chmod +x build.sh
```

7. Build the images;

```bash
./build.sh
```

8. Build the cluster;

```bash
docker-compose up
```

9. Run Apache Spark code using the provided [Jupyter notebook](build/workspace/pyspark.ipynb) with PySpark examples.

## <a name="tech-stack-version"></a>Tech Stack Version

- Infrastructure

| App                | Version            |
| ------------------ | ------------------ |
| **Docker**         | 1.13.0+            |
| **Docker Compose** | 3.0+               |

- Applications

| App                | Version            | Latest             |
| ------------------ | ------------------ | ------------------ |
| **Apache Spark**   | 3.0.0              | 3.0.0              |
| **Apache Hadoop**  | 2.7                | 2.7                |
| **JupyterLab**     | 2.1.4              | 2.1.4              |

- Tech

| App                | Version            |
| ------------------ | ------------------ |
| **Python**         | 3.7                |
| **Scala**          | 2.12               |

## <a name="contributing"></a>Contributing

We'd love some help. To contribute, follow the steps bellow:

1. Fork the project;
2. Create your feature branch, we use [gitflow](https://github.com/nvie/gitflow);
3. Do your magic :rainbow:;
4. Commit your changes;
5. Push to your feature branch;
6. Create a [new pull request](https://github.com/andre-marcos-perez/spark-cluster-on-docker/pulls).

Some ideas:

- Microsoft Windows build script;
- Spark submit support;
- JupyterLab Scala kernel;
- Jupyter notebook with Apache Spark Scala API examples;
- JupyterLab R kernel;
- Jupyter notebook with Apache Spark R API examples;
- Test coverage.

## <a name="contributors"></a>Contributors

 - **André Perez** - [dekoperez](https://twitter.com/dekoperez) - andre.marcos.perez@gmail.com

## <a name="links"></a>Links

 - **DockerHub Repo**: [JupyterLab image repository](https://hub.docker.com/r/andreper/jupyterlab);
 - **DockerHub Repo**: [Spark master image repository](https://hub.docker.com/r/andreper/spark-master);
 - **DockerHub Repo**: [Spark worker image repository](https://hub.docker.com/r/andreper/spark-worker).
