# WorkFlowDemo

## Github Workflow 的使用方法

- blank.yml是一个yml文件，包含了指定操作系统平台，以及在一个runner上需要进行的行为。

```yml
# This is a basic workflow to help you get started with Actions

name: CI

# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but only for the main branch
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v2

      # Runs a single command using the runners shell
      - name: Run a one-line script
        run: echo Hello, world!

      # Runs a set of commands using the runners shell
      - name: Run a multi-line script
        run: |
          echo Add other actions to build,
          echo test, and deploy your project.
```

## 分步解析

```yml
# This is a basic workflow to help you get started with Actions

name: CI
```
- 这一步是指定Github Action使用CI框架, 进行持续集成的操作


```yml
# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but only for the main branch
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:
```
这一部分针对的是Github Repositiory的push以及pr操作, `on`表明如果在对应的branch发生了上述操作，就触发整个工作流的执行;
最后的`workflow_dispatch`是什么? 看起来好像是不需要人工点击这个Action Tab就能够重复进行操作.


