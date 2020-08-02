# Kong (API Management) +  Konga (Admin API)

Deployment manual [Kong API Management Community](https://konghq.com/) y [Konga](https://pantsel.github.io/konga/) on containers with [Docker](https://www.docker.com/) y [Docker Compose](https://docs.docker.com/compose/).

#### Versiones:
- Kong v2.1.0
- Konga vlatest
- Docker v19.03.12
- Docker-compose v1.24.1
- Postgres v9.6
- MongoDB v4.1.5


## Run

    docker-compose up -d

- Open [Konga](http://localhost:1337/) with browser, login how admin (admin / adminadminadmin).
- Add Conexion Kong:
    + Name: Kong API
    + Conexion: http://kong:8001
- Load Snapshot file "snapshot_api_test.json".
- Consume API test  (Http Get) [http://localhost:8000/prueba/cd86bfdc-1413-4011-8d4b-f4668ce87dfd](http://localhost:8000/prueba/cd86bfdc-1413-4011-8d4b-f4668ce87dfd)
 
## Endpoints

### Kong

- Proxy: [http://localhost:8000](http://localhost:8000)
- Proxy w/ SSL: [https://localhost:8443](https://localhost:8443)
- Admin API: [http://localhost:8001](http://localhost:8001)

Kong uses PostgreSQL (9.6) with a persistent Docker volume for its credentials.

### Konga

- GUI: [http://localhost:1337](http://localhost:1337)

The following default users are configured in `konga/user_seed.js`:
- admin / adminadminadmin
- demo / demodemodemo

After logging in as admin, create a new connection with URL `http://kong:8001`.

Konga uses MongoDB (4.1.5) with a persistent Docker volume for its credentials.
