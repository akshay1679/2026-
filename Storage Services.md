# 🗂 1. Storage Services (Storing Unstructured Data at Scale)

This is about storing files like images, videos, backups, logs, etc.

## ✅ AWS – Amazon S3

- **Top-level unit:** ==Bucket== (name must be globally unique).
- **Data unit:** ==Object== (a file).
- **Why people like it:**
    
    - Very mature and reliable.
    - S3 API is the industry standard.
    - Huge ecosystem support.

---

## ✅ Azure – Blob Storage

- **Top-level unit:** ==Storage Account== (contains containers).
- **Data unit:** ==Blob== (file).
    - Types: Block, Append, Page blobs.

- **Why people like it:**

    - Strong integration with Windows & Active Directory.
    - Very good for Data Lakes and analytics.
        

---

## ✅ GCP – Cloud Storage

- **Top-level unit:** ==Bucket== (globally unique).
- **Data unit:** ==Object== (file).
- **Why people like it:**
    
    - Very strong global consistency.
    - Simple pricing model.
    - Designed for global workloads.