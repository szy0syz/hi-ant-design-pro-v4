# Ant Design Pro

This project is initialized with [Ant Design Pro](https://pro.ant.design). Follow is the quick guide for how to use.

## 替换layout里的Footer组件

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
