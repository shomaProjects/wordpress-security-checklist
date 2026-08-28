# wordpress-security-checklist
Checklist for basic WordPress security audit: CVE inventory, open admin panels and backups, ports, SSL, typical XSS/SQLi. Used in my client work.

# WordPress Security Checklist

Чек-лист базового аудита безопасности WordPress-сайта.
Использую в работе с клиентами, открыт для контрибуций.

## 1. Инвентаризация
- [ ] Версия WordPress актуальна
- [ ] Версии плагинов и тем сверены с базами CVE (wpvulndb, WPScan)
- [ ] Удалены неиспользуемые плагины и темы

## 2. Забытые двери
- [ ] /wp-admin/ не светит наружу без необходимости
- [ ] phpinfo.php отсутствует
- [ ] Бэкапы (.sql, .zip, .bak) не лежат в публичном доступе
- [ ] .env, wp-config.php.bak, .git — закрыты
- [ ] Directory listing отключён

## 3. Сеть и сервисы
- [ ] `nmap -sV target.com` — открыты только 80/443
- [ ] FTP, SSH, MySQL не торчат наружу
- [ ] XML-RPC отключён, если не используется

## 4. SSL и заголовки
- [ ] HTTPS работает, редирект с HTTP
- [ ] HSTS, X-Frame-Options, X-Content-Type-Options настроены
- [ ] Content-Security-Policy хотя бы базовый

## 5. Типовые уязвимости
- [ ] SQLi в плагинах (ручная проверка критичных форм)
- [ ] XSS в поиске и комментариях
- [ ] Перебор пользователей через ?author=N
- [ ] Брутфорс админки (ограничение попыток)

## Инструменты, которые я использую
- Nmap, WPScan (с разрешения владельца)
- Burp Suite Community
- curl, httpie для проверки заголовков

---
Автор: shoma_projects
Контакты для заказа аудита: https://kwork.ru/user/thefluxcode
