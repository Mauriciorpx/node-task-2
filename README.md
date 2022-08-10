# dbdiagram link:

https://dbdiagram.io/d/62f2425fc2d9cf52fa72a80f

# Blog scripts:

CREATE TABLE "users" (
"id" serial PRIMARY KEY,
"name" varchar NOT NULL,
"created_at" timestamp DEFAULT 'now()'
);

CREATE TABLE "comments" (
"coment_id" serial PRIMARY KEY,
"content" text NOT NULL,
"user_id" int NOT NULL,
"post_id" int NOT NULL,
"created_at" timestamp DEFAULT 'now()',
"updated_at" timestamp DEFAULT 'now()'
);

CREATE TABLE "posts" (
"post_id" serial PRIMARY KEY,
"user_id" int NOT NULL,
"content" text NOT NULL,
"created_at" timestamp DEFAULT 'now()',
"updated_at" timestamp DEFAULT 'now()'
);

ALTER TABLE "posts" ADD FOREIGN KEY ("user_id") REFERENCES "users" ("id");

ALTER TABLE "comments" ADD FOREIGN KEY ("post_id") REFERENCES "posts" ("post_id");

ALTER TABLE "comments" ADD FOREIGN KEY ("user_id") REFERENCES "users" ("id");

insert into users (
name
)values ('Andres'), ('Pedro'), ('Daniel');

insert into posts (
user_id,
content
) values (1,'Hola mundo'), (2,'Great Job'), (1,'Nice blog');

insert into comments (
post_id,
user_id,
content
) values (1, 1, 'Noob'), (1, 2, 'Nice code'), (3, 1, 'Sure, there is useful info');

select \* from comments
