---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901830"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>호스팅: WebHostBuilder 종속성에서 제거되는 ObjectPoolProvider

ASP.NET Core가 재생에 대해 추가 비용을 지불하도록 하는 과정에서 `ObjectPoolProvider`가 기본 종속성 세트에서 제거되었습니다. `ObjectPoolProvider`에 의존하는 특정 구성 요소가 이제 해당 구성 요소를 추가합니다.

토론은 [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`WebHostBuilder`에서는 기본적으로 DI 컨테이너에 `ObjectPoolProvider`를 제공합니다.

#### <a name="new-behavior"></a>새 동작

`WebHostBuilder`에서는 더 이상 기본적으로 DI 컨테이너에 `ObjectPoolProvider`를 제공하지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

이러한 변경으로 인해 ASP.NET Core가 더 많은 비용을 지불하게 되었습니다.

#### <a name="recommended-action"></a>권장 조치

구성 요소에 `ObjectPoolProvider`가 필요한 경우 `IServiceCollection`을 통해 종속성에 추가해야 합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
