# SQL Best Practices

## Query Optimization

- Analyze execution plans before optimizing
- Filter early — WHERE clauses reduce dataset size
- Use appropriate join types (INNER, LEFT, etc.)
- Avoid SELECT * — specify needed columns
- Use LIMIT/TOP when testing or appropriate
- Consider materialized views for expensive queries

## Indexing Strategy

- Index columns used in WHERE, JOIN, ORDER BY
- Composite indexes for multi-column filters
- Include covering indexes for read-heavy queries
- Monitor index usage and remove unused indexes
- Balance index count with write performance

## Data Modeling

- Primary keys on all tables
- Foreign keys for referential integrity
- NOT NULL constraints where appropriate
- Check constraints for data validation
- Appropriate data types minimize storage
- Normalized design for transactional systems
- Denormalized design for analytical queries

## Performance Patterns

- Batch operations over row-by-row processing
- Use transactions appropriately
- Avoid N+1 query problems
- Partition large tables by date or key
- Archive old data to maintain performance
- Monitor slow query logs
- Use connection pooling for applications
