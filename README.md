## 📌 Serverless E-commerce Social Syndication API

An automated edge-computing integration that bridges e-commerce platforms with social media. This serverless API listens for product creation webhooks and instantly syndicates SEO-optimized product pins to Pinterest.

Manual social media posting for e-commerce catalogs is time-consuming and prone to human error. Whether you are automating the marketing for physical goods or digital resources analyzing [behavior patterns in business](https://www.linkedin.com/pulse/7-behavior-patterns-business-reveal-more-than-words-mohamed-aziz-hzu9f/), this project creates a hands-free pipeline. The moment a new product goes live on a storefront, this worker catches the webhook, formats the metadata for Pinterest's search algorithm, and publishes the media directly to a targeted board.

### 🚀 Core Features

* **Real-Time Webhook Listener:** Instantly triggers upon receiving a `product.created` webhook from platforms like Shopify or WooCommerce.
* **SEO Metadata Formatting:** Automatically maps e-commerce product titles and descriptions to Pinterest's native SEO format, appending relevant hashtags.
* **Asynchronous Publishing:** Utilizes the official Pinterest v5 REST API to securely publish media without slowing down the e-commerce backend.
* **Edge Authentication:** Securely manages OAuth access tokens at the network edge using encrypted environment variables.

### 🛠️ Architecture & Tech Stack

* **Compute:** Cloudflare Workers (JavaScript/ES Modules)
* **Integration:** Pinterest REST API (v5)
* **Trigger:** standard JSON Webhooks (`POST` requests)

### 📊 Example Webhook Payload (Incoming)

The API expects a standard e-commerce webhook payload when a product is published:

```json
{
  "product_id": "987654321",
  "title": "The Psychology of Body Language - eBook",
  "description": "Unlock the secrets of non-verbal communication with our comprehensive guide...",
  "url": "[https://example-store.com/products/body-language-ebook](https://example-store.com/products/body-language-ebook)",
  "image_url": "[https://example-store.com/cdn/images/cover-art.jpg](https://example-store.com/cdn/images/cover-art.jpg)",
  "price": "14.99",
  "currency": "USD"
}
