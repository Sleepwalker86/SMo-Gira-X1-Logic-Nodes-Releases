# Logikbaustein PiHole Gira X1

Dieser Baustein fragt die PiHole Status API in eurem Netzwerk ab.

Trifft eine „1“ am Eingang „Trigger“ ein wird die API abgefragt und an die Ausgänge weitergeleitet.

Folgende Eingänge stehen zur Verfügung:
- Trigger (Bool)

Folgende Parameter stehen zur Verfügung:
- Host (String)

Folgende Ausgänge stehen zur Verfügung:
- domains_being_blocked (Integer)
- dns_queries_today (Integer)
- ads_blocked_today (Double)
- public double ads_percentage_today (Integer)
- unique_domains (Integer)
- queries_forwarded (Integer)
- queries_cached (Integer)
- clients_ever_seen (Integer)
- unique_clients (Integer)
- dns_queries_all_types (Integer)
- reply_UNKNOWN (Integer)
- reply_NODATA (Integer)
- reply_NXDOMAIN (Integer)
- reply_CNAME (Integer)
- reply_IP (Integer)
- reply_DOMAIN (Integer)
- reply_RRNAME (Integer)
- reply_SERVFAIL (Integer)
- reply_REFUSED (Integer)
- reply_NOTIMP (Integer)
- reply_OTHER (Integer)
- reply_DNSSEC (Integer)
- reply_NONE (Integer)
- reply_BLOB (Integer)
- dns_queries_all_replies (Integer)
- privacy_level (Integer)
- file_exists (Bool)
- status (String)
- absolute (Integer)
- days (Integer)
- hours (Integer)
- minutes (Integer)
- Aktive (Bool, 1= Status enabled 0= Status disabled)

API PiHole https://discourse.pi-hole.net/t/pi-hole-api/1863

Verwendetes Icon https://www.flaticon.com/free-icons/hand Hand icons created by Freepik - Flaticon
