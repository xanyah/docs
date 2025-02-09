# Self-building your desktop application

The web application is a simple Vite + React web application.

:::warning

The following features are disabled on the web application because of their requirements of native APIs:

- Printing a sale receipt
- Printing an invoice

:::

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
