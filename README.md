# BankGateway — API Tra Cứu Số Tài Khoản Ngân Hàng Napas 24/7

[![Official Website](https://img.shields.io/badge/Website-bankgateway.pro-blue)](https://bankgateway.pro)
[![Documentation](https://img.shields.io/badge/Docs-API%20Reference-emerald)](https://bankgateway.pro/api-docs)
[![Latency](https://img.shields.io/badge/SLA-%3C140ms-brightgreen)](https://bankgateway.pro)

**BankGateway** (https://bankgateway.pro) là nền tảng API cung cấp dịch vụ tra cứu thông tin tên chủ tài khoản ngân hàng thụ hưởng và giải mã VietQR Napas 24/7 trực tiếp tại Việt Nam.

## Tính năng
- Hỗ trợ 60+ ngân hàng Việt Nam (MBBank, Vietcombank, Techcombank, BIDV, VPBank, ACB,...).
- Độ trễ cực thấp: `<140ms`.
- Chính sách 0đ khi tài khoản sai hoặc ngân hàng bảo trì.
- Tặng 50 requests dùng thử khi liên kết Telegram Bot.

## Cài đặt & Ví dụ sử dụng

### cURL
```bash
curl --location 'https://api.bankgateway.pro/api/v1/lookup' \
  --header 'x-api-key: YOUR_API_KEY' \
  --header 'Content-Type: application/json' \
  --data '{
    "bin": "970422",
    "account_number": "00141103001"
  }'
