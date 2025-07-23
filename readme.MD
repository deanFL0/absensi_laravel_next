# Attendance System API Documentation

## Base URL

`http://localhost:8000/api`

---

## Departements

### Get All Departements

`GET /departements`

**Response:**

```json
{
    "data": [
        {
            "id": 1,
            "departement_name": "Miss Ida Turner Jr.",
            "max_clock_in_time": "08:43:00",
            "max_clock_out_time": "16:43:00"
        },
        {
            "id": 2,
            "departement_name": "IT",
            "max_clock_in_time": "08:00:00",
            "max_clock_out_time": "16:00:00"
        },
        ...
    ],
    "links": {
        "first": "http://127.0.0.1:8000/api/departements?page=1",
        "last": "http://127.0.0.1:8000/api/departements?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "links": [
            {
                "url": null,
                "label": "&laquo; Previous",
                "active": false
            },
            {
                "url": "http://127.0.0.1:8000/api/departements?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next &raquo;",
                "active": false
            }
        ],
        "path": "http://127.0.0.1:8000/api/departements",
        "per_page": 20,
        "to": 7,
        "total": 7
    }
}
```

### Get Specific Departements

`GET /departements/{id}`

**Response:**

```json
[
  {
    "id": 1,
    "departement_name": "Engineering",
    "max_clock_in_time": "09:30:00",
    "max_clock_out_time": "17:30:00"
  }
]
```

### Create Departement

`POST /departements`
**Request Body:**

```json
[
  {
    "departement_name": "Engineering",
    "max_clock_in_time": "09:30:00",
    "max_clock_out_time": "17:30:00"
  }
]
```

### Update Departement

`PUT /departements/{id}`
**Request Body:**

```json
{
  "departement_name": "Engineering",
  "max_clock_in_time": "09:30:00",
  "max_clock_out_time": "17:30:00"
}
```

### Delete Departement

`DELETE /departements/{id}`
**Response:**

```json
{ "message": "Departement deleted successfully" }
```

---

## Employees

### Get All Employees

`GET /departements`

**Response:**

```json
{
    "data": [
        {
            "id": 1,
            "employee_id": "EMP-J1ASVCWUGWK2WLCDMZFXPST3SE3J1DDZ12WERCNENFA2F7",
            "name": "Miss Sydni Hermiston",
            "address": "3698 Carroll Mill Apt. 501\nWest Vidaberg, KS 97620-6778",
            "departement_id": 4,
            "departement": {
                "id": 4,
                "departement_name": "Mrs. Joanny Pagac Jr.",
                "max_clock_in_time": "08:57:00",
                "max_clock_out_time": "16:57:00"
            },
            "created_at": "2025-07-23T02:13:54.000000Z",
            "updated_at": "2025-07-23T08:47:33.000000Z"
        },
        ...
    ],
    "links": {
        "first": "http://127.0.0.1:8000/api/employees?page=1",
        "last": "http://127.0.0.1:8000/api/employees?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "links": [
            {
                "url": null,
                "label": "&laquo; Previous",
                "active": false
            },
            {
                "url": "http://127.0.0.1:8000/api/employees?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next &raquo;",
                "active": false
            }
        ],
        "path": "http://127.0.0.1:8000/api/employees",
        "per_page": 20,
        "to": 7,
        "total": 7
    }
}
```

---

### Get Specific Employees

`GET /employees/{id}`

**Response:**

```json
[
  {
    "id": 1,
    "employee_id": "EMP-J1ASVCWUGWK2WLCDMZFXPST3SE3J1DDZ12WERCNENFA2F7",
    "name": "Miss Sydni Hermiston",
    "address": "3698 Carroll Mill Apt. 501\nWest Vidaberg, KS 97620-6778",
    "departement_id": 4,
    "departement": {
      "id": 4,
      "departement_name": "Mrs. Joanny Pagac Jr.",
      "max_clock_in_time": "08:57:00",
      "max_clock_out_time": "16:57:00"
    },
    "created_at": "2025-07-23T02:13:54.000000Z",
    "updated_at": "2025-07-23T08:47:33.000000Z"
  }
]
```

### Create Employee

`POST /employees`
**Request Body:**

```json
[
  {
    "departement_id": 1,
    "name": "Miss Sydni Hermiston",
    "address": "3698 Carroll Mill Apt. 501\nWest Vidaberg, KS 97620-6778",
    "created_at": "2025-07-23T02:13:54.000000Z",
    "updated_at": "2025-07-23T08:47:33.000000Z"
  }
]
```

### Update Employee

`PUT /employees/{id}`
**Request Body:**

```json
{
  "employee_id": "EMP-J1ASVCWUGWK2WLCDMZFXPST3SE3J1DDZ12WERCNENFA2F7",
  "departement_id": 1,
  "name": "Miss Sydni Hermiston",
  "address": "3698 Carroll Mill Apt. 501\nWest Vidaberg, KS 97620-6778",
  "created_at": "2025-07-23T02:13:54.000000Z",
  "updated_at": "2025-07-23T08:47:33.000000Z"
}
```

### Delete Employee

`DELETE /employees/{id}`
**Response:**

```json
{ "message": "Employee deleted successfully" }
```

---

## Attendance

### Get Attendance log

`GET /attendances-log`
**Response:**

```json
{
    "data": [
        {
            "id": 1,
            "employee_id": "EMP-J1ASVCWUGWK2WLCDMZFXPST3SE3J1DDZ12WERCNENFA2F7",
            "attendance_id": "ATT-ORNI5LHBDNIKGHRRSBGSIS3RJDFIPNPK2CQBBLE9MTGSUXB3KI60HKA29H5CARYQ4U2DUM2Y0US38PRRZPPNYX9DDZPBSJU1",
            "date_attendance": "2017-08-23 17:16:50",
            "attendance_type": 1,
            "description": "Est nostrum quo ea ratione at quasi consequatur.",
            "created_at": "2025-07-23T02:13:55.000000Z",
            "updated_at": "2025-07-23T02:13:55.000000Z"
        },
        ...
    ],
    "links": {
        "first": "http://127.0.0.1:8000/api/employees?page=1",
        "last": "http://127.0.0.1:8000/api/employees?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "links": [
            {
                "url": null,
                "label": "&laquo; Previous",
                "active": false
            },
            {
                "url": "http://127.0.0.1:8000/api/employees?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next &raquo;",
                "active": false
            }
        ],
        "path": "http://127.0.0.1:8000/api/employees",
        "per_page": 20,
        "to": 7,
        "total": 7
    }
}
```

**Optional Filters (query params):**
|Parameter|Description|
| --- | --- |
|`filters[employee][departement_id][$eq]=1`|Filter by department ID|
|`filters[date_attendance][$eq]=2025-07-21`|Filter by date (YYYY-MM-DD)|

filter can be combined with `&` (e.g. `filters[employee][departement_id][$eq]=1&[date_attendance][$eq]=2025-07-21`)

### Clock in

`POST /attendances`
**Request Body:**

```json
{
  "employee_id": "EMP-ENQIN0WKZVKHK1YVARRYBR5U7QWNFLFTIROTPQEGKOLX9O",
  "clock_in": "2025-07-22 09:00:00"
}
```

### Clock out

`PUT /attendances/{id}`
**Request Body:**

```json
{
  "clock_out": "2025-07-22 17:00:00"
}
```
