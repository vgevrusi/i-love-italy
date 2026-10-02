# Pars Space API v1

این API برای ارتباط مستقیم بین پنل‌های Pars Space طراحی شده و UI جدید Pars Space از این namespace استفاده می‌کند.

## Base
`/api/pars/v1`

## Authentication
- Header: `X-Pars-Key: psp_...`
- یا `Authorization: Bearer psp_...`

کلید از داخل پنل در بخش **Pars Space API** ساخته و مدیریت می‌شود.

## Identity
`GET /api/pars/v1/identity`

## Health
`GET /api/pars/v1/health`

## Stats
`GET /api/pars/v1/stats`

## Users
`GET /api/pars/v1/users`
`POST /api/pars/v1/users`

## Inbounds
`GET /api/pars/v1/inbounds`
`POST /api/pars/v1/inbounds`

## Subscriptions
`GET /api/pars/v1/subscriptions`
`POST /api/pars/v1/subscriptions`

## Panel Nodes
`GET /api/pars/v1/nodes`
`POST /api/pars/v1/nodes/connect`
`POST /api/pars/v1/nodes/{node_id}/ping`
`POST /api/pars/v1/nodes/{node_id}/sync`
`DELETE /api/pars/v1/nodes/{node_id}`

## Node connection flow
1. روی پنل مقصد، از Settings > Pars Space API کلید `psp_...` را دریافت کنید.
2. در پنل مبدا، Nodes > Add node را باز کنید.
3. آدرس HTTPS پنل مقصد و کلید `psp_...` را وارد کنید.
4. Pars Space ابتدا `/identity` را روی پنل مقصد بررسی می‌کند.
5. بعد از تأیید، Node ذخیره می‌شود.
6. Ping و Sync از namespace اختصاصی Pars Space انجام می‌شوند.

## Important
این API برای ارتباط پنل به پنل از مسیرهای `/api/pars/v1/*` استفاده می‌کند و به APIهای legacy Spider برای اتصال Node وابسته نیست.
