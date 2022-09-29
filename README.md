**ecommerce_tracker**

Internet retail, also known as e-commerce, is the largest sector of the electronics industry, having generated an estimated US$29 trillion in 2017 (Source: United Nations Conference on Trade and Development). E-commerce platforms like Shopify and WooCommerce provide a suite of services to businesses of all sizes. Due to the prevalence of these platforms, this backend application allows the user to perform Create, Read, UPdate, and Destroy (CRUD) on Insomnia.

- The seeds file contains all the existing information.
- The models file contains all the models and constraints.
- The routes file contains all the http request codes and route information.

### Database Models

- `Category`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `category_name`
    - String
    - Doesn't allow null values

- `Product`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `product_name`

    - String
    - Doesn't allow null values

  - `price`

    - Decimal
    - Doesn't allow null values
    - Validates that the value is a decimal

  - `stock`

    - Integer
    - Doesn't allow null values
    - Set a default value of 10
    - Validates that the value is numeric

  - `category_id`
    - Integer
    - References the `category` model's `id`

- `Tag`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `tag_name`
    - String

- `ProductTag`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `product_id`

    - Integer
    - References the `product` model's `id`

  - `tag_id`
    - Integer
    - References the `tag` model's `id`

### Relationships

- `Product` belogs to `Category`

- `Category` has many `Product`

- `Product` belogs to many `Tag`, and they are linked by `ProductTag` through the model

- `Tag` belongs to many `Product`
