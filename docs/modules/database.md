# 数据库设计

## 新闻数据库

使用 PostgreSQL，设计了如下表结构：

```SQL
                                        Table "public.news"
    Column     |           Type           | Collation | Nullable |             Default              
---------------+--------------------------+-----------+----------+----------------------------------
 id            | integer                  |           | not null | nextval('news_id_seq'::regclass)
 news_url      | text                     |           |          | 
 media         | character varying(20)    |           |          | 
 category      | character varying(20)    |           |          | 
 tags          | character varying(30)[]  |           |          | 
 title         | character varying(200)   |           |          | 
 description   | text                     |           |          | 
 content       | text                     |           |          | 
 first_img_url | text                     |           |          | 
 pub_time      | timestamp with time zone |           |          | 
Indexes:
    "news_pkey" PRIMARY KEY, btree (id)
    "news_news_url_key" UNIQUE CONSTRAINT, btree (news_url)
```

## 用户新闻数据库

```SQL
                                        Table "public.news"
    Column     |           Type           | Collation | Nullable |             Default              
---------------+--------------------------+-----------+----------+----------------------------------
 id            | integer                  |           | not null | 
 news_id       | integer                  |           |          | 
 cite_count    | integer                  |           |          | 
 ai_processed  | boolean                  |           |          | 
 data          | jsonb                    |           |          | 
```

## 用户数据库

```SQL
                                        Table "public.news"
    Column     |           Type           | Collation | Nullable |             Default              
---------------+--------------------------+-----------+----------+----------------------------------
 id            | integer                  |           | not null | 
 tags          | jsonb                    |           |          | 
 user_name     | character varying(12)    |           | not null | 
 password      | character varying(40)    |           | not null | 
 signature     | character varying(200)   |           |          | 
 mail          | character varying(100)   |           |          | 
 avatar        | text                     |           |          | 
 register_date | timestamp with time zone |           |          | 
 favorites     | jsonb                    |           |          | 
 readlist      | jsonb                    |           |          | 
 read_history  | jsonb                    |           |          | 
 search_history| jsonb                    |           |          | 
```

## 索引数据库

```SQL
    Column     |           Type           | Collation | Nullable |             Default              
---------------+--------------------------+-----------+----------+----------------------------------
 news_id       | integer                  |           | not null |
 news_url      | text                     |           | not null | 
 media         | text                     |           |          | 
 category      | character varying(20)    |           |          | 
 tags          | character varying(30)[]  |           |          | 
 title         | character varying(200)   |           |          | 
 description   | text                     |           |          | 
 content       | text                     |           |          | 
 first_img_url | text                     |           |          | 
 pub_time      | timestamp with time zone |           |          | 
```

