---
title: Javascript component
toc: true
date: 2020-02-19 17:36:35
tags:
  - lit-element
  - javascript
  - component
categories:
  - component
  - lit-element
  - javascript
---

## Javascript 형식 컴포넌트 기본적인 구조

```js
import { LitElement, html } from 'lit-element';

export class MyElement extends LitElement {
  render() {
    return html`
      <p>My First JavaScript lit-element-component.</p>
    `; // ``백틱 사이에 html형식으로 리턴함
  }
}

customElements.define('my-element', MyElement); // 컴포넌트 이름 : <my-element>
```

### 내가 만든 컴포넌트 사용법(import)

#### 1. HTML

```html
<head>
  <script type="module" src="./my-element.js"></script>
  <!-- src="해당 컴포넌트 주소(위치)" -->
</head>
<body>
  <my-element></my-element>
</body>
```

#### 2. Javascript

```js
import './my-element1.js'; // ''사이 해당 컴포넌트 위치

---
  render() {
    return html`
      <my-element1></my-element1>
    `;
  }
```

------

### 다른 사람의 컴포넌트(third-party) 사용법

대부분의 경우 npm을 통해 다운받을 수 있음

```bash
cd my-project-folder # 현재 작업폴더로 이동
npm install package-name  # 해당 컴포넌트가 들어있는 패키지 인스톨
```

### 1. HTML

```html
<head>
  <script type="module" src="node_modules/package-name/existing-element.js"></script> <!-- 해당 컴포넌트 위치 -->
</head>
<body>
  <existing-element></existing-element>
</body>
```

### 2. Javascript

```js
import 'package-name/existing-element.js'; // 해당 컴포넌트 위치

class MyElement extends LitElement{
  render(){
    return html`
      <existing-element></existing-element>
    `;
  }
}
customElements.define('my-element', MyElement);
```

저녁 뭐먹을

2트