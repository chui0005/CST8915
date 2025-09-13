# Youtube Demo link 

[My demo](https://youtu.be/M7kaENXgB94)

---

# Pet Store Microservices Overview

This project is composed of three main services that work together to provide a complete pet store application: the **Order Service**, the **Product Service**, and the **Store Front**. 

---

## Order Service (Node.js)

The **Order Service** is responsible for creating, managing, and retrieving customer orders. It handles requests such as placing new orders.

- **Technology:** Implemented in **Node.js** using Express for building RESTful APIs.  
- **Interactions:**  
  - The **Store Front** (Vue.js) communicates with it via HTTP endpoints to place orders.  
  - There is currently no interaction with the **Product Service**  but in a production ready application I think it would query **Product Service** when verifying product details during order creation.  

---

## Product Service (Rust)

The **Product Service** manages the product catalog. It is responsible for storing and serving product information such as descriptions, pricing, and availability. 

- **Technology:** Built in **Rust**.  
- **Interactions:**  
  - The **Store Front** requests product lists and details via its HTTP API.  
  - There is currently no interaction with the **Order Service** but in a production ready application I think  **Order Services** would query its API to validate items in an order (e.g., check product ID, price, stock).  

---

## Store Front (Vue.js)

The **Store Front** is the user interface of the system. It provides customers with the ability to browse the catalog, view product details, add items to a cart, and place orders. It acts as the main entry point for end users.

- **Technology:** Implemented in **Vue.js**.  
- **Interactions:**  
  - Communicates with the **Product Service** to display product data.  
  - Submits order requests and retrieves order status from the **Order Service**.  
