# Salon Scheduler

A command-line appointment booking system for a salon, built with Bash and PostgreSQL.

## Overview

This interactive script allows salon staff to book appointments for customers. It displays available services, looks up or creates customer records, and schedules appointments — all from the terminal.

## Files

| File | Description |
|------|-------------|
| `salon.sh` | Main Bash script that runs the interactive scheduler |
| `salon.sql` | PostgreSQL database dump to set up the schema and data |
| `examples.txt` | Sample input/output showing expected script behavior |

## Database Schema

The PostgreSQL database (`salon`) contains three tables:

- **services** — Available salon services (e.g., cut, color, perm, style, trim)
- **customers** — Customer records with `customer_id`, `name`, and `phone`
- **appointments** — Booked appointments linking a customer, service, and time

## Setup

### Prerequisites

- PostgreSQL installed and running
- A PostgreSQL user named `freecodecamp`

### 1. Create the Database

```bash
psql --username=freecodecamp < salon.sql
```

### 2. Make the Script Executable

```bash
chmod +x salon.sh
```

### 3. Run the Scheduler

```bash
./salon.sh
```

## Usage

1. The script displays all available services with numbered options.
2. Enter the number corresponding to the desired service.
3. Enter the customer's phone number.
   - If the customer is not found, you will be prompted for their name and a new record will be created.
4. Enter the desired appointment time.
5. A confirmation message is displayed with the booking details.

### Example Session

```
~~~~~ MY SALON ~~~~~

Welcome to My Salon, how can I help you?

1) cut
2) color
3) perm
4) style
5) trim
1

What's your phone number?
555-555-5555

I don't have a record for that phone number, what's your name?
Fabio

What time would you like your cut, Fabio?
10:30

I have put you down for a cut at 10:30, Fabio.
```
