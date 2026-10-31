# Product Hierarchy UML Class Diagram

```mermaid
classDiagram
    class Product {
        <<abstract>>
        -Long id
        -String name
        -double price
        +getId() Long
        +getName() String
        +getPrice() double
        +getSummary()* String
    }
    class Discountable {
        <<interface>>
        +applyDiscount(double rate) void
        +getDiscountedPrice() double
    }
    class DigitalProduct {
        -String downloadUrl
        -double fileSizeMB
        +getSummary() String
        +applyDiscount(double rate) void
        +getDiscountedPrice() double
    }
    class PhysicalProduct {
        -double weightKg
        -String dimensions
        +getSummary() String
        +applyDiscount(double rate) void
        +getDiscountedPrice() double
    }
    Product <|-- DigitalProduct
    Product <|-- PhysicalProduct
    Discountable <|.. DigitalProduct
    Discountable <|.. PhysicalProduct
```