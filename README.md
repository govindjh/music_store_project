# Music Store Analysis

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?logo=postgresql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Advanced-blue)

SQL-based analysis of a digital music store database using PostgreSQL. Explores employee hierarchy, customer spending, popular genres, and artist performance through basic, moderate, and advanced queries.

## Schema Diagram

![Schema Diagram](music%20store%20data/schema_diagram.png)

## Dataset

The dataset consists of 13 CSV tables covering a digital music store schema:

| Table | Description |
|---|---|
| `album` | Albums linked to artists |
| `artist` | Artists |
| `customer` | Customer information |
| `employee` | Employee hierarchy and details |
| `genre` | Music genres (Rock, Jazz, etc.) |
| `invoice` | Sales invoices |
| `invoice_line` | Line items per invoice |
| `media_type` | Media formats |
| `playlist` | Playlists |
| `playlist_track` | Track-playlist associations |
| `track` | Individual tracks with length and genre |

## Prerequisites

- PostgreSQL (any recent version)
- pgAdmin or any SQL client

## Setup

1. Create a new PostgreSQL database:
   ```sql
   CREATE DATABASE music_store;
   ```

2. Create the schema tables using the schema diagram as a reference.

3. Import the CSV data from `music store data/`:
   ```sql
   COPY table_name FROM 'path/to/csv' DELIMITER ',' CSV HEADER;
   ```

4. Run the analysis queries in `Music_Store_Analysis.sql`.

## Questions Answered

### Basic
| Question | Query |
|---|---|
| Senior most employee by job title | `employee` table ordered by `levels` DESC |
| Countries with most invoices | `invoice` grouped by `billing_country` |
| Top 3 invoice totals | `invoice` totals sorted DESC |
| Best city for a promotional festival | City with highest sum of invoice totals |
| Best customer (most money spent) | Customer with highest total spend |

### Moderate
| Question | Query |
|---|---|
| Rock music listeners | Emails and names of customers who bought Rock tracks |
| Top 10 rock bands | Bands with the most Rock tracks |
| Tracks longer than average | Songs exceeding average song length |

### Advanced
| Question | Query |
|---|---|
| Amount spent by each customer per artist | Customer-artist spend breakdown using CTE |
| Top customer per country | Highest-spending customer per country (handles ties with `ROW_NUMBER()`) |

## Files

| File | Description |
|---|---|
| `Music_Store_Analysis.sql` | All SQL queries (basic → moderate → advanced) |
| `music store data/` | CSV data files and schema diagram |

## Key Techniques Used

- CTEs (Common Table Expressions)
- Window functions (`ROW_NUMBER()`, `PARTITION BY`)
- Subqueries
- Joins (INNER, implicit)
- Aggregation (`SUM`, `COUNT`, `GROUP BY`)
- Sorting and limiting results
