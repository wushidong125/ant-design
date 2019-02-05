---
order: 12
title:
  zh-CN: 自定义页签头
  en-US: Customized bar of tab
---

## zh-CN

使用 react-sticky 组件实现吸顶效果。

## en-US

use react-sticky.

````jsx
import { Tabs } from 'antd';
import { StickyContainer, Sticky } from 'react-sticky';

const TabPane = Tabs.TabPane;

const renderTabBar = (props, DefaultTabBar) => (
  <Sticky bottomOffset={80}>
    {({ style }) => (
      <DefaultTabBar {...props} style={{ ...style, zIndex: 1, background: '#fff' }} />
    )}
  </Sticky>
);

ReactDOM.render(
  <StickyContainer>
    <Tabs defaultActiveKey="1" renderTabBar={renderTabBar}>
      <TabPane tab="Tab 1" key="1" style={{ height: 200 }}>Content of Tab Pane 1</TabPane>
      <TabPane tab="Tab 2" key="2">Content of Tab Pane 2</TabPane>
      <TabPane tab="Tab 3" key="3">Content of Tab Pane 3</TabPane>
    </Tabs>
  </StickyContainer>,
  mountNode
);
````