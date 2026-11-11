# Txlemetry PHP 5 candidate

The package is `txlemetry/txlemetry-php`, with public classes under `Txlemetry\`. Import the static client with `use Txlemetry\Txlemetry;`. The default collector is `app.txlemetry.com`.

`TXLEMETRY_API_KEY` and `TXLEMETRY_HOST` take precedence over the historical `POSTHOG_API_KEY` and `POSTHOG_HOST` fallbacks. Existing applications can keep their environment configuration while changing imports and package coordinates.

The public API snapshot was checked against the upstream 4.14.2 shape after the explicit namespace, version, environment-constant and default-host changes. This is an API shape check; full behavior and installation validation are still required.

The upstream distribution archive omits tests and their configuration through `.gitattributes`. The maintained source tree restores them from the same pinned Git commit, with Git blob hashes recorded in `docs/internal/txlemetry-php-test-source-recovery.json` in the project repository. Release archives continue excluding development files.

Use an installed Composer executable and run `composer install`, then `make lint`, `make api-check` and `make test` as appropriate. Lint no longer changes dependency declarations and clean preserves composer.lock. The Docker target opens an interpreter shell; its required extensions and Composer must be prepared before running development commands.

The consumer minimum remains PHP 8.2. The development PHPUnit 11 dependency requires a newer PHP runtime, and the current lock was resolved with PHP 8.4.26. The minimum-runtime and supported-platform matrix, actual tests, artifact checks and public distribution remain release gates. No candidate has been published.
