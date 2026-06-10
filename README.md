# Music Store Analysis

SQL-based analysis of a music store database using PostgreSQL. Explores employee hierarchy, customer spending, popular genres, and artist performance through basic, moderate, and advanced queries.

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

A schema diagram is available at `music store data/music store data/schema_diagram.png`.

## Questions Answered

### Basic
- Senior most employee by job title
- Countries with most invoices
- Top 3 invoice totals
- Best city for a promotional festival (highest invoice sum)
- Best customer (most money spent)

### Moderate
- Rock music listeners (email, name, genre)
- Top 10 rock bands by track count
- Tracks longer than average song length

### Advanced
- Amount spent by each customer per artist
- Top customer by spending per country (handles ties)

## Files

- `Music_Store_Analysis.sql` — all SQL queries
- `music store data/` — CSV data files and schema diagram
