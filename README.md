# Base FHIR Client (Rails)

Provides the boilerplate code for jumpstarting any rails-based FHIR client.

Configured for Heroku deployment.

## Use

To use, just fork this repository and begin building your rails app according 
to your own specs.

### View Configuration

Configured to allow for immediate use of 
[Bootstrap](https://getbootstrap.com/docs/4.3/getting-started/introduction/),
[bootstrap-toggle](https://www.bootstraptoggle.com/), and
[jQuery](https://api.jquery.com/)

Also comes starts off with Header and Footer partials that autoload on all 
pages, ready to be customized.

### Model Configuration

To track session-specific server-side (including FHIR server connection via 
the [FHIR::Client gem](https://github.com/fhir-crucible/fhir_client) and 
session-based storage using Rails.cache), this boilerplate is configured to 
use it's own custom 
[SessionHandler](http://htmlpreview.github.io/?https://github.com/paciowg/base-fhir-client-rails/blob/master/doc/SessionHandler.html)

### Running

Since this base app is configured for heroku deployment, running it is 
slightly more effort than just `rails s`.

1. To start, you must be running `postgres`

    ```
    pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start
    ```
    (This gets old. Personally, I made a `pg_start` alias for this command)

2. Next, run the rails app the way you would any other

    ```
    cd ~/path/to/your/app/
    rails s
    ```

3. Now you should be able to see it up and running at `localhost:3000`

4. When done, gracefully stop your `puma` server

    ```
    Control-C
    ```

5. Finally, stop your `postgres` instance

    ```
    pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log stop
    ```
    (This also gets old. Personally, I made a `pg_stop` alias for this command)

## Installation

If you intend on building off of this project, please fork the 
`base-fhir-client-rails` repo and go from there. However, if you intend on 
furthering development of this base project, follow the below instructions.

To pull in remote `base-fhir-client-rails` from github for local development:

```
cd ~/path/to/your/workspace/
git clone https://github.com/paciowg/base-fhir-client-rails
```

## Copyright

Copyright 2019 The MITRE Corporation
