# Database Architecture

## Users
This table stores user information, including administrators.

| Column | Type | Description | Unique | Required |
| --- | --- | --- | --- | --- |
| id | INT | Unique user ID | ✅ | ✅ |
| name | VARCHAR | User's name | ❌ | ✅ |
| email | VARCHAR | User's email address | ✅ | ✅ |
| email_verified_at | TIMESTAMP | Timestamp of email verification | ❌ | ❌ |
| password | VARCHAR | User's password | ❌ | ✅ |
| is_admin | BOOLEAN | User is an admin or not | ❌ | ✅ |
| remember_token | VARCHAR | Remember token for login | ❌ | ❌ |
| created_at | TIMESTAMP | Record creation timestamp | ❌ | ✅ |
| updated_at | TIMESTAMP | Record update timestamp | ❌ | ✅ |

## Guests
This table stores information about guests.

| Column | Type | Description | Unique | Required |
| --- | --- | --- | --- | --- |
| id | INT | Unique guest ID | ✅ | ✅ |
| name | VARCHAR | Guest's name | ❌ | ✅ |
| phone | VARCHAR | Guest's phone number | ❌ | ✅ |
| purpose | VARCHAR | Purpose of the visit | ❌ | ✅ |
| created_at | TIMESTAMP | Record creation timestamp | ❌ | ✅ |
| updated_at | TIMESTAMP | Record update timestamp | ❌ | ✅ |

## Rooms
This table stores information about available rooms.

| Column | Type | Description | Unique | Required |
| --- | --- | --- | --- | --- |
| id | INT | Unique room ID | ✅ | ✅ |
| name | VARCHAR | Room name | ❌ | ✅ |
| description | TEXT | Room description | ❌ | ❌ |
| image | VARCHAR | Room image URL | ❌ | ❌ |
| quota | INT | Room quota (maximum capacity) | ❌ | ✅ |
| created_at | TIMESTAMP | Record creation timestamp | ❌ | ✅ |
| updated_at | TIMESTAMP | Record update timestamp | ❌ | ✅ |

## Bookings
This table stores information about bookings.

| Column | Type | Description | Unique | Required |
| --- | --- | --- | --- | --- |
| id | INT | Unique booking ID | ✅ | ✅ |
| guest_id | INT | Foreign key to Guests table | ❌ | ✅ |
| room_id | INT | Foreign key to Rooms table | ❌ | ✅ |
| start_date | DATE | Booking start date | ❌ | ✅ |
| end_date | DATE | Booking end date | ❌ | ✅ |
| created_at | TIMESTAMP | Record creation timestamp | ❌ | ✅ |
| updated_at | TIMESTAMP | Record update timestamp | ❌ | ✅ |

**Notes:**
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered into a property of a database table cannot be NULL.
