Welcome to the petagres wiki!

## What is Petagres?
Petagres is an advanced relational database management system
that supports an extended subset of the SQL standard, including
transactions, foreign keys, subqueries, triggers, user-defined types
and functions.  This distribution also contains C language bindings.

## Major Features
1. Provide better control over bloat.  petagres will prevent bloat by allowing in-place updates in common cases and by reusing space as soon as a transaction that has performed a delete or non-in-place-update has committed. In short, with this new storage, whenever possible, we’ll avoid creating bloat in the first place.
2. Reduce write amplification both by avoiding rewrites of heap pages and by making it possible to do an update that touches indexed columns without updating every index.
3. Reduce the tuple size by shrinking the tuple header.
4. Delete marking in indexes: This will allow inplace updates even when index columns are updated and additionally with this we can avoid the need for a dedicated vacuum process to perform retail deletes.
5. Statement level rollback, a transaction mechanism compatible to oracle and mysql.
6. No vacuum.
7. No freeze, No transaction id wraparound.

## Open Issues
1. More testing is needed for recovery and rollbacks. We will not be surprised if you encounter some issues in that area.
2. Delete marking in indexes include: hash, gist, gin, brin

## Roadmap
Read the [Roadmap](https://github.com/linn0/petagres/wiki/Petagres-Roadmaps).

## License
The Petagres is distributed under the GPL license, version 3. 
The Petagres client libraries for C, Java and ODBC are distributed 
under the LGPL license, version 3 or later.
