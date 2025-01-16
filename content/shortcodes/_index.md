+++
date = '2025-01-15T11:06:37-07:00'
draft = false
title = 'Shortcodes'
+++
Here are examples of the shortcodes

## Badge

Code:
```
{{</* badge "Badge" */>}}
```
Output:
{{< badge "Badge" >}}

Variants:

```
{{</* badge content="info" type="info" */>}}
{{</* badge content="warning" type="warning" */>}}
{{</* badge content="error" type="error" */>}}
```

Result:

{{< badge content="info" type="info" >}} &nbsp;
{{< badge content="warning" type="warning" >}} &nbsp;
{{< badge content="error" type="error" >}}

With link and icon:

```
{{</* badge content="Releases" link="https://github.com/imfing/hextra/releases" icon="github" */>}}
```

Result:

{{< badge content="Releases" link="https://github.com/imfing/hextra/releases" icon="github" >}}

## YouTube

Embed a YouTube video.

```
{{</* youtube VIDEO_ID */>}}
```

Result:

{{< youtube id=dQw4w9WgXcQ loading=lazy >}}

For more information, see [Hugo's YouTube Shortcode](https://gohugo.io/content-management/shortcodes/#youtube).

## PDF

With PDF shortcode, you can embed a PDF file in your content.

```
{{</* pdf "https://example.com/sample.pdf" */>}}
```

You can also place the PDF file in your project directory and use the relative path.

```
{{</* pdf "path/to/file.pdf" */>}}
```

Example:

{{< pdf "https://upload.wikimedia.org/wikipedia/commons/1/13/Example.pdf" >}}

## Callout

{{< callout emoji="👾">}}
  A **callout** is a short piece of text intended to attract attention.
{{< /callout >}}

{{< callout type="info" >}}
  A **callout** is a short piece of text intended to attract attention.
{{< /callout >}}

{{< callout type="warning" >}}
  A **callout** is a short piece of text intended to attract attention.
{{< /callout >}}

{{< callout type="error" >}}
  A **callout** is a short piece of text intended to attract attention.
{{< /callout >}}

### Default

{{< callout emoji="🌐">}}
  Hugo can be used to create a wide variety of websites, including blogs, portfolios, documentation sites, and more.
{{< /callout >}}

```markdown
{{</* callout emoji="🌐" */>}}
  Hugo can be used to create a wide variety of websites, including blogs, portfolios, documentation sites, and more.
{{</* /callout */>}}
```

### Info

{{< callout type="info" >}}
  Please visit GitHub to see the latest releases.
{{< /callout >}}

```markdown
{{</* callout type="info" */>}}
  Please visit GitHub to see the latest releases.
{{</* /callout */>}}
```

### Warning

{{< callout type="warning" >}}
  This API will be deprecated in the next version.
{{< /callout >}}

```markdown
{{</* callout type="warning" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

### Error

{{< callout type="error" >}}
  Something went wrong and it's going to explode.
{{< /callout >}}

```markdown
{{</* callout type="error" */>}}
  Something went wrong and it's going to explode.
{{</* /callout */>}}
```

## Cards

{{< cards >}}
  {{< card link="../callout" title="Callout" icon="warning" >}}
  {{< card link="../callout" title="Card with tag" icon="tag" tag="custom tag">}}
  {{< card link="/" title="No Icon" >}}
{{< /cards >}}

{{< cards >}}
  {{< card link="/" title="Image Card" image="https://github.com/user-attachments/assets/71b7e3ec-1a8d-4582-b600-5425c6cc0407" subtitle="Internet Image" >}}
  {{< card link="/" title="Local Image" image="/images/card-image-unprocessed.jpg" subtitle="Raw image under static directory." >}}
  {{< card link="/" title="Local Image" image="images/space.jpg" subtitle="Image under assets directory, processed by Hugo." method="Resize" options="600x q80 webp" >}}
{{< /cards >}}

```
{{</* cards */>}}
  {{</* card link="../callout" title="Callout" icon="warning" */>}}
  {{</* card link="../callout" title="Card with tag" icon="tag" tag= "A custom tag" */>}}
  {{</* card link="/" title="No Icon" */>}}
{{</* /cards */>}}
```

```
{{</* cards */>}}
  {{</* card link="/" title="Image Card" image="https://source.unsplash.com/featured/800x600?landscape" subtitle="Unsplash Landscape" */>}}
  {{</* card link="/" title="Local Image" image="/images/card-image-unprocessed.jpg" subtitle="Raw image under static directory." */>}}
  {{</* card link="/" title="Local Image" image="images/space.jpg" subtitle="Image under assets directory, processed by Hugo." method="Resize" options="600x q80 webp" */>}}
{{</* /cards */>}}
```

### Card Parameters

| Parameter  | Description                                                     |
|----------- |-----------------------------------------------------------------|
| `link`     | URL (internal or external).                                     |
| `title`    | Title heading for the card.                                     |
| `subtitle` | Subtitle heading (supports Markdown).                           |
| `icon`     | Name of the icon.                                               |
| `tag`      | Text in tag.                                                    |
| `tagColor` | Color of the tag: `gray` (default), `yellow`, `red` and `blue`. |
  
### Image Card

Additionally, the card supports adding image and processing through these parameters:

| Parameter  | Description                                 |
|----------- |---------------------------------------------|
| `image`    | Specifies the image URL for the card.       |
| `method`   | Sets Hugo's image processing method.        |
| `options`  | Configures Hugo's image processing options. |

Card supports three kinds of images:

1. Remote image: the full URL in the `image` parameter.
2. Static image: use the relative path in Hugo's `static/` directory.
3. Processed image: use the relative path in Hugo's `assets/` directory.

Hextra auto-detects if image processing is needed during build and applies the `options` parameter or default settings (Resize, 800x, Quality 80, WebP Format).
It currently supports these `method`: `Resize`, `Fit`, `Fill` and `Crop`.

For more on Hugo's built in image processing commands, methods, and options see their [Image Processing Documentation](https://gohugo.io/content-management/image-processing/).

### Tags

Card supports adding tags which could be useful to show extra status information.

{{< cards >}}
  {{< card link="../callout" title="Card with default tag" tag="tag text" >}}
  {{< card link="../callout" title="Card with error tag" tag="tag text" tagType="error" >}}
  {{< card link="../callout" title="Card with info tag" tag="tag text" tagType="info" >}}
  {{< card link="../callout" title="Card with warning tag" tag="tag text" tagType="warning" >}}
  {{< card link="/" title="Image Card" image="https://github.com/user-attachments/assets/71b7e3ec-1a8d-4582-b600-5425c6cc0407" subtitle="Internet Image" tag="tag text" tagType="error" >}}
{{< /cards >}}

```
{{</* cards */>}}
  {{</* card link="../callout" title="Card with default tag color" tag="tag text" */>}}
  {{</* card link="../callout" title="Card with default red tag" tag="tag text" tagType="error" */>}}
  {{</* card link="../callout" title="Card with blue tag" tag="tag text" tagType="info" */>}}
  {{</* card link="../callout" title="Card with yellow tag" tag="tag text" tagType="warning" */>}}
{{</* /cards */>}}
```

### Columns

You can specify the maximum number of columns for cards to span by passing the `cols` parameter to the `cards` shortcode. Note that columns will still be collapsed on smaller screens.

{{< cards cols="1" >}}
  {{< card link="/" title="Top Card" >}}
  {{< card link="/" title="Bottom Card" >}}
{{< /cards >}}

{{< cards cols="2" >}}
  {{< card link="/" title="Left Card" >}}
  {{< card link="/" title="Right Card" >}}
{{< /cards >}}

```
{{</* cards cols="1" */>}}
  {{</* card link="/" title="Top Card" */>}}
  {{</* card link="/" title="Bottom Card" */>}}
{{</* /cards */>}}

{{</* cards cols="2" */>}}
  {{</* card link="/" title="Left Card" */>}}
  {{</* card link="/" title="Right Card" */>}}
{{</* /cards */>}}
```

## Details

A built-in component to display a collapsible content.

{{< details title="Details" >}}
<p>This is an HTML paragraph added to the Markdown file.</p>
{{< /details >}}

{{< details title="Click me to reveal" closed="true" >}}

This will be hidden by default.

{{< /details >}}

### Usage

````markdown
{{</* details title="Details" */>}}

This is the content of the details.

Markdown is **supported**.

{{</* /details */>}}
````

````markdown
{{</* details title="Click me to reveal" closed="true" */>}}

This will be hidden by default.

{{</* /details */>}}
````

## File Tree

{{< filetree/container >}}
  {{< filetree/folder name="content" >}}
    {{< filetree/file name="_index.md" >}}
    {{< filetree/folder name="docs" state="closed" >}}
      {{< filetree/file name="_index.md" >}}
      {{< filetree/file name="introduction.md" >}}
      {{< filetree/file name="introduction.fr.md" >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
  {{< filetree/file name="hugo.toml" >}}
{{< /filetree/container >}}

### Usage

```text {filename="Markdown"}
{{</* filetree/container */>}}
  {{</* filetree/folder name="content" */>}}
    {{</* filetree/file name="_index.md" */>}}
    {{</* filetree/folder name="docs" state="closed" */>}}
      {{</* filetree/file name="_index.md" */>}}
      {{</* filetree/file name="introduction.md" */>}}
      {{</* filetree/file name="introduction.fr.md" */>}}
    {{</* /filetree/folder */>}}
  {{</* /filetree/folder */>}}
  {{</* filetree/file name="hugo.toml" */>}}
{{</* /filetree/container */>}}
```

## Icons

To use this shortcode inline, inline shortcode needs to be enabled in the config:

```yaml {filename="hugo.yaml"}
enableInlineShortcodes: true
```

List of available icons can be found in [`data/icons.yaml`](https://github.com/imfing/hextra/blob/main/data/icons.yaml).

{{< icon "academic-cap" >}}
{{< icon "cake" >}}
{{< icon "gift" >}}
{{< icon "sparkles" >}}

### Usage

```
{{</* icon "github" */>}}
```

[Heroicons](https://v1.heroicons.com/) v1 outline icons are available out of the box.

### How to add your own icons

Create `data/icons.yaml` file, then add your own SVG icons in the following format:

```yaml {filename="data/icons.yaml"}
your-icon: <svg>your icon svg content</svg>
```

It then can be used in the shortcode like this:

```
{{</* icon "your-icon" */>}}

{{</* card icon="your-icon" */>}}
```

Tip: [Iconify Design](https://iconify.design/) is a great place to find SVG icons for your site.

## Tabs

{{< tabs items="JSON,YAML,TOML" >}}

{{< tab >}}<strong>JSON</strong>: JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax.{{< /tab >}}
{{< tab >}}<strong>YAML</strong>: YAML is a human-readable data serialization language.{{< /tab >}}
{{< tab >}}<strong>TOML</strong>: TOML aims to be a minimal configuration file format that's easy to read due to obvious semantics.{{< /tab >}}

{{< /tabs >}}

### Default

```
{{</* tabs items="JSON,YAML,TOML" */>}}

  {{</* tab */>}}<strong>JSON</strong>: JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax.{{</* /tab */>}}
  {{</* tab */>}}<strong>YAML</strong>: YAML is a human-readable data serialization language.{{</* /tab */>}}
  {{</* tab */>}}<strong>TOML</strong>: TOML aims to be a minimal configuration file format that's easy to read due to obvious semantics.{{</* /tab */>}}

{{</* /tabs */>}}
```

### Specify Selected Index

Use `defaultIndex` property to specify the selected tab. The index starts from 0.

```
{{</* tabs items="JSON,YAML,TOML" defaultIndex="1" */>}}

  {{</* tab */>}}<strong>JSON</strong>: JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax.{{</* /tab */>}}
  {{</* tab */>}}<strong>YAML</strong>: YAML is a human-readable data serialization language.{{</* /tab */>}}
  {{</* tab */>}}<strong>TOML</strong>: TOML aims to be a minimal configuration file format that's easy to read due to obvious semantics.{{</* /tab */>}}

{{</* /tabs */>}}
```

The `YAML` tab will be selected by default.

{{< tabs items="JSON,YAML,TOML" defaultIndex="1" >}}

{{< tab >}}<strong>JSON</strong>: JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax.{{< /tab >}}
{{< tab >}}<strong>YAML</strong>: YAML is a human-readable data serialization language.{{< /tab >}}
{{< tab >}}<strong>TOML</strong>: TOML aims to be a minimal configuration file format that's easy to read due to obvious semantics.{{< /tab >}}

{{< /tabs >}}

