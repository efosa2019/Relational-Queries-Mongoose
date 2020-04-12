Relational queries with Mongoose
You work at a news company and your task is to implement comments for a company blog. Each blog post (story) needs to have many comments. There are two ways to go about the blog implementation.

First, you can save/store all the comments right in the blog post document. This way you have a single collection. The downside is that if you need to access, index, or search individual comments, then having them inside of the blog post collection is not optimal.

The second approach is to create a new collection just for comments. In this collection, you can store comments which will be referenced to/from their blog posts. In the second approach (which is having two collections: posts and comments), you have two options: child refs and parent refs (refs - references).

Mongoose provides a mechanism to fetch related documents using populate() which greatly simplifies querying for both approaches. Without Mongoose, you still can implement parent-child relationship but you'll need to write more code yourself, such as making two queries instead of one.

So now that you understand the task. Let's get to implementing both approaches: child refs and parent refs starting with child refs first. Of course we will use Mongoose and its populate().

Child Refs
In the child refs approach, you store references (Object IDs) to comments in a post document. This will allow you to use Mongoose's populate() to fetch comments in a post query. Instead of making two queries: find post and find comment, you'll run a single query on post using populate().
