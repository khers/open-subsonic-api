# OpenSubsonic Website

[![Netlify Status](https://api.netlify.com/api/v1/badges/55c14fbc-7240-4dc0-9092-3cd442400473/deploy-status)](https://app.netlify.com/sites/opensubsonic/deploys)

This is the source code for the OpenSubsonic documentation website. It is built with [Hugo](https://gohugo.io) and the [Docsy][] theme. 

You can find detailed theme instructions in the [Docsy user guide][].

## Running in a container locally

You can run this project inside a [Docker](https://docs.docker.com/)
container, the container runs with a volume bound to the project's source
folder. This approach doesn't require you to install any dependencies other
than [Docker Desktop](https://www.docker.com/products/docker-desktop) on
Windows and Mac, and [Docker Compose](https://docs.docker.com/compose/install/)
on Linux.

1. Build the docker image

   ```bash
   docker-compose build
   ```

1. Run the built image

   ```bash
   docker-compose up
   ```

   > NOTE: You can run both commands at once with `docker-compose up --build`.

1. Verify that the service is working.

   Open your web browser and type `http://localhost:1313` in your navigation bar,
   This opens a local instance of the project's homepage. You can now make
   changes to the source code and those changes will immediately show up in your
   browser after you save.

2. To update the openApi files inside docker and validate that your changes are correct run the following command

   ```bash
   docker-compose run site npm run build
   ```


### Cleanup

To stop Docker Compose, on your terminal window, press **Ctrl + C**.

To remove the produced images run:

```bash
docker-compose rm
```
For more information see the [Docker Compose
documentation](https://docs.docker.com/compose/gettingstarted/).

## Setting up the development environment

1. Install dependencies:
   - [Go][]
   - [Hugo][]
   - [Node.js][]
2. Clone this repository
   ```bash
   git clone https://github.com/deluan/open-subsonic-api
   cd open-subsonic-api
   ```
3. If you want to do SCSS edits and want to publish these, you need to install `PostCSS`
   ```bash
   npm install
   ```

### Running the website locally

Building and running the site locally requires a recent `extended` version of [Hugo](https://gohugo.io).
You can find out more about how to install Hugo for your environment in our
[Getting started](https://www.docsy.dev/docs/getting-started/#prerequisites-and-installation) guide.

Once you've made your working copy of the site repo, from the repo root folder, run:

```bash
hugo server
```

### Troubleshooting

As you run the website locally, you may run into the following error:

```
➜ hugo server

INFO 2021/01/21 21:07:55 Using config file: 
Building sites … INFO 2021/01/21 21:07:55 syncing static files to /
Built in 288 ms
Error: Error building site: TOCSS: failed to transform "scss/main.scss" (text/x-scss): resource "scss/scss/main.scss_9fadf33d895a46083cdd64396b57ef68" not found in file cache
```

This error occurs if you have not installed the extended version of Hugo.
See this [section](https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-hugo) of the user guide for instructions on how to install Hugo.

Or you may encounter the following error:

```
➜ hugo server

Error: failed to download modules: binary with name "go" not found
```

This error occurs if you have not installed the `go` programming language on your system.
See this [section](https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-go-language) of the user guide for instructions on how to install `go`.


[Go]: https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-go-language
[Hugo]: https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#install-hugo
[Node.js]: https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites/#installupgrade-nodejs
[Docsy user guide]: https://docsy.dev/docs
[Docsy]: https://docsy.dev
