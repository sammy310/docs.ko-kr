---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394098"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a>SPA: 사용되지 않는 것으로 표시된 SpaServices 및 NodeServices

다음 NuGet 패키지의 내용은 ASP.NET Core 2.1 이후 모두 필요하지 않습니다. 따라서 다음 패키지는 사용되지 않는 것으로 표시됩니다.

- [Microsoft.AspNetCore.SpaServices](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [Microsoft.AspNetCore.NodeServices](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

동일한 이유로 다음 npm 모듈은 더 이상 사용되지 않는 것으로 표시됩니다.

- [aspnet-angular](https://www.npmjs.com/package/aspnet-angular)
- [aspnet-prerendering](https://www.npmjs.com/package/aspnet-prerendering)
- [aspnet-webpack](https://www.npmjs.com/package/aspnet-webpack)
- [aspnet-webpack-react](https://www.npmjs.com/package/aspnet-webpack-react)
- [domain-task](https://www.npmjs.com/package/domain-task)

이전 패키지 및 npm 모듈은 나중에 .NET 5에서 제거됩니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

사용되지 않는 패키지 및 npm 모듈은 ASP.NET Core를 다양한 SPA(단일 페이지 앱) 프레임워크와 통합하기 위한 것입니다. 이러한 프레임워크에는 Angular, React 및 Redux를 사용한 React가 포함됩니다.

#### <a name="new-behavior"></a>새 동작

[Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet 패키지에 새 통합 메커니즘이 있습니다. 패키지는 ASP.NET Core 2.1 이후 Angular 및 React 프로젝트 템플릿의 기반으로 유지됩니다.

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core는 Angular, React 및 Redux를 React를 포함한 다양한 SPA(단일 페이지 앱) 프레임워크와의 통합을 지원합니다. 처음에 이러한 프레임워크와의 통합은 서버 쪽 렌더링 및 Webpack과의 통합과 같은 시나리오를 처리하는 ASP.NET Core 관련 구성 요소를 사용하여 수행되었습니다. 시간이 지남에 따라 업계 표준이 변경되었습니다. 각 SPA 프레임워크는 자체 표준 명령줄 인터페이스를 릴리스했습니다. 예를 들어 Angular CLI 및 create-react-app입니다.

2018년 5월에 ASP.NET Core 2.1이 릴리스되었을 때 팀은 표준 변경에 대응했습니다. SPA 프레임워크 자체 도구 체인과 통합하는 새롭고 간단한 방법이 제공되었습니다. 새로운 통합 메커니즘은 `Microsoft.AspNetCore.SpaServices.Extensions` 패키지에 존재하며 ASP.NET Core 2.1 이후 Angular 및 React 프로젝트 템플릿의 기반으로 유지됩니다.

이전 ASP.NET Core 관련 구성 요소는 관련이 없으며 권장되지 않는다는 것을 명확하게 하기 위해 다음과 같이 합니다.

- 2\.1 이전 통합 메커니즘은 사용되지 않는 것으로 표시되었습니다.
- 지원되는 npm 패키지는 더 이상 사용되지 않는 것으로 표시됩니다.

#### <a name="recommended-action"></a>권장 작업

이러한 패키지를 사용하는 경우 다음 기능을 사용하도록 앱을 업데이트합니다.

- `Microsoft.AspNetCore.SpaServices.Extensions` 패키지에 있습니다.
- 사용 중인 SPA 프레임워크에서 제공됨

서버 쪽 렌더링 및 핫 모듈 재로드와 같은 기능을 사용하려면 해당 SPA 프레임워크에 대한 설명서를 참조하세요. `Microsoft.AspNetCore.SpaServices.Extensions`의 기능은 사용되지 않는 것이 *아니며* 계속 지원됩니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
