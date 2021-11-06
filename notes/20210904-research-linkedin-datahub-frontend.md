# Linkedin DataHub 前端技术调研简报

#datahub #linkedin #frontend #big-data #data-middle-platform

<!-- 袁继伟 yuanjw09@chinatelecom.cn -->

## 项目地址

- [DataHub](https://datahubproject.io/)
- [Demo](https://demo.datahubproject.io/)
- [React App RFC](https://datahubproject.io/docs/rfc/active/2055-react-app/)
- [React App README](https://github.com/linkedin/datahub/tree/master/datahub-web-react)

## 主要技术组成

通过 package.json 和浏览项目，可以总结出其主要的技术组成。

- 语言：   TypeScript
- 框架：   React / React Router
- 组件库： Ant Design
- 前后端通信： GraphQL + React Apollo
- CSS样式：Styled Components
- 可视化：vx (react + D3)

## 整体技术分析

项目使用 TypeScript，TypeScript = JavaScript + Types , 类型是极佳的业务注释。

前端框架采用的React 采用的是 `react@17.0.0` 的版本， 使用 Hooks（react 16.8 引入） 函数式组件写法。头部互联网厂商用 React 多一些。

Ant Design 是 蚂蚁金服开发的 React　组件库，功能强大，比现有的 iview 和 elementui 都要好一些。

GraphQL 与 RESTful API 相对比，由前端决定后端的返回结果，可以自定义组合接口，一定程度上能降低联调成本，但实现 GraphQL 后端支撑成本大于前端。

vx, 现在名为 visx， airbnb 团队开发，展示可视化图表，用 React 封装了 D3.js

## 功能分析

Datahub 实现的业务功能主要是：

- 用户认证/用户管理
- 展示元数据
- 更新元数据
- 浏览元数据
- 搜索元数据
  
## 与其他模块的关系

基于 GraphQL 与 [datahub-frontend server](https://github.com/linkedin/datahub) 通信

## 业务（页面）组成分析

路由是分析一个前端项目业务（页面）组成的入口，路由控制配置在 `src/app/Routes.tsx` 中

- `/` -> `HomePage` 
- `/login` -> `LogIn`
- `/search` -> `SearchPage`
- `/entity` -> `EntityPage`
- `/browse` -> `BrowseResultsPage`
- `/analytics` -> `AnalyticsPage`

## EntityPage 

EntityPage `/src/app/entity/EntityPage.tsx` 是最核心的页面，其页面解析分为两种情况:

1. `LineageExplorer`
    使用 vx 库可视化展示血缘分析图，vx 由 airbnb 开发。在 1.0.0 版本后改名，最新版名称为 [visx](https://airbnb.io/visx)。

2. `entityRegistry.renderProfile()` 
    根据路由参数不同，渲染 `src/entity` 目录下不同的页面。比如 `src/entity/chart/ChartEntity.tsx` 、`src/entity/dashboard/DashboardEntity.tsx` 等。

在 2021-09-01 最新版本 dataset 页面结构（布局，样式）与其他 entity 页面不同。

## 技术选型 React vs Vue

对开源项目有一个基本了解后，根据自身业务情况来进行技术上的选型。对UI 层（前端）来讲，最重要的一个技术选型是前端框架内的选择。datahub 采用的前端框架是 react，需要综合产品和技术团队的具体情况选择框架。

#### 选择 React:

优点：
- 前端团队可以拓展 React 的能力，React 生态更丰富。许多大数据开源项目UI层前端技术选型是 React，比如：
    - [Superset](https://superset.apache.org/)
    - [airflow](https://airflow.apache.org/)
- React 是软件服务部前端技术选型的考虑范围。
- 如果改动小，集成和改动的成本低。

缺点：
- React 是独立的前端框架技术体系，有一定维护成本。
- 样式风格不一致，需要一定改动成本。

#### 选择 Vue:

优点：
- 可以保持技术栈与工具链的统一，便于维护。

缺点：
- 需要重写。开发成本高。

## 需要关注和进一步研究的问题

除了前端框架之外，还需要考虑如下问题：

- 是否使用 GraphQL, 需要结合后端考虑
- 国际化 / 多语言：建议方案 react-i18n-next
- 登陆的问题：集成单点登陆
- 用户和路由权限的问题

## 其他

这是目前的初步调研，介绍项目大概的技术情况，没有涉及具体代码实现。根据产品后续规划，做进一步的分析与设计与开发。

## 参考链接

- [microsoft/TypeScript](https://github.com/microsoft/TypeScript)
- [facebook/react](https://github.com/facebook/react)
- [graphql/graphql-js](https://github.com/graphql/graphql-js)
- [apllographql/apollo-client](https://github.com/apollographql/apollo-client)
- [airbnb/visx](https://github.com/airbnb/visx)
- [ant-design/ant-design](https://github.com/ant-design/ant-design)
- [styled-components/styled-components](https://github.com/styled-components/styled-components)