# Rails Application Tasks

This repository contains solutions for the following Rails tasks:

1. **Add a Custom Route** (`/about`)  
2. **Set Up a Model with Associations** (Author → Post)  
3. **Deploy a Rails Application** (Preparation & Instructions)

---

## 1. Project Setup

Follow these steps to set up the Rails project locally.

### Prerequisites

- Ruby (version 3.0.0 or later)
- Rails (version 7.0.0 or later)
- PostgreSQL or any other preferred database
- Git

### Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/basitali111/my_interview_app.git
   ```
   Change into the project directory:
   ```bash
   cd my_interview_app
   ```

2. **Install Gems**  
   ```bash
   bundle install
   ```

3. **Set up the Database**  
   - Update your `config/database.yml` with your local database credentials.
   - Run migrations:
     ```bash
     rails db:create
     rails db:migrate
     ```

4. **Run the Rails Server**  
   ```bash
   rails server
   ```
   Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 2. Custom Route `/about`

- A new route `/about` points to a static "About Us" page.
- The page is styled using [Bootstrap](https://getbootstrap.com/).

To see the "About Us" page, visit:  
```
http://localhost:3000/about
```

---

## 3. Model with Associations (Author → Post)

- A new `Author` model has been created with a one-to-many association to `Post`.
- Deleting an `Author` automatically deletes all associated `Posts`.

#### Generating the Models

```bash
rails generate model Author name:string
rails generate model Post title:string content:text author:references
rails db:migrate
```

#### Association

```ruby
# app/models/author.rb
class Author < ApplicationRecord
  has_many :posts, dependent: :destroy
end

# app/models/post.rb
class Post < ApplicationRecord
  belongs_to :author
end
```

---

## 4. Deployment Preparation

### Why Not Deployed to Heroku?

Heroku’s free tier for Rails applications has been discontinued.

## Feedback & Contributions

If you have any feedback or would like any changes to be made, please let me know or open an issue in this repository. I’m happy to accommodate any requests you may have.

**Thank you for reviewing this project!**

```

---

If you have any questions or requests, feel free to reach out.  
Thank you!