# Sourcemap failure on Chrome for Vue 2 components with CSS


## Describe the bug

When `css.devSourcemap` is false or unset, Chrome fails to display the mapped source for Vue 2 single file components (SFC) that contain CSS. Note that Safari works as expected.

Some limitation in Chrome? since the template, the javascript, and the CSS are served separately, it seems that Chrome defaults to showing the CSS.

As a workaround, either:
- Enable`css.devSourcemap` does resolve the problem for Chrome art the cost of a larger payload.
- Do not declare CSS in SFC. 


## Repo steps

1. Download and execute the sample app
```
git clone git@github.com:jf-paradis/demo-vite-issues.git
cd demo-vite-issues
npm install
npm run dev
```

2. Open Chrome at the URL specified by Vite.
3. Open DevTools and reload the page: the code will stop at a debugger statement.

### Expected resutls

The source code shows and the debugger stopped at the debugger statement.

### Actual results

The source code is not shown (the file is blank ecept for CSS).

