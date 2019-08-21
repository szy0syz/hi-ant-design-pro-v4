# Ant Design Pro

This project is initialized with [Ant Design Pro](https://pro.ant.design). Follow is the quick guide for how to use.

## 替换 layout 里的 Footer 组件

```jsx
import ProLayout, { DefaultFooter,} from '@ant-design/pro-layout';

var defaultLinks = [{
  key: 'Ant Design Pro',
  title: 'Ant Design Pro',
  href: 'https://pro.ant.design',
  blankTarget: true
}, {
  key: 'Ant Design',
  title: 'Ant Design',
  href: 'https://ant.design',
  blankTarget: true
}];
var defaultCopyright = '2019 云南XXXX集团公司';

const footerRender: BasicLayoutProps['footerRender'] = (_, defaultDom) => {
  if (!isAntDesignPro()) {
    return <>
      <DefaultFooter links={defaultLinks} copyright={defaultCopyright} />
    </>;
  }
  // ...
}
```

## 配置 umi 区块的 npm 源

```
block: {
  defaultGitUrl: 'https://github.com/ant-design/pro-blocks',
  npmclient: 'cnpm',
},
```

## 删除国际化 i18n

```
// 可以使用antd pro命令行工具先删除现有项目的多国语言
yarn i18n-remove

// 然后再添加区块时，就要删除多国语言
umi block list
```

## 关闭 mock 和使用代理

```js
// 关闭mock
yarn start:no-mock

// 配置代理 config
{
  proxy: {
    '/server/api/': {
      target: 'https://preview.pro.ant.design/',
      changeOrigin: true,
      pathRewrite: { '^/server': '' },
    },
  },
}
```
