# 如何做开源产品的前端技术调研？ 以 Linkedin DataHub 项目为例

#datahub #linkedin #frontend #big-data #data-middle-platform

前段时间花了两天，看了看LinkedIn Datahub 这个项目。这是LinkedIn 开源的一个元数据管理工具。我负责调研其前端技术情况。国内很多厂商做大数据产品，基本都是基于开源产品（GitHub）集成或者二次开发。这是中国 IT Services 产业发展的阶段性表现。但无论怎样，我们要掌握迅速摸清一个开源产品的技术体系和实现的能力，然后根据产品和业务需求去做二开。

## 项目地址

我们分析一个开源项目，要通读开源项目的文档，特别是架构设计说明，和一些 RFC 说明文档。

- [DataHub](https://datahubproject.io/)
- [Demo](https://demo.datahubproject.io/)
- [React App RFC](https://datahubproject.io/docs/rfc/active/2055-react-app/)
- [React App README](https://github.com/linkedin/datahub/tree/master/datahub-web-react)

## 主要技术构件

如何快速浏览其主要的技术栈：通过 package.json 我们可以简单了解引入的包，了解其技术构件组成。但是并不是构件重要性都是一致的。后续我们需要阅读项目代码，总结归纳出其主要的技术构件。在技术调研阶段，要关注核心的技术构件，不要过于关注枝节性的技术构件。

比如，Datahub React App 前端，主要技术构件为：

- 语言：       TypeScript
- 框架：       React / React Router
- 组件库：     Ant Design
- 前后端通信： GraphQL + React Apollo
- CSS样式：    Styled Components
- 可视化：     vx (react + D3)

## 整体技术分析

在分析完开源产品主要技术组成后，我们需要思考，开源项目为什么选择这个技术栈？技术的优劣是什么，项目是如何做工程的取舍的？比如在 LinkedIn DataHub React App这一项目中:

项目使用 TypeScript开发，TypeScript = JavaScript + Types , 类型是极佳的业务注释。

前端框架采用的React 采用的是 `react@17.0.0` 的版本， 使用 Hooks（react 16.8 引入） 函数式组件写法。头部互联网厂商用 React 多一些。

组件库使用是蚂蚁金服开发的 Ant Design，是 React 体系下第一组件库，功能强大，比 Vue 体系下的 iview 和 elementui 都要好一些。

前后端通信 使用 GraphQL + React Apollo， GraphQL 与 RESTful API 相对比，由前端决定后端的返回结果，可以自定义组合接口，一定程度上能降低联调成本，但实现 GraphQL 后端支撑成本大于前端。

CSS 样式的方案采用了 Styled Componets, CSS in JS 的代表技术。

数据可视化的方案采用了 vx, 现在名为 visx， airbnb 团队开发，用 React 封装了 D3.js， 用于展示可视化图表。

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

这是目前的初步调研，介绍项目大概的技术情况，没有涉及具体代码实现。
技术根据产品后续规划，做进一步的分析与设计与开发。

如果对本文有什么建议可以联系。

## 参考链接

- [microsoft/TypeScript](https://github.com/microsoft/TypeScript)
- [facebook/react](https://github.com/facebook/react)
- [graphql/graphql-js](https://github.com/graphql/graphql-js)
- [apllographql/apollo-client](https://github.com/apollographql/apollo-client)
- [airbnb/visx](https://github.com/airbnb/visx)
- [ant-design/ant-design](https://github.com/ant-design/ant-design)
- [styled-components/styled-components](https://github.com/styled-components/styled-components)