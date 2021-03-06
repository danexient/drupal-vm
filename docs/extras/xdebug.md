[XDebug](https://xdebug.org/) is a useful tool for debugging PHP applications, but it uses extra memory and CPU for every request, so is disabled by default.

To enable XDebug, do the following in `config.yml`:

  - Change `php_xdebug_default_enable` (and, optionally, `php_xdebug_coverage_enable` to get code coverage reports) to `1`
  - Make sure `xdebug` is in the list of `installed_extras`

If you don't need to use XDebug, you can comment it out or remove it from `installed_extras` before you `vagrant up` Drupal VM.

### PHPStorm and XDebug with Drupal VM

To use XDebug with PHPStorm, change the `php_xdebug_idekey` variable as shown below in `config.yml`, and then run `vagrant provision` to reconfigure the VM:

```yaml
php_xdebug_idekey: PHPSTORM
```

### Sublime Text and XDebug with Drupal VM

To use XDebug with Sublime Text, change the `php_xdebug_idekey` variable as shown below in `config.yml`, and then run `vagrant provision` to reconfigure the VM:

```yaml
php_xdebug_idekey: sublime.xdebug
```

### NetBeans and XDebug with Drupal VM

To use XDebug with NetBeans, change the `php_xdebug_idekey` variable as shown below in `config.yml`, and then run `vagrant provision` to reconfigure the VM.

```yaml
php_xdebug_idekey: netbeans-xdebug
```

## Profiling code with XDebug

While most people use XDebug only for debugging purposes, you can also use it for profiling. It's not as commonly used for profiling as either Blackfire or XHProf, but it works!

**Note**: You should only enable one code profiler at a time—e.g. when using [Blackfire](blackfire.md), disable [XHProf](xhprof.md), [Tideways](tideways.md) and [XDebug](xdebug.md).

For a list of available role variables, see the [`geerlingguy.php-xdebug` Ansible role's README](https://github.com/geerlingguy/ansible-role-php-xdebug#readme).
