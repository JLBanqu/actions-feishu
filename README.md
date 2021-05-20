# actions-feishu

[![Lint](https://github.com/xiachufang/actions-feishu/actions/workflows/lint.yml/badge.svg)](https://github.com/xiachufang/actions-feishu/actions/workflows/lint.yml)
[![build-test](https://github.com/xiachufang/actions-feishu/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/xiachufang/actions-feishu/actions/workflows/test.yml)

通过 GitHub Actions 来发送消息到飞书

# Quick start

Actions 配置样例：

```yaml
    - name: feishu notify
      uses: xiachufang/actions-feishu@v1.3
      with:
        webhook: ${{ secrets.FEISHU_WEBHOOK }}
        title: I'm title
        content: |
          I'm message body

          from: ${{ github.repository }}

```

更多示范例子见: [test.yml](./.github/workflows/test.yml)

# Configuration

## Inputs

| Variable | Required | Description |
| :---: | :---: | :----: |
| `webhook`| **true** | webhook address |
| `title` | **false** | title of message|
| `content` | **true** | content of message|
| `message_type`| **false**| message type, optional: `post`, `text`, `template`, default: `post`|
| `msg_template_path`| **false**| message template path, only work when `message_type` is `template`|
| `msg_template_values`| **false**| message template fillings, , only work when `message_type` is `template`|

详细定义见: [action.yml](./action.yml)

## Outputs

| Variable  | Description |
| :---:  | :----: |
| `response` | API response from feishu |
