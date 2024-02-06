# Tell Rails Your Foreign Key is a UUID

Let's say you have a blog with an `Author` model, and you want to create a
`blog_posts` table. Each post has an author, and you want a foreign key on
`blog_posts` to the Author's id.

``` ruby
class CreateAuthors < ActiveRecord::Migration[7.0]
  def change
    create_table :authors do |t|
      t.string :name
    end
  end
end

class CreateBlogPosts < ActiveRecord::Migration[7.0]
  def change
    create_table :blog_posts do |t|
      t.string :title
      t.text :content
      t.references :author, null: false, foreign_key: true

    end
  end
end
```

Pretty straightforward, right? But if `Author#id` is a UUID, you'll probably
run into some issues with this migration. Rails by default assumes your table's
IDs will be `BigInt` and if your IDs aren't then you need to specify the `type`
in `t.references`:

``` ruby
class CreateAuthors < ActiveRecord::Migration[7.0]
  def change
    create_table :authors, id: :uuid do |t|
      t.string :name
    end
  end
end

class CreateBlogPosts < ActiveRecord::Migration[7.0]
  def change
    create_table :blog_posts, id: :uuid do |t|
      t.string :title
      t.text :content
      t.references :author, null: false, foreign_key: true, type: :uuid

    end
  end
end
```

via https://til.hashrocket.com/posts/t9w6z3nomd-tell-rails-your-foreign-key-is-a-uuid
