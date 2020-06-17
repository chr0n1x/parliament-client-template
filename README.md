# parliament-client-template

## 🚀 Quick start

1. **Clone this repo**

   ```sh
   git clone git@git.corp.adobe.com:devrel/parliament-client-template.git
   cd parliament-client-template
   ```

1. **Install dependencies**

   ```sh
   npm install
   ```

1. **Create an environment File**

   Create a `.env.development` and `.env.production` files and define environment variables as below. Refer: [https://help.github.com/en/articles/creating-a-personal-access-token-for-the-command-line](https://help.github.com/en/articles/creating-a-personal-access-token-for-the-command-line)

   For local:

   ```
   GATSBY_SITE_PATH_PREFIX =
   GATSBY_GIT_CORP_TOKEN = 1cdba7077XXXXXXXXXXXXXXXX633c1
   GATSBY_SOURCE = git.corp.adobe.com/<source_org>/<source_repo>.git //Repo URL in given format which you want to use to generate a microsite
   GATSBY_SOURCE_BRANCH=master
   GATSBY_SOURCE_PATTERNS=**/*
   GATSBY_SOURCE_TITLE=My Docs Site
   ```

   For Jenkins:

   ```
   GATSBY_GIT_CORP_TOKEN = credentials('TOKEN')
   GATSBY_SOURCE = 'git.corp.adobe.com/<source_org>/<source_repo>.git' //Repo URL in given format which you want to use to generate a microsite
   GATSBY_TARGET = 'git.corp.adobe.com/<target_org>/<target_repo>.git' // Repo URL in given format where you want to host the static html build output from Gatsby for Gihub Pages
   GATSBY_SITE_PATH_PREFIX = '/pages/<target_org>/<target_repo>' // Path Prefix for link relationship to work
   GATSBY_SOURCE_BRANCH=master
   GATSBY_SOURCE_PATTERNS=**/*
   GATSBY_SOURCE_TITLE=My Docs Site
   ```

1. **Start developing.**

   ```sh
   gatsby develop
   ```

1. **Open the source code and start editing!**

   Your site is now running at `http://localhost:8000`!

   _Note: You'll also see a second link: _`http://localhost:8000/___graphql`_. This is a tool you can use to experiment with querying your data. Learn more about using this tool in the [Gatsby tutorial](https://www.gatsbyjs.org/tutorial/part-five/#introducing-graphiql)._

   Open the `my-default-starter` directory in your code editor of choice and edit `src/pages/index.js`. Save your changes and the browser will update in real time!

## ✅ Testing

### Development

1. **Run unit tests**

   ```sh
   npm run test:integration
   ```

2. ** Run end to end tests**

   ```sh
   gatsby clean
   npm run test:e2e
   ```

### Production

To simulate production tests first set the environment variable `GATSBY_SITE_PATH_PREFIX` locally as it is required for production tests to run properly.

1. **Run unit tests**


   ```sh
   npm run test:integration
   ```

2. ** Run end to end tests**

   ```sh
   gatsby clean
   npm run build:prod
   npm run test:e2e:ci
   ```
