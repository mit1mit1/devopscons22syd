# What's it for?

SQLAlchemy has two distinct components.

1. The Core - a SQL abstraction toolkit, basically letting you talk to your database more easily from python code;
2. The ORM - a mapper between object classes and the database, for when you want to think in terms of objects instead of DB schemas.

In addition, there is:

- Alembic - a DB migration tool to keep track of sequential alters done on a DB over different versions of a product.

See [real sql alchemy and alembic examples](../personalNotes/real-sql-alchemy-alembic.md) for more specific details.

# References

- https://www.sqlalchemy.org/philosophy.html
- https://www.sqlalchemy.org/features.html
- https://github.com/sqlalchemy/alembic
