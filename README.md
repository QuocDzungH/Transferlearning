# Transfer Learning for Image Classification

Dự án này nghiên cứu và thực nghiệm phương pháp **Transfer Learning** (Học chuyển giao) ứng dụng trong bài toán phân loại hình ảnh (mèo và chó, CIFAR-10), giúp tối ưu hóa thời gian huấn luyện và nâng cao độ chính xác khi làm việc với các tập dữ liệu nhỏ.

---

## 🎯 Mục đích dự án
* **Thực nghiệm Transfer Learning:** Đánh giá hiệu quả của việc sử dụng các mô hình đã được huấn luyện trước (Pre-trained models) so with việc huấn luyện từ đầu (Train from scratch).
* **Đánh giá quy mô dữ liệu:** So sánh ảnh hưởng của số lượng dữ liệu huấn luyện (50, 200, 1000 mẫu) đến hiệu năng của mô hình.
* **Tối ưu hóa & Can thiệp mô hình:** Thực hành đóng đóng băng (freezing) / mở đóng băng (unfreezing) các lớp và điều chỉnh kiến trúc mạng cho bài toán phân loại cụ thể.

---

## 📊 Tập dữ liệu (Data)

Dự án sử dụng hai nguồn dữ liệu chính:

1. **Cats vs Dogs Dataset:**
   * **Nguồn:** Dữ liệu hình ảnh mèo và chó.
   * **Phân chia theo quy mô:** Để thử nghiệm khả năng học của mô hình trên các kích thước dữ liệu khác nhau, tập dữ liệu được chia thành các thư mục:
     * `transfer_learning_cat-dog-50`: 50 ảnh
     * `transfer_learning_cat-dog-200`: 200 ảnh
     * `transfer_learning_cat-dog-1000`: 1000 ảnh
   * **Nguồn nén:** `data50.zip`

2. **CIFAR-10 Dataset:**
   * Tập dữ liệu chuẩn gồm 60,000 ảnh màu kích thước 32x32 thuộc 10 lớp khác nhau (`transfer_learning_cifar10`).

---

## 🤖 Mô hình & Phương pháp (Models)

Dự án áp dụng khung làm việc **PyTorch** và **NumPy** để xử lý và huấn luyện:

* **Pre-trained Backbone:** Sử dụng các mạng thị giác máy tính phổ biến pre-trained trên tập ImageNet (ví dụ: *ResNet*, *VGG*, hoặc *MobileNet*).
* **Kỹ thuật can thiệp mô hình (Model Manipulation):**
  * **Feature Extraction:** Đóng băng toàn bộ các lớp convolutional base, chỉ huấn luyện classifier (Fully Connected Layers) mới ở cuối.
  * **Fine-tuning:** Mở đóng băng một vài lớp cuối hoặc toàn bộ mô hình với learning rate nhỏ để thích ứng tốt hơn với tập dữ liệu mới.

---
