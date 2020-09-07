#   Sourcing from Headless CMS



My research so far has looked at different CMS:
*   Prismic
*   Strapi
*   GraphCMS

So far, *(07/09/2020)*, the conclusions have been:

### Prismic
*   Prismic is great for creating pages without much functionality. Without a JSON field and without integration to consume data in the CMS, it is difficult to create a component that has a specific behavior on the frontend. For example, you can easily create an image gallery, but if you had a requirement such as: "a message describing the image should be shown when the user clicks on each image", this would be difficult to achieve.
*   So, if you are creating a blog or institutional page, Prismic is great, otherwise not yet.

### GraphCMS
*   With GraphCMS you don't need a specific source plugin, you can use the [gatsby-source-graphql](https://www.gatsbyjs.com/plugins/gatsby-source-graphql/) plugin, for a more general purpose.
*   **However, you end up being limited to a rigid scheme**. Which is a shame as it practically makes it unfeasible. You will always need to create very specific and repetitive schemes.
*   That way, you can explore the content generated in the cms more freely through Gatsby's Graphql explorer. Integration is simpler, and requires less configuration than other plugins.
*   The Rich Text element comes with a out-of-the-box wysiwyg editor.
*   You do not need to set up a development and production environment for the CMS, which comes with tradeoffs.
*   GraphCMS, like Strapi, comes with JSON element out-of-the-box. This allows very customizable elements to be created and maintained between the CMS and the Frontend as long as there is a simple layer of communication between developers and content creators.

### Strapi
*   For a general purpose I found no better alternative than Strapi. It allows for any level of customization, which comes with a workload and learning.
*   The Rich Text Field of Strapi uses a Markdown syntax. While GraphCMS uses a WYSIWYG. If you plan to pass the html to jsx this is a shame. It would be great if Strapi returned out-of-the-box the html, markdown and text like graphcms.
*   You can customize the admin of Strapi and replace the Markdown editor. See this [tutorial](https://strapi.io/blog/how-to-change-the-wysiwyg-in-strapi).
*   Strapi is more customizable, and gives developers more power and autonomy. But it requires a little more communication between developers and content creators, as it is necessary that the contentTypes are informed for the configuration of the Gatsby plugin. I say a little more communication, because using a headless cms this communication is necessary anyway.
*   Using Strapi you can run locally and deploy with the rest of your system. This is particularly useful when working with a distributed or microservice based system. This feature of Strapi can be exploited to yield an improvement in the build times of Gatsby.
*   It is not trivial, but you can run the Strapi in Kubernetes Cluster. [Tutorial](https://strapi.io/blog/deploy-strapi-on-kubernetes-with-https).