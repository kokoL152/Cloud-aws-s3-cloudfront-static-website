## 🚀 AWS S3 & CloudFront Static Website Deployment Project

This is an entry-level cloud architecture project designed to demonstrate how to host a static website using Amazon S3 and achieve global content delivery and acceleration with Amazon CloudFront.

---

## 💡 Project Goals & Highlights

* **Static Website Hosting:** Store HTML, CSS, JavaScript, and other static files in a highly available, durable, and scalable Amazon S3 bucket.
* **Content Delivery Network (CDN):** Leverage Amazon CloudFront as a CDN to cache website content at global edge locations, thereby accelerating content delivery, reducing access latency, and offloading traffic from the origin (S3).
* **Enhanced Security:** Ensure users access the website via encrypted connections by enforcing HTTPS redirection through CloudFront.
* **Serverless Architecture (Partial):** S3 and CloudFront are serverless services, eliminating the need to manage underlying servers, reducing operational complexity and cost.
* **Strict Free Tier Compliance:** The entire project is designed and implemented strictly within AWS Free Tier limits to ensure no additional costs are incurred during the learning process.

---

## 🛠️ AWS Services Used

* **Amazon S3:** Used for storing static website files (`index.html`, `error.html`, etc.), configured in static website hosting mode.
* **Amazon CloudFront:** Functions as a Content Delivery Network (CDN) to accelerate content delivery and provide low-latency global access.

---

## 📐 Architecture Diagram

Here's a high-level overview of the project's architecture:

```mermaid
graph LR
    User --> |HTTPS Request| CloudFront[CloudFront CDN];
    CloudFront -- Cache Hit --> User;
    CloudFront -- Cache Miss / First Request --> S3[Amazon S3 Bucket];
    S3 -- Website Endpoint --> CloudFront;
    subgraph AWS Cloud
        CloudFront;
        S3;
    end
