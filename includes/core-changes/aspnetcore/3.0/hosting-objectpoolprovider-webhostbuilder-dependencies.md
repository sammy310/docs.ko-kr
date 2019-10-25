---
ms.openlocfilehash: 16b9fde49f513643a37f65f3e926a34fc991c55a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394318"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>호스팅: WebHostBuilder 종속성에서 제거되는 ObjectPoolProvider

ASP.NET Core가 재생에 대해 추가 비용을 지불하도록 하는 과정에서 `ObjectPoolProvider`가 기본 종속성 세트에서 제거되었습니다. `ObjectPoolProvider`에 의존하는 특정 구성 요소가 이제 해당 구성 요소를 추가합니다.

자세한 내용은 [aspnet/AspNetCore#5944](https://github.com/aspnet/AspNetCore/issues/5944)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`WebHostBuilder`에서는 기본적으로 DI 컨테이너에 `ObjectPoolProvider`를 제공합니다.

#### <a name="new-behavior"></a>새 동작

`WebHostBuilder`에서는 더 이상 기본적으로 DI 컨테이너에 `ObjectPoolProvider`를 제공하지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

이러한 변경으로 인해 ASP.NET Core가 더 많은 비용을 지불하게 되었습니다.

#### <a name="recommended-action"></a>권장 작업

구성 요소에 `ObjectPoolProvider`가 필요한 경우 `IServiceCollection`을 통해 종속성에 추가해야 합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
