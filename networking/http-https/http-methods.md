

# HTTP Methods

## Why HTTP Methods Exist

A client may want to perform different actions on a resource.

Examples:

- Retrieve data
- Create data
- Update data
- Delete data

Question:

```text
How Does The Server Know
What Action Is Requested?
```

HTTP Methods solve this problem.

---

## What Are HTTP Methods?

HTTP Methods define the operation a client wants to perform.

Example:

```http
GET /users
```

Meaning:

```text
Retrieve Users
```

Methods provide intent.

---

## Common HTTP Methods

| Method | Purpose |
|----------|----------|
| GET | Read Data |
| POST | Create Data |
| PUT | Replace Data |
| PATCH | Partial Update |
| DELETE | Remove Data |
| HEAD | Headers Only |
| OPTIONS | Supported Operations |

---

## GET

Purpose:

```text
Retrieve Data
```

Example:

```http
GET /users/123
```

Characteristics:

- Safe
- Idempotent
- No resource modification

Common usage:

- APIs
- Websites
- Search operations

---

## POST

Purpose:

```text
Create Resource
```

Example:

```http
POST /users
```

Characteristics:

- Not idempotent
- Usually creates new resources

Common usage:

- Registration
- Form submission
- Resource creation

---

## PUT

Purpose:

```text
Replace Existing Resource
```

Example:

```http
PUT /users/123
```

Characteristics:

- Idempotent
- Full replacement

If executed multiple times:

```text
Same Final State
```

---

## PATCH

Purpose:

```text
Partial Update
```

Example:

```http
PATCH /users/123
```

Only specific fields are updated.

Common usage:

- Profile updates
- Status changes

---

## DELETE

Purpose:

```text
Remove Resource
```

Example:

```http
DELETE /users/123
```

Characteristics:

- Idempotent

Deleting repeatedly should result in the same final state.

---

## HEAD

Purpose:

```text
Retrieve Headers Only
```

Example:

```http
HEAD /users
```

Useful for:

- Metadata checks
- Health checks
- Cache validation

---

## OPTIONS

Purpose:

```text
Discover Supported Methods
```

Example:

```http
OPTIONS /users
```

Common in:

- APIs
- CORS preflight requests

---

## Safe Methods

Safe methods do not modify server state.

Examples:

```text
GET
HEAD
OPTIONS
```

---

## Idempotent Methods

An idempotent request can be executed repeatedly with the same result.

Examples:

```text
GET
PUT
DELETE
HEAD
OPTIONS
```

Common interview topic.

---

## Production Impact

HTTP methods influence:

- API design
- Caching
- Security controls
- Load balancing
- REST architecture

Choosing the wrong method can create reliability and maintenance issues.

---

## Common Production Problems

### Using GET For Updates

Symptoms:

- Unexpected side effects
- Cache issues

### Using POST Everywhere

Symptoms:

- Poor API design
- Reduced clarity

### Incorrect Idempotency

Symptoms:

- Duplicate operations
- Data inconsistency

---

## Common Interview Questions

- GET vs POST?
- PUT vs PATCH?
- What is idempotency?
- Which methods are safe?
- Which methods are idempotent?
- Why is DELETE idempotent?
- What is OPTIONS used for?
- What is HEAD used for?

---

## Quick Revision

| Method | Key Purpose |
|----------|----------|
| GET | Read Data |
| POST | Create Data |
| PUT | Full Update |
| PATCH | Partial Update |
| DELETE | Remove Resource |
| HEAD | Headers Only |
| OPTIONS | Discover Capabilities |
| Safe Methods | GET, HEAD, OPTIONS |
| Idempotent Methods | GET, PUT, DELETE, HEAD, OPTIONS |
| Most Common Interview Topic | PUT vs PATCH |