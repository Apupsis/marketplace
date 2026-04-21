---
description: Build a data ingestion pipeline from source to destination with validation and error handling.
---

# Ingest Command

Build a complete data ingestion pipeline with extraction, validation, transformation, and loading stages.

## Scope

This command creates production-ready ingestion code that:
- Connects to data sources (databases, APIs, files)
- Validates data quality and schema compliance
- Transforms data to target schema
- Loads data into destination with error handling
- Logs metrics and errors for monitoring

## Execution Flow

1. Analyze source schema and data characteristics
2. Design target schema and transformation logic
3. Implement extraction with retry and timeout handling
4. Add validation rules for data quality
5. Build transformation pipeline with error handling
6. Implement loading with transaction management
7. Add comprehensive logging and metrics
8. Create tests with realistic data samples

## Constraints

- Use existing data-toolkit skills for implementation
- Follow idempotent design patterns
- Include data quality checks at each stage
- Add monitoring hooks for observability
- Document data lineage and assumptions
- Handle partial failures gracefully
- Provide rollback capabilities
- Test with production-scale data samples
