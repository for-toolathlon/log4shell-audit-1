# Log4Shell — Security Briefing Notes

## Core Facts

- **Vulnerability:** Apache Log4j2 JNDI features do not protect against attacker-controlled LDAP and other JNDI related endpoints. When message lookup substitution is enabled, an attacker can execute arbitrary code loaded from LDAP servers.
- **CVE identifiers:**
  - **CVE-2021-44228** — "Log4Shell" (Apache Log4j2 JNDI RCE vulnerability, CVSS 3.x score **10.0 CRITICAL**, CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H). Affects Log4j2 versions 2.0-beta9 through 2.14.1.
  - **CVE-2021-45046** — Thread Context Lookup pattern vulnerable to DoS (CVSS 3.x score 9.0 CRITICAL, CVSS:3.1/AV:N/AC:H/PR:N/UI:N/S:C/C:H/I:H/A:H). Affected `log4j-core` versions 2.0-beta9 through 2.12.2 and 2.13.0 through 2.16.0; fixed in 2.3.1 (Java 6), 2.12.3 (Java 7), and 2.16.0 (Java 8 and later).
- **Affected (affected) versions:** Log4j 2.0-beta9 through 2.14.1 (Log4Shell, CVE-2021-44228).
- **Fix versions:** Log4j 2.15.0 (Java 8 and later), 2.12.2 (Java 7), 2.3.1 (Java 6); **2.16.0 and later** is the recommended fix (removes JNDI entirely; also fixes CVE-2021-45046).
- **Severity:** CVE-2021-44228 rated **CVSS 3.1 10.0 / Critical** (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H) — unauthenticated remote RCE possible. CVE-2021-45046 rated 9.0 / Critical.

## Sources

- Apache Logging Services Security page: <https://logging.apache.org/security.html>
- ASF Apache Log4j CVEs announcement: <https://news.apache.org/foundation/entry/apache-log4j-cves>
- CISA Apache Log4j Vulnerability Guidance: <https://www.cisa.gov/news-events/news/apache-log4j-vulnerability-guidance>
- Wikipedia Log4Shell: <https://en.wikipedia.org/wiki/Log4Shell>
- CVE-2021-44228 official example page: <https://www.cve.org/CVERecord?id=CVE-2021-44228>
