# Commit Message Lint 2.0

## Configuration
You would need to add a configuration folder named .github at the root of your repository. The folder should contain a file named config.yml. This file will serve as the configuration and the contents of that file will be:
```
PR_TITLE_REGEX: <PR Title Regex>
COMMIT_MESSAGE_REGEX: <Commit Message Regex>
```
## Usage

Go to the checks section on your PR to see the result of the check run performed by the app. It will show you the result as well as the commit messages which failed.

If a developer does not adhere to the format, the check section of PR will show failure for this app. Then the reviewer can take the decision on whether to merge the PR or not.

If the app is not configured and the config.yml file is not provided, the app will mark the check as success but the message will show that the file is not configured.

The idea is to enforce developers to follow a specific format for their commit messages and PR title, so that there is consistency. Also, this allows organisations to integrate other tools which function by extracting information out of the commit messages.



## Example
```
PR_TITLE_REGEX: /((?:[a-z][a-z]+))(\d{3})(:)([a-z0-9])/i
COMMIT_MESSAGE_REGEX: /(#)(#)((?:[a-z][a-z]+))(\d{3})(:)([a-z0-9])/i
```

For above regex, the corresponding valid messages would be:
```
PR Title message - JIR123:login feature

Commit message - ##JIR302:login feature
```


Reference: [Commit-Message-Lint](https://github.com/SystangoTechnologies/commit-message-lint/wiki/Commit-Message-Lint---2.0)
