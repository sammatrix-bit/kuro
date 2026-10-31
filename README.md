# KURO VPN

هستهٔ Xray-core + Aether (Cloudflare WARP/MASQUE) | UI dark/minimal | اندروید (Kotlin + Compose)

---

## 1. ساخت کانفیگ رایگان (Auto)

- دکمهٔ `+` در بالای صفحه
- **یک دکمه، همهٔ کارها**: نام + پروتکل + transport + ip-version → **دریافت توکن** و **اسکن گیت‌وی** خودکار
- ذخیرهٔ کانفیگ با گیت‌وی پین‌شده → ظاهر در Configs → `GO` برای اتصال

> رایگان: Aether/WARP + imported VLESS/VMess/Trojan/SS.

---

## 2. هسته‌ها و روند کار

- **Xray-core**: TUN کامل، VLESS/VMess/Trojan/SS، TLS/Reality, ws/gRPC/H2, split tunnel (*.ir/geoip:ir direct), DNS 1.1.1.1/8.8.8.8.
- **Aether core**: Cloudflare MASQUE/WG، توکن خودکار، گیت‌وی انتخاب‌شده توسط core.
- جریان:
  - Aether: register identity (cached) → core setup → SOCKS 1819 → TUN.
  - Xray: parse config → build JSON → KuroVpnService loop → latency test.

---

## 3. IP Scanner (رونده کار)

- دکمهٔ «شروع اسکن IP»
- log persist و terminal viewport
- gateway انتخاب‌شده در `lastScannedEndpoint` ذخیره می‌شود
- پس از scan در ساخت کانفیگ استفاده می‌گردد.

---

## 4.

---

نکته Media/Video: mux off، keepAlive 15s، connIdle 12، uplink/downlink 0 (پایدار برای seek).# kuro
