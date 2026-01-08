# Reddit Data Pipeline Engineering | AWS End-to-End Data Engineering

## Overview
This project implements a comprehensive data pipeline to extract, transform, and load Reddit data into Amazon Redshift. It leverages Apache Airflow, AWS Glue, and Amazon Athena for efficient data processing and analysis.

## Features
- Extraction of Reddit posts using the Reddit API.
- Transformation of data to a suitable format for analytics.
- Loading data into Amazon Redshift for querying and analysis.

## Technologies Used
- Apache Airflow
- AWS Glue
- Amazon Athena
- Amazon Redshift

## Project Structure
- **`pipelines/`**: Contains the main Reddit data pipeline code.
- **`etls/`**: Handles the extraction, transformation, and loading of Reddit data.
- **`utils/`**: Houses utility functions and constants.
- **`config/`**: Stores configuration files.

## Setup Instructions

### Prerequisites
- Python 3.9-3.12 (Python 3.13+ not yet supported by Apache Airflow)
- Poetry (for dependency management)

### Installation

1. **Install Poetry** (if not already installed):
   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

2. **Install project dependencies**:
   ```bash
   poetry install
   ```
   This will create a virtual environment and install all required packages with secure, up-to-date versions.

3. **Activate the virtual environment**:
   ```bash
   poetry shell
   ```

4. Set up your AWS credentials in the AWS CLI or environment variables.

5. Configure the project settings in `config/config.conf`.

6. Run the Reddit data pipeline using the provided DAG file:
   ```bash
   airflow trigger_dag etl_reddit_pipeline
   ```

### Dependency Management

This project uses Poetry for dependency management, which provides:
- Automatic dependency resolution
- Reproducible builds via `poetry.lock`
- Easy security updates: `poetry update`
- Separate development dependencies

#### Adding New Dependencies
```bash
# Add a runtime dependency
poetry add package-name

# Add a development dependency
poetry add --group dev package-name
```

#### Updating Dependencies
```bash
# Update all packages
poetry update

# Update specific package
poetry update package-name
```

## Usage
- Customize the DAG (`reddit_dag.py`) to suit your specific Reddit data extraction requirements.
- Adjust the AWS and database configurations in `config/config.conf` accordingly.
- Run the pipeline on a scheduled basis or manually trigger it using Apache Airflow.

## Contributing
1. Fork the repository.
2. Create a new branch: `git checkout -b feature/new-feature`.
3. Make your changes and commit: `git commit -m "Add new feature"`.
4. Push to the branch: `git push origin feature/new-feature`.
5. Open a pull request.
