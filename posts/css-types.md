---
title: "CSS modules vs styled-components in React js"
date: "2022-08-07"
---

### CSS modules

There are different ways in which a React js page can be styled using CSS. One of them is CSS modules. The disadvantage of using normal CSS is that, once a style is defined, it can be used globally by any component. CSS modules overcomes this issue by keeping the style scope to local by default.

> This means that the defined styles can only be used by importing the module.css file into the component.

#### Implementation

If there is file called `layout.js`, it's CSS should be defined in a file called `layout.module.css`. Then this file should be imported inside the layout.js file as shown below -

---

```{javascript}
...
import styles from './layout.module.css'
...

const Layout = () => {
    return (
        <div className={styles.container}>
        ...
        </div>
    )
}
...

```

---

### Styled components

```

```
