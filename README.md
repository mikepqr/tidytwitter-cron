# Run tidytwitter every day using Github Actions

[tidytwitter](https://github.com/mikepqr/tidytwitter) is a python script that
deletes your old tweets and favorites.

This repository demonstrates the use of Github Actions to run it every 24 hours
(or as often as you like).

# Instructions

1. Create a copy of this repository using the
   [template](https://github.com/mikepqr/tidytwitter-cron/generate)

2. Go to Settings then Secrets then "New repository secret" and add the
   following secrets (as documented in the [tidytwitter
   README](https://github.com/mikepqr/tidytwitter#installation)):

       TIDYTWITTER_API_KEY
       TIDYTWITTER_API_SECRET
       TIDYTWITTER_ACCESS_TOKEN
       TIDYTWITTER_ACCESS_TOKEN_SECRET

3. Trigger the workflow manually (see "Actions") to check it works. You should
   see [something like
   this](https://github.com/mikepqr/tidytwitter-cron/runs/1804087604?check_suite_focus=true)
   after a minute or so.

And you're done. tidytwitter will run every day at [05:00
UTC](https://github.com/mikepqr/tidytwitter-cron/blob/ad5bc23288e9ec56e70fe7de594604ea9d79eee3/.github/workflows/tidytwitter.yml#L6)
(change that line if you want it to run at a different time).

## Note

There is nothing special about tidytwitter. You can use Github actions to run
pretty much any light weight recurring job, including those that take backups.
This happens to be an unusually simple example, but take a look at [Git
scraping](https://simonwillison.net/2020/Oct/9/git-scraping/) for sophisticated
stateful examples.
[real-estate-scrape](https://github.com/mikepqr/real-estate-scrape) is one of
mine.
