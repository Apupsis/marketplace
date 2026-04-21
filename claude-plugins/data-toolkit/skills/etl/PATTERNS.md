# ETL Patterns

## Incremental Loading

- Track high-water marks (max timestamp, ID)
- Use change data capture when available
- Implement soft deletes for historical tracking
- Partition data by date for efficient updates

## Error Handling

- Retry transient failures with exponential backoff
- Dead letter queue for poison records
- Alert on error rate thresholds
- Log errors with context for debugging
- Implement circuit breakers for downstream failures

## Data Quality

- Schema validation at ingestion
- Completeness checks (null rates, required fields)
- Accuracy checks (range validation, checksums)
- Consistency checks (referential integrity)
- Timeliness monitoring (data freshness SLAs)

## Orchestration

- DAG-based workflow definitions
- Dependency management between tasks
- Backfill strategies for historical data
- Parallel execution where possible
- Resource allocation and queuing

## Monitoring

- Data volume metrics per pipeline stage
- Processing time and throughput
- Error rates and types
- Data quality metrics
- Pipeline success/failure rates
- SLA compliance tracking
