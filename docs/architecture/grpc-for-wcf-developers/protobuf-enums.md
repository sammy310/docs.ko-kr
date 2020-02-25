---
title: Protobuf 열거형-WCF 개발자를 위한 gRPC
description: Protobuf에서 열거형을 선언 하 고 사용 하는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543146"
---
# <a name="protobuf-enumerations"></a>Protobuf 열거형

Protobuf는 열거형 형식을 지원 합니다. 열거형이 `Oneof` 필드의 형식을 결정 하는 데 사용 된 이전 섹션에서이 지원을 살펴보았습니다. 사용자 고유의 열거형 형식을 정의할 수 있으며, Protobuf는 열거형 형식으로 C# 컴파일합니다. 

다양 한 언어와 함께 Protobuf를 사용할 수 있으므로 열거의 명명 규칙은 C# 규칙과 다릅니다. 그러나 코드 생성기는 이름을 기존 C# case로 변환 합니다. 필드 이름에 해당 하는 파스칼식 대/소문자가 열거형 이름으로 시작 하는 경우 제거 됩니다.

예를 들어 다음 Protobuf 열거형에서 필드에는 `ACCOUNT_STATUS`접두사가 붙습니다. 이 접두사는 파스칼식 대/소문자 열거형 이름 `AccountStatus`와 동일 합니다.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

생성기는 다음 코드 C# 에 해당 하는 열거형을 만듭니다.

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

Protobuf 열거형 정의에는 첫 번째 필드로 0 상수가 *있어야* 합니다. 에서 C#와 같이 같은 값을 사용 하 여 여러 필드를 선언할 수 있습니다. 그러나 열거형에서 `allow_alias` 옵션을 사용 하 여이 옵션을 명시적으로 사용 하도록 설정 해야 합니다.

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

`.proto` 파일의 최상위 수준에서 열거형을 선언 하거나 메시지 정의 내에 중첩 시킬 수 있습니다. 중첩 된 메시지와 같이 중첩 된 열거형은 생성 된 메시지 클래스의 `.Types` 정적 클래스 내에서 선언 됩니다.

Protobuf에서 생성 된 열거형에는 [[Flags]](xref:System.FlagsAttribute) 특성을 적용할 수 없으며 Protobuf는 비트 열거형 조합을 인식 하지 못합니다. 다음 예제를 확인 합니다.

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

`product.AvailableIn`을 `Region.NorthAmerica | Region.SouthAmerica`로 설정 하면 `3`정수 값으로 serialize 됩니다. 클라이언트 또는 서버에서 값을 deserialize 하려고 하면 `3`의 열거 정의에서 일치 항목을 찾을 수 없습니다. 결과는 `Region.None`됩니다.

Protobuf에서 여러 열거형 값으로 작업 하는 가장 좋은 방법은 열거형 형식의 `repeated` 필드를 사용 하는 것입니다.

>[!div class="step-by-step"]
>[이전](protobuf-any-oneof.md)
>[다음](protobuf-maps.md)
