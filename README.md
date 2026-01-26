# Performance Testing Framework

A comprehensive, automated framework for performance testing and benchmarking distributed systems for [Debezium](https://debezium.io/) Change Data Capture deployments.

## Overview

This repository provides end-to-end infrastructure and tooling for conducting reliable, repeatable performance tests. It combines infrastructure-as-code, containerized services, automated load generation, and real-time monitoring to evaluate system behavior under various load conditions.

## Project Structure

```
├── debezium_server/                # Folder dedicated to Debezium Server
│   ├── infrastructure_automation/
│   ├── observed_machine/
│   └── observer_machine/
├── container_images/               # Custom Docker images used in this framework
│   ├── performance_mysql/
│   └── ycsb_jdbc/
├── _images/                        # Images used across this repository
├── _excalidraw/                    # Source files for diagrams
└── _results/                       # Results obtained from executing this repo
```

## Key Features

- **Automated Infrastructure**: Terraform and Ansible scripts for one-command AWS deployment
- **Distributed Architecture**: Separate observer and observed machines to prevent measurement interference
- **Containerized Services**: Docker-based deployments ensure consistency and portability
- **Real-time Monitoring**: Prometheus + Grafana stack with pre-configured dashboards
- **Load Generation**: YCSB (Yahoo! Cloud Serving Benchmark) for realistic database workloads
- **Reproducibility**: Versioned configurations and container images for consistent results

## Workload Configuration

Workloads use YCSB configuration files with customizable parameters:

- Read/write ratios
- Record counts and data volume
- Operation distribution (INSERT, UPDATE, READ)

For workload configuration details, see the [YCSB Wiki](https://github.com/brianfrankcooper/YCSB/wiki/Running-a-Workload).

## Results and Analysis

Test results are stored in the `_results/` directory. There, you can find a set of chart images along with the raw results of each execution.

## Documentation

- [Debezium Server Testing Framework](./debezium_server/README.md)
- [Infrastructure Automation](./debezium_server/infrastructure_automation/README.md)
- [Container Images](./container_images/README.md)
- [Observer Machine Setup](./debezium_server/observer_machine/README.md)
- [Observed Machine Setup](./debezium_server/observed_machine/README.md)

## License

This project is licensed under the terms specified in [LICENSE.txt](./LICENSE.txt).

## Contributing

Contributions are welcome. Please ensure:

- Infrastructure changes are tested with Terraform
- Container images follow the shared Makefile conventions
- Documentation is updated for new features
- Test results are reproducible

## Support

For issues, questions, or contributions, please open an issue in the repository.
