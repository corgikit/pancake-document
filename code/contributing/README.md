---
description: We appreciate you showing an interest in supporting ZexdexApp!
---

# Contributing

![](../../.gitbook/images/developers-header.png)

ZexdexApp is a project that is open-source. This section is meant to help you through your initial interactions with the z-team if you wish to contribute to the project.

We strongly advise you to create an issue on Github before beginning any development so that the team can debate the issue and possible solutions.

## Setup your dev environment

Install [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) If you haven't.

1.  Fork and clone the [repository](https://github.com/zexdexecosystem/zexdex-frontend)

    ```bash
    $ git clone [fork_repo_url]
    ```

2.  Add [upstream](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork) remote. E.g.

    ```bash
    $ git remote add upstream git@github.com/zexdexecosystem/zexdex-frontend.git
    ```

3.  Make sure you have the latest version of the default branch ( `develop` )

    ```bash
    $ git checkout develop
    $ git pull upstream develop
    ```

4.  Create your own branch and install dependencies

    ```bash
    $ git checkout -b branch-name
    $ yarn
    ```

5.  Happy coding 🎉

## Coding rules

In order to keep each of our repositories as consistent as possible, we strive to do so. If you adhere to the following guidelines and provide high-quality code, your pull request will have a greater chance of being approved. **Let's get started** 💪

### Use the UIKit

{% hint style="warning" %}
Before you begin, be sure to check the [UI Kit](https://github.com/zexdexecosystem/zexdex-frontend/tree/master/packages/uikit). Many parts have already been developed, so we don't want you to waste time doing it from scratch. 😉
{% endhint %}

Use the appropriate component from the UI Kit as a foundation if a version of a component has to be produced. For example:

```javascript
import styled from "styled-components";
import { Button } from "@zexdex.app/uikit";

const NewButtonVariant = styled(Button)`
  // custom styles here
`;
```

### Use the tools!

The majority of our repositories employ [Typescript](https://www.typescriptlang.org/docs), [Prettier](https://prettier.io), and [ESLint](https://eslint.org/docs/user-guide/getting-started). Make sure you are knowledgeable about Typescript best practices and that your IDE has an ESLint and Prettier plugin enabled.

{% hint style="warning" %}
Before submitting a pull request, make sure your code is formatted using Prettier and is free of any ESLint errors.
{% endhint %}

### Some good practices

- Keep components as small and ["dumb"](https://en.wikipedia.org/wiki/Pure_function) as possible.
- Use [Composition over Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html).
- Remember that several other developers will read and maintain your code. Make it as simple to understand and update as you can._​_

## Creating your pull request

Your code is ready to be submitted for review, congratulations🥳

- All pull requests **must** have a description of what the PR is trying to accomplish.
- Keep pull requests **as small as possible**. Larger pull requests should be broken up into smaller chunks with a dedicated base branch. Please tag the PR's that are merging into your base branch with the `epic` tag.
- If possible self-review your PR and **add comments** where additional clarification is needed.

{% hint style="info" %}
Create a [draft PR](https://github.blog/2019-02-14-introducing-draft-pull-requests/) as soon as possible so we can view your ongoing progress.
{% endhint %}

### Pull Request Title

Our Pull Request Title follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) using [commitlint](https://commitlint.js.org/#/).‌

_More at_ [_Angular's guidelines_](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)\_\_

| Type         | Description                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------- |
| **build**    | Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)         |
| **ci**       | Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs) |
| **docs**     | Documentation only changes                                                                                  |
| **feat**     | A new feature                                                                                               |
| **fix**      | A bug fix                                                                                                   |
| **perf**     | A code change that improves performance                                                                     |
| **refactor** | A code change that neither fixes a bug nor adds a feature                                                   |
| **style**    | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)      |
| **test**     | Adding missing tests or correcting existing tests                                                           |

**Thanks for helping us making ZexdexApp even more awesome** ❤
