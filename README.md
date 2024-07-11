# Codeception for VSCode

Run your Codeception tests using the Test Explorer UI.

## Features

- Shows a Test Explorer in the Test view in VS Code's sidebar with all detected tests and suites and their state
- Shows a failed test's log when the test is selected in the explorer
- Lets you choose test suites or individual tests in the explorer that should be run automatically after each file
  change

## Extension Settings

This extension contributes the following settings:

- `codeception.codeception`: Absolute path to php. Fallback to global php if it exists on the command line.
- `codeception.phpunit`: Path to codeception. 
- `codeception.command`: Custom command to run. Ex: `docker exec -t container_name`.
- `codeception.args`: Any codeception args (codeception --help)
- `codeception.clearOutputOnRun`: True will clear the output when we run a new test. False will leave the output after every
  test.
- `codeception.showAfterExecution` Specify if the test report will automatically be shown after execution

## Commands

The following commands are available in VS Code's command palette, use the ID to add them to your keyboard shortcuts:

- `codeception.reload`: codeception: Reload tests
- `codeception.run-all`: codeception: Run all tests
- `codeception.run-file`: codeception: Run tests in current file
- `codeception.run-test-at-cursor`: codeception: Run the test at the current cursor position
- `codeception.rerun`: codeception: Repeat the last test run

## Configuration

### Docker

```jsonc
{
  "codeception.command": "docker exec -t docker-php-fpm-1 /bin/bash -c",
  "codeception.codecept": "vendor/bin/codecept",
  "codeception.args": [
  ],
  "codeception.paths": {
      // ${pwd} (current directory) is mounted to /app
      "${workspaceFolder}": "/var/www/html",
      // ${workspaceFolder} is mapped to /app
  },
}
```