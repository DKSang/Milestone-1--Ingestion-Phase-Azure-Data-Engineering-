
# 🚀 Milestone 1 – Ingestion Phase (Azure Data Engineering)

## 📌 Giới thiệu

Dự án này mô phỏng giai đoạn **ingestion** trong một giải pháp Data Engineering end-to-end.
Mục tiêu là **thu thập dữ liệu từ Rebrickable** (bao gồm file download và REST API), sau đó lưu trữ vào **Azure Data Lake Storage (ADLS Gen2)** với cấu trúc phân tầng rõ ràng (raw zone).

## 🏗️ Kiến trúc tổng quan

* **Nguồn dữ liệu**:

  * File CSV nén từ trang download (Lego datasets).
  * REST API từ Rebrickable (user-specific data).
* **Công cụ ingestion**: Azure Data Factory (ADF).
* **Đích lưu trữ**: Azure Data Lake (raw container, partition by date).
* **Quản lý bảo mật**: Azure Key Vault + Managed Identity.
* **Triển khai**: CI/CD pipelines qua Azure DevOps (Dev & Prod).

![ADF Pipeline](./Screenshot%202025-09-29%20004744.png)
![ADF Pipeline](./Screenshot%202025-09-29%20004806.png)

## 🔧 Các kỹ năng đã áp dụng

* **Azure Data Factory**:

  * Pipelines, datasets, linked services.
  * Parameterization & dynamic content.
  * Scheduling (daily ingestion).
  * Error handling + email notification.
* **Azure Storage / Data Lake**:

  * Cấu hình redundancy (LRS cho Dev, GRS cho Prod).
  * Lifecycle management policies & access tiers.
  * Tổ chức folder structure (by source, dataset, date).
* **Azure Key Vault**: quản lý secrets, token.
* **Security best practices**: Managed Identity + Entra groups + RBAC.
* **CI/CD**: Tích hợp với Git repository, deploy ADF pipelines qua Azure DevOps.

## ▶️ Cách chạy

1. Clone repo này.
2. Cập nhật file cấu hình `config.json` với endpoint/file cần ingest.
3. Deploy resource group + ADF + ADLS + Key Vault (Dev/Prod).
4. Trigger pipeline từ ADF hoặc để schedule tự động chạy hàng ngày.

---

💡 Đây là milestone đầu tiên trong hành trình Data Engineering với Azure.
Các milestone tiếp theo sẽ tập trung vào **transform** và **serve** dữ liệu.
>>>>>>> 25821d9009c3554ca3e921c3ef89543f89c5bad6


