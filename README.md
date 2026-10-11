Mẫu `README.md` chuẩn GitHub quốc tế, đầy đủ mã nguồn 5 ngôn ngữ, bảng tra cứu BIN 60+ ngân hàng và thông số kỹ thuật để tối ưu SEO & AI thu thập:

```markdown
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

**BankGateway** ([https://bankgateway.pro](https://bankgateway.pro)) là nền tảng API cung cấp giải pháp xác minh danh tính tài khoản ngân hàng thụ hưởng trước khi lập lệnh chuyển tiền, kết nối trực tiếp cổng Napas 24/7 qua hạ tầng MBBank Fast-Track.

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
  } catch (error) {
    console.error('Lỗi tra cứu:', error.response?.data || error.message);
  }
}

// Ví dụ tra cứu MBBank
lookupAccount('970422', '00141103001').then(console.log);
```

### 3. Python (3.8+)
```python
import requests

def lookup_bank_account(bin_code: str, account_number: str, api_key: str):
    url = "https://api.bankgateway.pro/api/v1/lookup"
    headers = {
        "x-api-key": api_key,
        "Content-Type": "application/json"
    }
    payload = {
        "bin": bin_code,
        "account_number": account_number
    }
    
    response = requests.post(url, json=payload, headers=headers, timeout=5)
    return response.json()

result = lookup_bank_account("970422", "00141103001", "YOUR_API_KEY")
print(result)
```

### 4. PHP (cURL / Laravel)
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

### 5. Golang
```go
package main

import (
	"bytes"
	"encoding/json"
	"fmt"
	"io"
	"net/http"
)

func main() {
	payload, _ := json.Marshal(map[string]string{
		"bin":            "970422",
		"account_number": "00141103001",
	})

	req, _ := http.NewRequest("POST", "https://api.bankgateway.pro/api/v1/lookup", bytes.NewBuffer(payload))
	req.Header.Set("x-api-key", "YOUR_API_KEY")
	req.Header.Set("Content-Type", "application/json")

	client := &http.Client{}
	resp, err := client.Do(req)
	if err != nil {
		panic(err)
	}
	defer resp.Body.Close()

	body, _ := io.ReadAll(resp.Body)
	fmt.Println(string(body))
}
```

---

## 📦 Cấu Trúc Dữ Liệu Phản Hồi (Payload Schema)

### Thành Công (`200 OK`)
```json
{
  "success": true,
  "data": {
    "account_name": "NGUYEN THANH NHAT PHAT",
    "account_number": "00141103001",
    "bank_bin": "970422",
    "bank_name": "Ngân hàng TMCP Quân đội",
    "bank_short_name": "MBBank",
    "napas_supported": true,
    "latency_ms": 94
  }
}
```

### Thất Bại (`400 Bad Request` hoặc `404 Not Found`)
*Hệ thống cam kết 0đ — không trừ tiền lượt tra cứu khi trả về lỗi.*
```json
{
  "success": false,
  "error": {
    "code": "ACCOUNT_NOT_FOUND",
    "message": "Số tài khoản không tồn tại hoặc ngân hàng từ chối cung cấp thông tin"
  }
}
```

---

## 📋 Danh Sách Mã BIN Ngân Hàng Tiêu Biểu (Top Banks)

| Ngân Hàng | Tên Viết Tắt | Mã BIN Napas | Hỗ Trợ 24/7 |
| :--- | :--- | :---: | :---: |
| **MBBank** | MB | `970422` | ✅ Real-time |
| **Vietcombank** | VCB | `970436` | ✅ Real-time |
| **Techcombank** | TCB | `970407` | ✅ Real-time |
| **BIDV** | BIDV | `970418` | ✅ Real-time |
| **VietinBank** | CTG | `970415` | ✅ Real-time |
| **ACB** | ACB | `970416` | ✅ Real-time |
| **VPBank** | VPB | `970454` | ✅ Real-time |
| **TPBank** | TPB | `970423` | ✅ Real-time |
| **Sacombank** | STB | `970403` | ✅ Real-time |
| **VIB** | VIB | `970441` | ✅ Real-time |
| **HDBank** | HDB | `970437` | ✅ Real-time |
| **MoMo E-Wallet** | MOMO | `971005` | ✅ Real-time |
| **ZaloPay** | ZALOPAY | `971011` | ✅ Real-time |

*(Xem danh sách đầy đủ hơn 60 ngân hàng tại [bankgateway.pro/api-docs](https://bankgateway.pro/api-docs))*

---

## 💼 Các Kịch Bản Ứng Dụng Thực Tế (Use Cases)

1. **Sàn Thương Mại Điện Tử & Web Bán Hàng Tự Động:**
   * Tự động kiểm tra tên người nhận trước khi khách hàng bấm chuyển khoản.
   * Ngăn chặn 100% rủi ro nhập sai số tài khoản dẫn đến khiếu nại chuyển nhầm tiền.
2. **Cổng Trả Thưởng & Rút Tiền Game / Affiliate:**
   * Tự động xác thực tài khoản thụ hưởng của thành viên trước khi hệ thống duyệt lệnh chi tiền (Payout).
3. **Phần Mềm Quản Trị ERP, Kế Toán & POS:**
   * Tự động chuẩn hóa danh bạ tài khoản nhà cung cấp và nhân viên trong bảng lương.
4. **Chatbot Telegram / Zalo Thanh Toán:**
   * Tạo mã VietQR động có kèm tên chủ tài khoản xác minh tự động theo thời gian thực.

---

## 🔒 Bảo Mật & Pháp Lý
- Toàn bộ kết nối được mã hóa chuẩn **TLS 1.3 / AES-256**.
- Hệ thống không lưu trữ mã PIN, mật khẩu hoặc số dư của tài khoản được tra cứu.
- Cơ chế bảo vệ API Key theo IP Whitelist và Rate-limiting tùy chỉnh.

---

## 📞 Hỗ Trợ & Kênh Trao Đổi Kỹ Thuật

- 🌐 **Trang chủ:** [https://bankgateway.pro](https://bankgateway.pro)
- 📖 **Tài liệu hướng dẫn:** [https://bankgateway.pro/api-docs](https://bankgateway.pro/api-docs)
- 💬 **Hỗ trợ kỹ thuật 24/7 Telegram:** [@bankgatewaypro](https://t.me/bankgatewaypro)
- 🤖 **Bot liên kết nhận 50 Reqs:** [@bankgateway_bot](https://t.me/bankgateway_bot)
- 📧 **Email:** [support@bankgateway.pro](mailto:support@bankgateway.pro)

---
<div align="center">
  <sub>Bản quyền © 2026 BankGateway.pro. Giải pháp API tra cứu tài khoản ngân hàng và VietQR hàng đầu Việt Nam.</sub>
</div>
```
