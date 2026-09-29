# T.O.B.I. Academy

T.O.B.I. Academy runs locally alongside Home Assistant. Its SQLite database and encrypted connection state live only in the private `/data` directory managed by Home Assistant.

## First start

1. Install and start the app.
2. Enable **Show in sidebar**.
3. Open **T.O.B.I. Academy** from the Home Assistant sidebar.

The database is created automatically. No POLADIUM password is requested or stored.

## Options

- `sync_interval_minutes`: Refresh interval for an active portal session. Minimum 15 minutes.
- `timezone`: Time zone for timetable calculations. Defaults to `Europe/Berlin`.

## Security model

Home Assistant Ingress handles access authentication. The connector only reuses a portal session transferred explicitly from the native Academy client. It never submits a username or password, restricts requests to allowlisted POLADIUM endpoints, encrypts the session at rest, and stops when the session expires.
