# Model domeny

## Encje

| Entity | Description | Key Attributes |
| :--- | :--- | :--- |
| **User** | A person registered in the system (Client). | `id`, `name`, `email`, `password` |
| **Order** | A specific transaction or booking made by a user. | `id`, `user_id`, `service_id`, `order_date`, `total_price`, `status` |
| **Service** | The professional service being offered. | `id`, `category_id`, `name`, `description`, `current_price` |
| **Category** | A group used to classify services (e.g., Repair, Cleaning). | `id`, `name` |
| **Payment** | Financial record of the transaction. | `id`, `order_id`, `amount`, `payment_method`, `status` |
| **Service Delivery** | Logistics of where and when the service happens. | `id`, `order_id`, `location`, `scheduled_time` |
| **Review** | Feedback left by the user after the service. | `id`, `user_id`, `service_id`, `rating`, `comment` |


---

## Relacje

* **User → Order**: A *User* places an *Order* (1:N).
* **Order → Service**: An *Order* is linked directly to a *Service* (N:1).
* **Service → Category**: A *Service* belongs to a *Category* (N:1).
* **Order → Payment**: An *Order* has one *Payment* record (1:1).
* **Order → Service Delivery**: An *Order* defines one *Service Delivery* (1:1).
* **User → Review**: A *User* writes a *Review* (1:N).
* **Review → Service**: A *Review* evaluates a specific *Service* (N:1).

---

## Uwagi

```mermaid
graph TD
    User[User] -- places --> Order[Order]
    Order -- for --> Service[Service]
    Service -- belongs to --> Category[Category]
    Order -- paid by --> Payment[Payment]
    Order -- scheduled via --> Delivery[Service Delivery]
    User -- writes --> Review[Review]
    Review -- evaluates --> Service
