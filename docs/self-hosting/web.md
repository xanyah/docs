# Self-hosting your web application

The web application is a simple Vite + React web application.

It can be hosted quite easily by any PaaS, such as [Scalingo](https://scalingo.io).

## Requirements

- Node.js `>= 22`
- Yarn `> 1.22`

## Environment variables

Here are the environment variables that are required to make the application work.

| Environment variable | Description                                            | Required           | Default value |
|----------------------|--------------------------------------------------------|--------------------|---------------|
| `VITE_API_URL`       | The API base URL                                       | :white_check_mark: |               |
| `VITE_SENTRY_DSN`    | The Sentry DSN, if you want to report errors on Sentry | :x:                |               |

## Building the application

```sh
# Clone the repository
git clone https://github.com/xanyah/desktop.git && cd desktop

# Install dependencies
yarn

# Build the static application
yarn build
```

Now, you can find a folder named `dist` containing all your assets to serve with a webserver.
