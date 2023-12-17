# Notifikace
Slouží k upozornění uživatele na nějakou událost bez použití [[Activity|Activity]]. Indikují také probíhající služby (služby, které mají zvýšenou prioritu).

Mohou mít tyto funkce:
- Zobrazení ikonky ve Statusbaru
- Zobrazení podrobnějších informací a spouštění [[Intent|Intentu]] po rozbalení Statusbaru
- Blikání notifikačních LED diod, zvukové upozornění a další HW záležitosti

## Notification Manager
Umožňuje vytvářet nové notifikace, upravovat staré nebo odstranit již nepotřebné.

```kotlin
String nsName = Context.NOTTFICATION_SERVICE
NotificationManager notificationManager = (NotificationManager).getSystemService(nsName)
```