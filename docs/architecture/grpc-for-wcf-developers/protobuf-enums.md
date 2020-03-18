---
title: 프로토부프 열거 - WCF 개발자를 위한 gRPC
description: Protobuf에서 열거를 선언하고 사용하는 방법을 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148077"
---
# <a name="protobuf-enumerations"></a>Protobuf 열거형

Protobuf는 열거 유형을 지원합니다. 이전 섹션에서는 열거형이 `Oneof` 필드의 유형을 결정하는 데 사용되었습니다. 사용자 고유의 열거 형 유형을 정의할 수 있으며 Protobuf는 이를 C# 열거형 유형으로 컴파일합니다.

다양한 언어로 Protobuf를 사용할 수 있으므로 열거에 대한 명명 규칙은 C# 규칙과 다릅니다. 그러나 코드 생성기는 이름을 기존 C# 사례로 변환합니다. 필드 이름과 동일한 파스칼 대/소문자가 열거 형 이름으로 시작하면 제거됩니다.

예를 들어 다음 Protobuf 열거형에서 필드에 는 접두사입니다. `ACCOUNT_STATUS` 이 접두사는 파스칼 대/소문자 열거형 이름과 동일합니다. `AccountStatus`

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

생성기는 다음 코드와 동일한 C# 열거형을 만듭니다.

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

Protobuf 열거 정의는 첫 번째 필드로 0 상수가 *있어야 합니다.* C#에서와 마찬가지로 동일한 값을 가진 여러 필드를 선언할 수 있습니다. 그러나 열거형의 `allow_alias` 옵션을 사용하여 이 옵션을 명시적으로 활성화해야 합니다.

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

`.proto` 파일의 최상위 수준에서 열거를 선언하거나 메시지 정의 내에 중첩할 수 있습니다. 중첩된 메시지와 같은 중첩 열거형은 생성된 `.Types` 메시지 클래스의 정적 클래스 내에서 선언됩니다.

프로토부프가 생성한 열거형에 [[깃발]](xref:System.FlagsAttribute) 속성을 적용할 수 있는 방법은 없으며, Protobuf는 비트별 열거형 조합을 이해하지 못합니다. 다음 예제를 살펴보십시오.

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

을 로 `product.AvailableIn` 설정하면 정수 값으로 `3`직렬화됩니다. `Region.NorthAmerica | Region.SouthAmerica` 클라이언트 또는 서버가 값을 역직렬화하려고 하면 에 대한 `3`열거형 정의에서 일치하는 값을 찾을 수 없습니다. 결과는 . `Region.None`

Protobuf에서 여러 열거형 값으로 작업하는 가장 `repeated` 좋은 방법은 열거형 형식의 필드를 사용하는 것입니다.

>[!div class="step-by-step"]
>[이전](protobuf-any-oneof.md)
>[다음](protobuf-maps.md)
