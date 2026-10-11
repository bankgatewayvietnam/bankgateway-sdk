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
