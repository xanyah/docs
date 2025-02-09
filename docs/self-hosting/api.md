# Self-hosting your API

The API is a simple Ruby on Rails web application.

It can be hosted quite easily by any PaaS, such as [Scalingo](https://scalingo.io).

## Requirements

- Ruby `>= 3.4.1`
- A Postgresql database `>= 17.0`
- Either Vips or Minimagick to handle [Active Storage images transformations](https://guides.rubyonrails.org/active_storage_overview.html#transforming-images)

## Environment variables

Here are the environment variables that are required to make the API work.
Currently, only S3-compatible APIs are supported for file storage, but any pull-request will be welcome to add other adapters.

| Environment variable         | Description                                                                                               | Required           | Default value |
|------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------|---------------|
| `DATABASE_URL`               | The database URL. Must be a postgres connection string like `postgres://USER:PASSWORD@HOST:POST/DATABASE` | :white_check_mark: |               |
| `SCALEWAY_ACCESS_KEY_ID`     | The S3 file storage access key                                                                            | :white_check_mark: |               |
| `SCALEWAY_ACCESS_KEY_SECRET` | The S3 file storage access key secret                                                                     | :white_check_mark: |               |
| `SCALEWAY_BUCKET_NAME`       | The S3 file storage bucket name                                                                           | :white_check_mark: |               |
| `SCALEWAY_ENDPOINT`          | The S3 file storage endpoint                                                                              | :white_check_mark: |               |
| `SCALEWAY_REGION`            | The S3 file storage region                                                                                | :white_check_mark: |               |

## Setting up the server

```sh
# Clone the repository
git clone https://github.com/xanyah/api.git && cd api

# Install dependencies
bundle install --without development test

# Run migrations
bundle exec rails db:migrate

# Start the server
bundle exec puma -C config/puma.rb
```
