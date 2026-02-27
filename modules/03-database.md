# Database (Safe Migrations + Query Safety)

## Risk levels

- HIGH: dropping/renaming columns on large tables, adding NOT NULL without backfill, locking indexes
- MED: missing indexes on new FKs, heavy data migrations in a single step
- LOW: additive nullable columns, small tables, pure metadata changes

## Safe migration pattern (production)

1. Add new nullable column(s)
2. Backfill in batches (job/command) — never in a single migration for big tables
3. Add index/constraint after backfill
4. Switch code to new column(s)
5. Remove old column(s) in a later deploy

## Checklist

- [ ] down() is correct
- [ ] additive-first strategy used when data exists
- [ ] indexes added for new query paths / FKs
- [ ] no N+1 introduced (use eager loading)

## Commands

- php artisan migrate:status
- php artisan migrate --pretend (if available in your flow) / review SQL
- php artisan tinker (verify queries)
