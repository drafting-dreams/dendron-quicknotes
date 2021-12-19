---
id: 9e90g0bzgpz6QvRuG0HOh
title: Stylelint
desc: ''
updated: 1639899083095
created: 1639898599197
---

1.  Webpack 配置读取 scss 文件的 loader 时，使用了一个 loader chain。sass-loader 的结果输入到 postcss-loader 的时候会将样式文件中的单引号变成双引号，而 postcss 中会做 stylelint 的处理，我们可以配置 stylelint 的规则’string-quotes’: ‘single’/’double’。为了适配 sass-loader 传出的结果，我们不得不将 lint 规则改为 double，此时如果使用了 vscode 的自动格式化功能，而 prettier 的 singlequotes 设置为 true，则格式化的时候会先变成双引号再变成单引号。为了解决这个问题，我们需要使得 prettier 对于不同的文件后缀使用不同的策略。于是就有了下面这样的配置方式。

    _prettierrc.json_

    ```js
    {
    	"singleQuote": true,
    	"overrides": [
    		{
    		"files": ["**/*.css", "**/*.scss", "**/*.html"],
    		"options": { "singleQuote": false }
    		}
    	]
    }

    ```
