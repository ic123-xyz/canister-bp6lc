# 文章风格规范

ic123.xyz 欢迎所有对互联网计算机 / ICP 感兴趣的朋友来参与网站的建设，一起创建最优质的内容，将 ICP 介绍给更多的用户，开发者和投资人。[所有人都可以参与编辑，无论是否开发者出身](http://ic123.xyz/docs/about/how-to-contribute/)。

在开始编辑文章之前，请先仔细阅读本文，了解 ic123.xyz 网站对文章风格的要求以及规范。

## 通用 {#general}

1. **`DFINITY`** 是唯一正确的拼写 - 七个字母都需要大写。
2. 所有的 markdown 文件名全部`小写`，不要有任何**空格**，使用 `英文`，文件名里的单词统一用 `-` 连接，不要用 `_`（在URL里看不清楚），以 `md` 为统一后缀。
3. 涉及到 ICP 的技术词汇，请参照 DFINITY 亚太团队编写的[《互联网计算机 (IC) 核心词汇表》](http:ic123.xyz/docs/getting-started/ic-glossary)。
4. ic123.xyz 网站的默认语言为`中文`，标点符号用`中文全角`。譬如，句号应该为 `。`，而不是`.`；逗号应该为`，`，而不是 `,`；括号应该为`（）` ，而不是 `()`。
5. 涉及到中英混杂的句子，如果英文单词前后都是中文单词，则在英文单词的前后各添加一个空格，这样视觉效果上更加醒目。譬如，`DFINITY 基金会的员工不会对 ICP 的价格做任何评论`，而不是 `DFINITY基金会的员工不会对ICP的价格做任何评论`。
6. 尽可能标注出所有的原文链接（特别是英文原文被翻译成中文的情况下）。
7. 尽可能地使用链接来丰富文章的内容并提升它的可信度。
8. `#` 仅仅使用在文章的开始，通常作为网站里的文章名字。在文章正文里，使用 `##` 做第一层分级，`###` 做第二层分级。除非有特殊情况，应该没有必要使用 `####`。在正文里，不要使用 `#`。
9. [Tag](https://ic123.xyz/blog/tags) 统一用小写。
10. 不需要使用 `icp`，`ic`，或者 `internet computer`, `互联网计算机` 这样的tag。整个本网站都是讲 ic 的。

## 文章原子结构 {#article-structure}

建议每篇文章按照以下的原子结构搭建，以实现所有的内容自成一体，便于迁移。

```bash
├── hello-icp-my-old-friend (文件夹)
│   ├── img （文件夹）
│   ├── index.md (文件)
```

`hello-icp-my-old-friend` 为文件夹的名字；`img` 为跟文章随行的图片资料库；`index.md` 是统一的文件名。Docusaurus 会自动地把这个网页转化为 `xxx/hello-icp-my-old-friend` （`xxx` 为上级文件夹）。这个网页的地址跟 `xxx/hello-icp-my-old-friend/`，或者 `xxx/hello-icp-my-old-friend.html` 的效果是一样的。

文章里所需要引用的所有图片，建议都放在 `img` 文件夹里，这样最方便日后的迁移。如果把图片放在另外第三方的服务器上（传统的中心化云服务 S3，区块链的 IPFS 服务，或者 ICP 网络上的其他容器）都会在日后迁移的时候造成巨大的困难，因为无法保持一一映射的关系。

在文章里引用图片，采用以下统一的公式即可，不需要再去考虑其他各种上下级文件夹路径错综复杂的写法。

```
![图片名字](./img/xxx.png)
```

![what is ic123](./img/asteroid-city.png)

如果文章里没有引用图片，可以省去文件夹的结构，直接就用 `hello-icp-my-old-friend.md` 就可以了。

## 图片格式 {#image-format}

1. 建议图片的 `width` 统一设置为 `800px` (Resolution = 72)。这样每张图片大小应该在 200-300KB 之间。图片尺寸太大的话只会增加下载的时间，降低网页调用的速度。
2. 图片可以用 `.jpg`，`jpeg`, `.png`, `.PNG` 等通用格式。

## 文章的路径 {#article-path}

每位作者需要做的第一个决定，就是文件夹（文件）应该放在哪条路径下面。

Docusaurus 的架构中，会被社区内容贡献者用到的文件夹有两个，`blog` 和 `docs`。

```bash
├── docusaurus
│   ├── .docusaurus
│   ├── blog （新闻）
│   ├── build
│   ├── docs
│       ├── about （关于ic123）
│       ├── apps-guide （应用介绍）
│       ├── dev-course （开发者教程）
│       ├── dev-resources （开发者资源）
│       ├── ecosystem-guide （生态资源）
│       ├── getting-started （新手上路）
│       ├── ic-web3 （解锁Web3）
│       ├── intro-ic （ICP介绍）
│   ├── node_modules
│   ├── src
│   ├── static
```

请在 `ic123 工作组` 里联系管理员，确认文件应该归属的路径。

## 新闻文章 (blog) {#blog-post}

如果文章是[新闻](https://ic123.xyz/blog)类型，除了遵循上述通用的文件夹原子结构以外，还需要注意几点。

1. 文件夹的命名规则遵循  `YYYY-MM-DD-my-dear-icp` 的格式，方便在 IDE 里管理文件。
2. Blog文章的文件名里包含的日期，应该是事件发生的日期，而不是文章发布的日期。文章发布的日期，在系统里可以查出来。事件发生的日期，如果不专门注明的话，就有可能永远失去了记录。
3. 文章的 `front matter` 必须得有。以此文为例，http://ic123.xyz/blog/rust-china-icp-dev-meetup-shanghai 。

    ```bash
    ---
    slug: rust-china-icp-dev-meetup-shanghai
    title: DFINITY x Rust 中国开发者大会2023
    authors: 
        -   beeling
        -   name: Frank Fang
            title: Initiator & Core @Scroll
            url: https://github.com/Junweif2
            image_url: https://avatars.githubusercontent.com/u/42843075?v=4
    image: "./img/rust-china-booth.jpg"
    tags: [rust, meetup, shanghai, tintin]
    ---
    ```
    - `slug`: 全部用`英文`。对于blog类型的文章，这个slug里定义的名字，才是最后网站的 URL 。Markdown 文件夹本身的名字 `2023-06-26-rust-china` 只是适用于本地文件的管理，不影响网页的 URL 。因为有了 `slug` 的存在，正文里不再需要用 `#` 来注明文章的题目，可以直接进入 `##` 的结构。
    - `title`:  这是文章的标题，用`中文`。
    - `authors`: 下段详述。
    - `image`: 这是文章的 social card，用在社交媒体引用时候的 preview，可以增加文章的点击率。
    - `tags`: 用方括号围起来，逗号隔开，中英文皆可。在[这里](http://ic123.xyz/blog/tags)看全部现有的标签。
    - `front matter` 的上下用 `---` 分隔开
4.  作者 authors 有两类，临时作者和长期作者。
    - 临时作者的格式
        ```bash
        name: xiao wang
        title: Founder of Joyland
        url: url-for-social-media
        image_url: url-for-avatar-image
        ```    
    - 长期作者，在 `authors.yml` 这个文件里添加 `wang` 的字条，以后直接引用 `wang` 即可。
        
        ```bash
        wang:
            name: xiao wang
            title: Founder of Joyland
            url: url-for-social-media
            image_url: url-for-avatar-image
    - 对于 blog 类型文章，Docusaurus使用 `authors` 来开篇明义地展示作者。文章实际的编辑者（提交最后 PR 的人）不会被视作文章作者。
5. 每篇文章都必须添加文章的 summary ，否则[新闻](http://ic123.xyz/blog)无法展示所有的博客文章的索引。假设 `blog`下有一百篇文章，只要有一篇文章没有使用 `<!--truncate-->`，就会打乱整个 `blog` 的索引呈现。

    用 `<!--truncate-->` 来隔断 summary 跟正文的内容。所有放在 `<!--truncate-->` 的文字，包括图片，将被展示在新闻的索引页面上。Summary 通常一句话介绍一下文章的主要内容就行。

    **请注意**：`<!--truncate-->` 之前不要有空格。请不要写成` <!--truncate-->`，否则 `Docusaurus` 构建会失败。

6. 因为文章的标题已经在 front matter 里被 `title` 所定义，在文章正文里就不再需要使用 `#` 来定义文章的标题了，直接使用 `##` 来分级就可以了。
7. 整篇文章在 commit 的时候，最重要的是 `slug`，因为它决定了文章的 URL 以及后续的 SEO (搜索引擎的搜索效率)。文章的其他部分都可以在初始 commit 之后继续更改而不影响文章在互联网和社交媒体上的有效传播。


## 非新闻文章 (docs) {#docs}

非新闻类/docs 的文章会稍微简单一些。除了依旧遵循上述的文件夹原子结构以外，还需要注意几点。

1. 文件夹的名字遵循 `x-my-dear-icp`。`x` 为阿拉伯数字序列号，方便在 IDE 里管理本地文件。网页相对应的 URL 为 `docs/yyy/my-dear-icp`。`yyy` 为 `docs/` 下选择的合适的文件夹。`x` 会被 Docusaurus 自动忽略，直接摘取后续的名字。
2. 文章的标题在 `index.md` 文件第一行用 `#` 标明，然后就可以进入 `##` 的正文结构了。不需要 `front matter`，也不需要 `<!--truncate-->`。
3. 文章的作者将直接在网页下方显示（包括时间戳），按照最后递交 PR ，被 merge 了的 commit 作者为准。
4. 整篇文章在 commit 的时候，最重要的是 `my-dear-icp` 部分，因为它决定了文章的 URL 以及后续的 SEO (搜索引擎的搜索效率)。文章的其他部分都可以在初始 commit 之后继续更改而不影响文章在互联网和社交媒体上的有效传播。

## Markdown 文本编辑功能 {#markdown-features}

下面介绍一些在 Docusaurus 中常用的 Markdown 文本编辑功能。

### 如何生成英文内链 {#enlish-heading-id}

Docusaurus 默认会为中文标题生成中文的标题 ID，这样会使得生成类似如下所示的链接。

`https://ic123.xyz/docs/about/styling-guide/#%E9%80%9A%E7%94%A8 `

这样的链接可读性并不好，如果您觉得您的标题可能会被单独链接，推荐使用自定义的标题 ID，如下所示。

`### account: 账号 {#account}`

这样 Docusaurus 会为您生成如下所示的链接。

`https://ic123.xyz/docs/getting-started/ic-glossary/#account`

具体代码请参考 [GitHub](https://github.com/ic123-xyz/ic123/blob/main/docusaurus/docs/getting-started/4-ic-glossary/index.md?plain=1#L5) 。

更多信息，请参考 [Docusaurus 官方文档](https://docusaurus.io/docs/markdown-features/toc#heading-ids)。

请注意：
1. 不要使用重复的标题 ID，会产生冲突。
2. 该功能 GitHub 并不支持，所以您在 GitHub 的预览页面该功能并不会启用。

### 如何修改目录层级 {#headings-of-toc}

Docusaurus 默认会在文档右侧的目录栏包含三级、及三级以上的标题。如果您需要支持到四级、甚至四级以上的目录结构，请按一下方式配置。

在您的文档的前文使用 `toc_min_heading_level` 和 `toc_max_heading_level` 来定义目录所包含的最小和最大标题级别，如下所示。

```
---
# 显示 h2 到 h5 标题
toc_min_heading_level: 2
toc_max_heading_level: 5
---
```

具体的示例请参考[注册互联网身份](https://ic123.xyz/docs/ic-web3/internet-identity/)。对应的代码示例请参考 [GitHub](https://github.com/ic123-xyz/ic123/blob/main/docusaurus/docs/ic-web3/1-internet-identity/index.md?plain=1#L1)。

更多信息，请参考 [Docusaurus 官方文档](https://docusaurus.io/docs/markdown-features/toc#table-of-contents-heading-level)。
