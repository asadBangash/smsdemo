# sms-demo — Demo access (local)

**URL:** `http://smsdemo.test`  
**Database:** `sms_demo` (separate from production `dream` on `dream.test`)

Set `APP_DEMO=true` in `.env`, then if you need a fresh dataset:

```bash
php artisan app:setup --fresh
php artisan storage:link
php artisan optimize:clear
```

**Demo password (all accounts below):** `123456`

**Login URL (all roles):** `{APP_URL}/login` (local: `http://smsdemo.test/login`)

| Portal | Email | After login |
|--------|-------|-------------|
| Super Admin | `superadmin@example.com` | Admin dashboard |
| Boys Branch Admin | `boysadmin@example.com` | Admin dashboard (Boys data only) |
| Girls Branch Admin | `girlsadmin@example.com` | Admin dashboard (Girls data only) |
| Boys Student | `boys.student@example.com` | `/student-panel-dashboard` |
| Girls Student | `girls.student@example.com` | `/student-panel-dashboard` |
| Boys Staff (Teacher) | `boys.teacher@example.com` | Admin dashboard (teacher permissions) |
| Girls Staff (Teacher) | `girls.teacher@example.com` | Admin dashboard (teacher permissions) |

Verify branch isolation:

```bash
php artisan demo:verify-branch-isolation
```