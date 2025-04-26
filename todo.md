# Listing (Today)

## Wwise Teller

### Features

- Helldivers 2 Integration

### Performance

- Disable rendering / lower max frame rate when it's idle.

### Releasing

- Create a test build on both Linux and Windows

## natPass

### Design

- Rework how GET route should be written 
    - Make use of URL parameter instead of body

### House Keeping

- Create a new branch to remove unnecessary files

### Performance 

- Ring buffer and timeout flushing to batch database write
- Initial phase of benchmark
    - Memory usage (test on local)
    - Throughput (test on remote)
- Load balancing algorithms for badge printer servers
    - It is possible that a host can connect multiple printers if it has 
    multiple USB ports

### Deployment

- Docker build spec and docker compose spec for the new setup.
- Security between natPass, rabbitMQ, and each individual badge printers
