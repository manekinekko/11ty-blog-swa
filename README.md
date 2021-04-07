# eleventy-base-blog

A starter repository showing how to build a blog with the [Eleventy](https://github.com/11ty/eleventy) static site generator.

![Azure Static Web Apps CI/CD](https://github.com/manekinekko/11ty-blog-swa/workflows/Azure%20Static%20Web%20Apps%20CI/CD/badge.svg)

## Demos

* [Netlify](https://eleventy-base-blog.netlify.com/)
* [GitHub Pages](https://11ty.github.io/eleventy-base-blog/)
* [Azure Static Web Apps](https://aka.ms/11ty-swa)

## Deploy this to your own site

These builders are amazing—try them out to get your own Eleventy site in a few clicks!

* [Get your own Eleventy web site on Netlify](https://app.netlify.com/start/deploy?repository=https://github.com/11ty/eleventy-base-blog)
* [Get your own Eleventy web site on Vercel](https://vercel.com/import/project?template=11ty%2Feleventy-base-blog)
* [Get your own Eleventy web site on Azure](#deploy-on-azure-static-web-apps)

## Getting Started

### 1. Clone this Repository

```
git clone https://github.com/11ty/eleventy-base-blog.git my-blog-name
```


### 2. Navigate to the directory

```
cd my-blog-name
```

Specifically have a look at `.eleventy.js` to see if you want to configure any Eleventy options differently.

### 3. Install dependencies

```
npm install
```

### 4. Edit _data/metadata.json

### 5. Run Eleventy

```
npx eleventy
```

Or build and host locally for local development
```
npx eleventy --serve
```

Or build automatically when a template changes:
```
npx eleventy --watch
```

Or in debug mode:
```
DEBUG=* npx eleventy
```

### Implementation Notes

* `about/index.md` shows how to add a content page.
* `posts/` has the blog posts but really they can live in any directory. They need only the `post` tag to be added to this collection.
* Add the `nav` tag to add a template to the top level site navigation. For example, this is in use on `index.njk` and `about/index.md`.
* Content can be any template format (blog posts needn’t be markdown, for example). Configure your supported templates in `.eleventy.js` -> `templateFormats`.
	* Because `css` and `png` are listed in `templateFormats` but are not supported template types, any files with these extensions will be copied without modification to the output (while keeping the same directory structure).
* The blog post feed template is in `feed/feed.njk`. This is also a good example of using a global data files in that it uses `_data/metadata.json`.
* This example uses three layouts:
  * `_includes/layouts/base.njk`: the top level HTML structure
  * `_includes/layouts/home.njk`: the home page template (wrapped into `base.njk`)
  * `_includes/layouts/post.njk`: the blog post template (wrapped into `base.njk`)
* `_includes/postlist.njk` is a Nunjucks include and is a reusable component used to display a list of all the posts. `index.njk` has an example of how to use it.


## Deploy on Azure Static Web Apps

Follow the [Quickstart](https://docs.microsoft.com/en-us/azure/static-web-apps/getting-started?tabs=angular&WT.mc_id=javascript-20338-wachegha) guide for Azure Static Web Apps and use the following configuration:

![image](https://user-images.githubusercontent.com/1699357/113004691-1507d200-9174-11eb-84aa-bd84d15200b2.png)

![image](https://user-images.githubusercontent.com/1699357/113004921-48e2f780-9174-11eb-9a1c-43e517abdf55.png)

After the first build is done. You should get the generated URL for your app (you can also view this URL from the Azure Portal):
![image](https://user-images.githubusercontent.com/1699357/113006543-c3f8dd80-9175-11eb-9d83-4e89771d9e1e.png)



