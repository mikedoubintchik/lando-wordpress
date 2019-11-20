# WordPress Lando

## 🎹 Development
👷 Setting up a development environment with Lando

Lando is Docker-based, but should make things a bit easier than most Docker setups.

* Install [Lando](https://docs.devwithlando.io/). We've tested it up to RC7.
* Clone this repository locally. If you are using Windows, make sure you've set `git` to use UNIX line endings.
* In a terminal go to the directory of the local repository clone.
* Run `lando start`.
* Wait for a few minutes for everything to begin loading. Subsequent starts will be much faster but you’ll need to give it time for the very first start.
* You should see a `BOOMSHAKALAKA!!!` line 🎉
* In the `NGINX URLS` section of the output note the third URL (it should start with `http://wordpress.lndo.site` and maybe have a port).
* If the URL is different than `http://wordpress.lndo.site`, then run: `lando wp search-replace 'http://wordpress.lndo.site' '<URL>'`
* Logs are accessible via the [lando logs](https://docs.devwithlando.io/cli/logs.html) command. If you mostly care about PHP error log, a useful command is: `lando logs -s appserver -t -f`.

⏸ Debugging PHP with XDebug
* If using Lando, configure your IDE to listen to XDebug on port 9000 and map the server's `/app/` directory to the root of this repository.

⏱ Profiling PHP with XDebug
* If using Lando, simply append `XDEBUG_PROFILE` param to either GET or POST parameters. The profiler will write to the root of this repository.

💉 Running tests:

* If using Lando you can run `lando phpunit` or `lando phpunit <php-file-with-tests>` in the main plugin directory.
* JavaScript tests: open `<URL-of-plugin-directory>/tests/test.html` in your browser.