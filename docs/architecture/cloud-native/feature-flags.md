---
title: 기능 플래그
description: Azure 앱 구성을 활용 하는 클라우드 네이티브 응용 프로그램에서 기능 플래그 구현
ms.date: 05/03/2020
ms.openlocfilehash: 72e1bfe777854a74fcac926811caf97e59986146
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83398322"
---
# <a name="feature-flags"></a>기능 플래그

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

1 장에서는 cloud native가 속도와 민첩성에 affirmed. 사용자는 신속한 응답성, 혁신적인 기능 및 가동 중지 시간을 예측할 수 있습니다. `Feature flags`는 클라우드 네이티브 응용 프로그램의 민첩성을 향상 시키는 데 도움이 되는 최신 배포 기술입니다. 이를 통해 프로덕션 환경에 새 기능을 배포할 수 있지만 가용성을 제한할 수 있습니다. 스위치 긋기를 사용 하면 앱을 다시 시작 하거나 새 코드를 배포 하지 않고도 특정 사용자에 대 한 새 기능을 활성화할 수 있습니다. 코드 배포에서 새 기능의 릴리스를 분리 합니다.

기능 플래그는 런타임에 사용자의 기능 표시 여부를 제어 하는 조건부 논리를 기반으로 빌드됩니다. 최신 클라우드 네이티브 시스템에서 초기에 새로운 기능을 프로덕션에 배포 하는 것이 일반적 이며 제한 된 대상으로 테스트 합니다. 신뢰도가 증가 함에 따라이 기능은 더 광범위 한 대상에 게 점진적으로 롤아웃 될 수 있습니다.

기능 플래그의 다른 사용 사례는 다음과 같습니다.

- 프리미엄 기능을 특정 고객 그룹으로 제한 하 여 더 높은 구독 요금을 지불 합니다.
- 문제 해결 기능을 신속 하 게 비활성화 하 여 롤백 또는 즉각적인 핫픽스의 위험을 방지 하 여 시스템을 안정화 합니다.
- 사용량이 많은 기간 동안 리소스 사용량이 많은 선택적 기능을 사용 하지 않도록 설정 합니다.
- `experimental feature releases`소규모 사용자 세그먼트를 수행 하 여 가능성 및 인기도의 유효성을 검사 합니다.

또한 기능 플래그는 `trunk-based` 개발을 촉진 합니다. 개발자가 단일 분기의 기능을 공동 작업 하는 소스 제어 분기 모델입니다. 이 접근 방식에서는 많은 수의 장기 실행 기능 분기를 병합 하는 위험과 복잡성을 최소화 합니다. 활성화 될 때 까지는 기능을 사용할 수 없습니다.

## <a name="implementing-feature-flags"></a>기능 플래그 구현

핵심에서 기능 플래그는 단순에 대 한 참조입니다 `decision object` . 또는의 부울 상태를 반환 `on` 합니다 `off` . 플래그는 일반적으로 기능 기능을 캡슐화 하는 코드 블록을 래핑합니다. 플래그 상태는 지정 된 사용자에 대해 해당 코드 블록이 실행 되는지 여부를 결정 합니다. 그림 10-11에서는 구현을 보여 줍니다.

```c#
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

**그림 10-11** -간단한 기능 플래그 구현.

이 방법이 기능 코드와 의사 결정 논리를 구분 하는 방법을 확인 합니다.

1 장에서는에 대해 설명 했습니다 `Twelve-Factor App` . 응용 프로그램 실행 코드의 외부에서 구성 설정을 유지 하는 것이 좋습니다. 필요한 경우 외부 원본에서 설정을 읽을 수 있습니다. 기능 플래그 구성 값은 해당 코드 베이스와도 독립적 이어야 합니다. 별도의 리포지토리에서 플래그 구성을 구체화 응용 프로그램을 수정 하 고 다시 배포 하지 않고도 플래그 상태를 변경할 수 있습니다.

[Azure 앱 구성은](https://docs.microsoft.com/azure/azure-app-configuration/overview) 기능 플래그에 대 한 중앙 집중식 리포지토리를 제공 합니다. 이를 통해 다양 한 종류의 기능 플래그를 정의 하 고 해당 상태를 빠르고 안전 하 게 조작할 수 있습니다. 앱 구성 클라이언트 라이브러리를 응용 프로그램에 추가 하 여 기능 플래그 기능을 사용 하도록 설정 합니다. 다양 한 프로그래밍 언어 프레임 워크가 지원 됩니다.

기능 플래그는 [ASP.NET Core 서비스](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core)에서 쉽게 구현할 수 있습니다. .NET 기능 관리 라이브러리 및 앱 구성 공급자를 설치 하면 코드에 기능 플래그를 선언적으로 추가할 수 있습니다. 이러한 속성을 사용 하면 `FeatureGate` 코드 베이스 전체에서 if 문을 수동으로 작성할 필요가 없습니다.

Startup 클래스에서 구성 된 후에는 컨트롤러, 작업 또는 미들웨어 수준에서 기능 플래그 기능을 추가할 수 있습니다. 그림 10-12은 컨트롤러 및 작업 구현을 제공 합니다.

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public class ProductController : Controller
{
    ...
}
```

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public IActionResult UpdateProductStatus()
{
    return ObjectResult(ProductDto);
}
```

**그림 10-12** -컨트롤러 및 작업의 기능 플래그 구현입니다.

기능 플래그를 사용 하지 않도록 설정 하면 사용자는 응답 본문이 없는 404 (찾을 수 없음) 상태 코드를 받게 됩니다.

기능 플래그는 c # 클래스에 직접 삽입할 수도 있습니다. 그림 10-13에서는 기능 플래그 삽입을 보여 줍니다.

```c#
public class ProductController : Controller
{
    private readonly IFeatureManager _featureManager;

    public ProductController(IFeatureManager featureManager)
    {
        _featureManager = featureManager;
    }
}
```

**그림 10-13** -클래스에 대 한 기능 플래그 삽입

기능 관리 라이브러리는 백그라운드에서 기능 플래그 수명 주기를 관리 합니다. 예를 들어, 구성 저장소에 대 한 많은 수의 호출을 최소화 하기 위해 라이브러리 캐시 플래그는 지정 된 기간 동안 상태를 지정 합니다. 요청을 호출 하는 동안 플래그 상태의 불변성을 보장할 수 있습니다. 또한도 제공 `Point-in-time snapshot` 합니다. 모든 키 값의 기록을 다시 생성 하 고 이전 7 일 이내에 언제 든 지 과거 값을 제공할 수 있습니다.

>[!div class="step-by-step"]
>[이전](devops.md)
>[다음](infrastructure-as-code.md)
