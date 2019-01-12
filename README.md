# React Native Github Markdown

Generate GitHub Flavored Markdown (with syntax highlight) using React Native WebView

## Features

- Render GitHub Flavored Markdown on your React Native WebView.

- Auto-height WebView adjusted to the document.

- Code syntax highlighting.

## Caveats

- Tested with Expo, i.e. WebView module shipped with React Native core. It should also work well with [react-native-webview](https://github.com/react-native-community/react-native-webview) though, as long as you substitute it for the old one (pull requests welcomed).

- Code syntax highlighting seems odd for long code snippets. It's a problem with `highlight.js`. You can choose to disable it using `highlight` prop.

## Usage

```jsx
import MarkdownWebView from "react-native-github-markdown";

<MarkdownWebView
  style={{ marginTop: 10 }}
  content={"# React Native Github Markdown\n\nHello world!"}
  highlight={false}
/>;
```

## Props

- `WebViewProps` same as [{ WebView } from "react-native"](https://facebook.github.io/react-native/docs/webview.html#props)

For `react-native-webview-autoheight`

- `autoHeight` (default: true) **disable it if you don't want auto-height**
- `width` (default: Screen width)
- `defaultHeight` (default height unless autoHeight)

For Markdown

- `content` raw markdown content to render
- `highlight` whether to use `highlight.js` for syntax highlighting

## Behind the scene

- Markdown generated by [marked](https://github.com/markedjs/marked) and use [DOMPurify](https://github.com/cure53/DOMPurify) for sanitizing

- Syntax highlighted by [highlight.js](https://github.com/highlightjs/highlight.js)

- CSS from GitHub's [Primer](https://github.com/primer/primer) and `highlight.js`

- WebView auto-height supported by [react-native-webview-autoheight](https://github.com/scazzy/react-native-webview-autoheight)
