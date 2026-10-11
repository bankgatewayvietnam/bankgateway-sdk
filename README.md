<div align="center">

# 🏦 BankGateway.pro — Vietnam Bank Lookup & VietQR API
### Cổng API Tra Cứu Tên Chủ Tài Khoản Ngân Hàng & Giải Mã VietQR Napas 24/7 Siêu Tốc

[![Website](https://img.shields.io/badge/Website-bankgateway.pro-0070f3?style=for-the-badge&logo=googlechrome&logoColor=white)](https://bankgateway.pro)
[![Documentation](https://img.shields.io/badge/Docs-API_Reference-10b981?style=for-the-badge&logo=gitbook&logoColor=white)](https://bankgateway.pro/api-docs)
[![Latency](https://img.shields.io/badge/Latency-%3C140ms-8b5cf6?style=for-the-badge&logo=speedtest&logoColor=white)](https://bankgateway.pro)
[![Coverage](https://img.shields.io/badge/Banks-60+_Banks-f59e0b?style=for-the-badge)](https://bankgateway.pro)
[![License](https://img.shields.io/badge/License-MIT-gray?style=for-the-badge)](LICENSE)

<p align="center">
  <b>Hạ tầng Open Banking API Developer-First tại Việt Nam. Tích hợp xác thực chủ tài khoản thụ hưởng chỉ với 5 dòng code.</b>
</p>

[Khám Phá Website](https://bankgateway.pro) • [Tài Liệu API](https://bankgateway.pro/api-docs) • [Bảng Giá](https://bankgateway.pro/bang-gia-api-tra-cuu-tai-khoan) • [Cộng Đồng Telegram](https://t.me/bankgatewaypro)

</div>

---

## 📌 Giới Thiệu

**BankGateway** (https://bankgateway.pro) là nền tảng API cung cấp giải pháp xác minh danh tính tài khoản ngân hàng thụ hưởng trước khi lập lệnh chuyển tiền, kết nối trực tiếp cổng Napas 24/7 qua hạ tầng MBBank Fast-Track.

### 🎯 Điểm Khác Biệt & Ưu Thế Vượt Trội
* ⚡ **Độ Trễ Thấp Nhất Thị Trường:** Trung bình **80ms – 140ms**, đáp ứng lưu lượng tải lớn cho ứng dụng Fintech và Game.
* 🛡️ **Cam Kết 0đ Rủi Ro:** Hoàn tiền 100% / Không trừ tiền khi số tài khoản không tồn tại, sai định dạng hoặc ngân hàng đang bảo trì.
* 🎁 **Dùng Thử Miễn Phí:** Tặng ngay **50 requests test thực tế** khi liên kết tài khoản với bot Telegram `@bankgateway_bot`.
* 💎 **Đơn Giá Tiết Kiệm:** Chỉ từ **135đ / lượt tra cứu thành công**. Số dư ví và hạn mức lượt (Vault) không bao giờ hết hạn.
* 🔍 **Hỗ Trợ Toàn Diện:** Bao phủ 60+ ngân hàng Việt Nam và các ví điện tử hàng đầu (MoMo, ZaloPay, Viettel Money).

---

## 🚀 Hướng Dẫn Tích Hợp (SDK Code Samples)

### 1. cURL
```bash
curl --location 'https://api.bankgateway.pro/api/v1/lookup' \
  --header 'x-api-key: YOUR_API_KEY' \
  --header 'Content-Type: application/json' \
  --data '{
    "bin": "970422",
    "account_number": "00141103001"
  }'
```

### 2. Node.js / TypeScript
```typescript
import axios from 'axios';

async function lookupAccount(bin: string, accountNumber: string) {
  try {
    const response = await axios.post(
      'https://api.bankgateway.pro/api/v1/lookup',
      { bin, account_number: accountNumber },
      {
        headers: {
          'x-api-key': 'YOUR_API_KEY',
          'Content-Type': 'application/json',
        },
        timeout: 5000,
      }
    );
    return response.data;
  } catch (error: any) {
    console.error('Lỗi tra cứu:', error.response?.data || error.message);
  }
}

// Tra cứu mẫu MBBank
lookupAccount('970422', '00141103001').then(console.log);
```

### 3. Python
```python
import requests

url = "https://api.bankgateway.pro/api/v1/lookup"
headers = {
    "x-api-key": "YOUR_API_KEY",
    "Content-Type": "application/json"
}
payload = {
    "bin": "970422",
    "account_number": "00141103001"
}

response = requests.post(url, json=payload, headers=headers, timeout=5)
print(response.json())
```

### 4. PHP
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => 'https://api.bankgateway.pro/api/v1/lookup',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_POST => true,
  CURLOPT_POSTFIELDS => json_encode([
    'bin' => '970422',
    'account_number' => '00141103001'
  ]),
  CURLOPT_HTTPHEADER => [
    'x-api-key: YOUR_API_KEY',
    'Content-Type: application/json'
  ],
  CURLOPT_TIMEOUT => 5,
]);

$response = curl_exec($curl);
curl_close($curl);

echo $response;
```

---

## 📋 Danh Sách Mã BIN Ngân Hàng Tiêu Biểu

| Ngân Hàng | Tên Viết Tắt | Mã BIN Napas | Trạng Thái 24/7 |
| :--- | :--- | :---: | :---: |
| **MBBank** | MB | `970422` | Hoạt động |
| **Vietcombank** | VCB | `970436` | Hoạt động |
| **Techcombank** | TCB | `970407` | Hoạt động |
| **BIDV** | BIDV | `970418` | Hoạt động |
| **VietinBank** | CTG | `970415` | Hoạt động |
| **ACB** | ACB | `970416` | Hoạt động |
| **VPBank** | VPB | `970454` | Hoạt động |
| **TPBank** | TPB | `970423` | Hoạt động |
| **Sacombank** | STB | `970403` | Hoạt động |
| **MoMo** | MOMO | `971005` | Hoạt động |
| **ZaloPay** | ZALOPAY | `971011` | Hoạt động |

*(Xem toàn bộ 60+ ngân hàng tại: [https://bankgateway.pro/api-docs](https://bankgateway.pro/api-docs))*

---

## 💼 Kịch Bản Ứng Dụng (Use Cases)
* **Website TMĐT, Nạp Thẻ:** Kiểm tra họ tên thụ hưởng ngay khi khách nhập STK, tránh 100% rủi ro chuyển nhầm.
* **Hệ Thống Payout / Rút Tiền:** Tự động đối soát tên người nhận trước khi lệnh chi tiền được duyệt.
* **Phần Mềm Kế Toán & ERP:** Tự động hóa danh bạ thanh toán hóa đơn đối tác.

---

## 📞 Hỗ Trợ Kỹ Thuật
* **Website:** [https://bankgateway.pro](https://bankgateway.pro)
* **Tài liệu API:** [https://bankgateway.pro/api-docs](https://bankgateway.pro/api-docs)
* **Telegram CSKH:** [@bankgatewaypro](https://t.me/bankgatewaypro)
* **Bot Nhận 50 Reqs:** [@bankgateway_bot](https://t.me/bankgateway_bot)
