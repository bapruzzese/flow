## Flow diagram: Administrator

```mermaid
flowchart LR
  Login["Admin login"]
  Desk["Admin desk"]
  Users["Search users"]
  Books["Add / delete book"]
  Authors["Add / delete author"]
  Recs["Add recommendation"]
  Return["Mark copy returned"]
  DB[("Database")]

  Login -->|"role = admin"| Desk
  Desk --> Users
  Desk --> Books
  Desk --> Authors
  Desk --> Recs
  Desk -->|"copy barcode"| Return

  Users -->|"search, delete member, change password"| DB
  Books -->|"title, isbn, author"| DB
  Authors -->|"author name"| DB
  Recs -->|"book_id, blurb"| DB
  Return -->|"loan closed, copy in, next hold ready"| DB
