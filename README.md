# Database Design Assignment 02 — ER-to-Relational Mapping

Relational mapping of the provided ER diagrams (Chen notation) for two case studies:

- [`OnlineRetailStore/schema.sql`](OnlineRetailStore/schema.sql) — Online Retail Store Management System
- [`HotelReservation/schema.sql`](HotelReservation/schema.sql) — Hotel Reservation Management System

[`ER-diagrams.pdf`](ER-diagrams.pdf) renders the resulting relational schema (the tables and
keys produced by the mapping below) as an ER diagram, one system per page.

## Mapping rules applied

- Each entity → a table; the underlined attribute becomes the primary key.
- 1:1 relationship → foreign key on either side (e.g. `Hotel.ManagerStaffId`).
- 1:N relationship → foreign key on the "many" side, referencing the "one" side's PK.
- M:N relationship → a new junction table with a composite PK made of both sides' FKs.
- Multivalued attribute → a new table with a composite PK of (owner FK, attribute value),
  e.g. `Room.Amenity` and `Guest.ContactDetails`.
