#### Goal

Create a Supabase project and one table for your app data.

#### Steps

1. Create a Supabase project. In the SQL editor or Table Editor, create one table with:
   - id (uuid or bigint), primary key
   - title (text)
   - created_at (timestamp default now()) or similar timestamp
2. Insert two rows as seed data.
3. Add SUPABASE_URL and SUPABASE_ANON_KEY to your React app environment and document where to put them in README.
4. Extra practice if you want
   - add a boolean column (completed) and seed one true, one false
