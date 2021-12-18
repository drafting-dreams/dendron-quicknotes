---
id: zzqTvXLGunv2F4OdzGObq
title: Cookies
desc: ''
updated: 1639841028253
created: 1639835690368
---

# Cookies are shared among different ports on a host

Once when I was using Egg.js, I tried to set cookie on `localhost:8000`, but didn't success. That's because cookies can be shared among different ports on a host, thus there's no need to add a port when setting a cookie. Below are some material found on the Internet.

For historical reasons, cookies contain a number of security and privacy infelicities. For example, a server can indicate that a given cookie is intended for "secure" connections, but the Secure attribute does not provide integrity in the presence of an active network attacker. **Similarly, cookies for a given host are shared across all the ports on that host, even though the usual "same-origin policy" used by web browsers isolates content retrieved via different ports.**

**Cookies do not provide isolation by port.** If a cookie is readable by a service running on one port, the cookie is also readable by a service running on another port of the same server. If a cookie is writable by a service on one port, the cookie is also writable by a service running on another port of the same server. For this reason, servers SHOULD NOT both run mutually distrusting services on different ports of the same host and use cookies to store security sensitive information.

# Cookies' content can not be in Chinese

Also while using Egg.js, I can't set cookies content with Chinese. Need to encode the content in the server first then set cookie.
