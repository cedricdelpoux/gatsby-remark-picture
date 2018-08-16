# gatsby-remark-picture

[![npm package][npm-badge]][npm]

## Features

-   Wrap images by a `<picture>` tag.
-   Make remark images reponsives by generating differents sizes
-   Add a `<source>` tag with `srcset`, `sizes` and `type` attributes.

### With `gatsby-remark-picture`

```md
Hello Word!

![](image.jpg)
```

The previous markdown will generate the following DOM:

```html
<div>
  <p>Hello Word!</p>
  <picture>
    <!-- With "withWebp: true" option -->
    <source
      srcset="
        /static/image-e5090913465832b3ea4cd5728e0970b2-0a74b.webp 200w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-4de56.webp 400w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-d9af4.webp 800w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-6c443.webp 1200w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-4010f.webp 1600w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-17ee1.webp 2400w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-64024.webp 4240w
      "
      sizes="(max-width: 800px) 100vw, 800px"
      type="image/jpeg"
    >
    <!-- With "withSource: true" option -->
    <source
      srcset="
        /static/image-e5090913465832b3ea4cd5728e0970b2-0a74b.jpg 200w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-4de56.jpg 400w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-d9af4.jpg 800w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-6c443.jpg 1200w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-4010f.jpg 1600w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-17ee1.jpg 2400w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-64024.jpg 4240w
      "
      sizes="(max-width: 800px) 100vw, 800px"
      type="image/jpeg"
    >
    <img
      srcset="
        /static/image-e5090913465832b3ea4cd5728e0970b2-0a74b.jpg 200w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-4de56.jpg 400w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-d9af4.jpg 800w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-6c443.jpg 1200w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-4010f.jpg 1600w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-17ee1.jpg 2400w,
        /static/image-e5090913465832b3ea4cd5728e0970b2-64024.jpg 4240w
      "
      src="/static/image-e5090913465832b3ea4cd5728e0970b2-d9af4.jpg"
    >
  </picture>
</div>
```

> Note: To remove the paragraph tag wrapping the `picture` tag, you can use [gatsby-remark-unwrap-images](https://github.com/xuopled/gatsby-remark-unwrap-images) plugin before `gatsby-remark-picture`

### Without `gatsby-remark-picture`

```md
Hello Word!

![](image.jpg)
```

The previous markdown will generate the following DOM:

```html
<div>
  <p>Hello Word!</p>
  <p>
    <img src="image.jpg" />
  </p>
</div>
```

## Getting started

[![gatsby-remark-picture](https://nodei.co/npm/gatsby-remark-picture.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/gatsby-remark-picture/)

You can download `gatsby-remark-picture` from the NPM registry via the
`npm` or `yarn` commands

```shell
yarn add gatsby-remark-picture
npm install gatsby-remark-picture --save
```

## Usage

Add the plugin in your `gatsby-config.js` file:

```js
module.exports = {
    plugins: [
        {
            resolve: "gatsby-transformer-remark",
            options: {
                plugins: [
                    // Optional: Remove the paragraph tag wrapping images
                    "gatsby-remark-unwrap-images",
                    // Wrap images by pictures
                    "gatsby-remark-picture",
                ],
            },
        },
    ],
}
```

## Props

| Name           | PropType | Description                                        | Default | Example             |
| -------------- | -------- | -------------------------------------------------- | ------- | ------------------- |
| className      | string   | Add custom className                               | -       | "myCustomClassName" |
| withSource     | boolean  | Add a `<source>` tag with responsives images       | false   | true                |
| withSourceWebp | boolean  | Add a `<source>` tag with responsives .webp images | false   | true                |

## Contributing

-   ⇄ Pull/Merge requests and ★ Stars are always welcome.
-   For bugs and feature requests, please [create an issue][github-issue].

See [CONTRIBUTING.md](./CONTRIBUTING.md) guidelines

## Changelog

See [CHANGELOG.md](./CHANGELOG.md)

## License

This project is licensed under the MIT License - see the
[LICENCE.md](./LICENCE.md) file for details

[npm-badge]: https://img.shields.io/npm/v/gatsby-remark-picture.svg?style=flat-square
[npm]: https://www.npmjs.org/package/gatsby-remark-picture
[github-issue]: https://github.com/xuopled/gatsby-remark-picture/issues/new
