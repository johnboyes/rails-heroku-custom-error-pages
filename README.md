# Example rails app demonstrating using a custom Heroku buildpack to serve custom error pages
as static files

See https://medium.com/@tair/custom-error-pages-in-rails-you-re-doing-it-wrong-ba1d20ec31c0

## Set up

[Deploy the app to Heroku] in the normal way, then:

Manually set your buildpack to Heroku's default
Ruby buildpack

```
heroku buildpacks:set heroku/ruby
```

Append the buildpack-ruby-rails-custom-error-pages to your buildpack list:

```
heroku buildpacks:add https://github.com/johnboyes/buildpack-ruby-rails-custom-error-pages
```

More info: [Heroku Dev Center article on multiple buildpacks]

Now if you visit your Heroku app in production and enter a url that will not be found, you will see
the custom 404 page.

# License

MIT, see the [LICENSE.md](LICENSE.md) file.

[ruby-buildpack]:https://github.com/heroku/heroku-buildpack-ruby
[Heroku Dev Center article on multiple buildpacks]:https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app
[Deploy the app to Heroku]: https://devcenter.heroku.com/articles/getting-started-with-rails4#deploy-your-application-to-heroku
