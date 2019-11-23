---
title: Protobuf 열거형-WCF 개발자를 위한 gRPC
description: Protobuf에서 열거형을 선언 하 고 사용 하는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 4ea4d03bede2a9ebfd1f2c3ee56f299e918800e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971571"
---
# <a name="protobuf-enumerations"></a>Protobuf 열거형

Protobuf는 열거형이 `oneof` 필드의 형식을 결정 하는 데 사용 된 이전 섹션에서 볼 수 있듯이 열거형 형식을 지원 합니다. 고유한 열거형 형식을 정의할 수 있으며, Protobuf는 열거형 형식으로 C# 컴파일됩니다. Protobuf는 다른 언어로 사용할 수 있으므로 열거의 명명 규칙은 C# 규칙과 다릅니다. 그러나 코드 생성기는 영리 하 고 이름을 기존 C# 사례로 변환 합니다. 필드 이름에 해당 하는 파스칼식 대/소문자가 열거형 이름으로 시작 하는 경우 제거 됩니다.

예를 들어이 Protobuf 열거형에서 필드는 파스칼식 대/소문자 열거형 이름: `AccountStatus`에 해당 하는 `ACCOUNT_STATUS`접두사가 붙습니다.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

따라서 생성기는 다음 코드에 C# 해당 하는 열거형을 만듭니다.

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

Protobuf 열거형 정의에는 첫 번째 필드로 0 상수가 **있어야** 합니다. 에서 C#와 같이 같은 값을 사용 하 여 여러 필드를 선언할 수 있지만 열거형에서 `allow_alias` 옵션을 사용 하 여이 옵션을 명시적으로 사용 하도록 설정 해야 합니다.

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

Protobuf에서 생성 된 열거형에는 [[Flags]](xref:System.FlagsAttribute) 특성을 적용할 수 없으며 Protobuf는 비트 열거형 조합을 인식 하지 못합니다. 다음 예제를 살펴보겠습니다.

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

`product.AvailableIn`을 `Region.NorthAmerica | Region.SouthAmerica`로 설정 하면 `3`정수 값으로 serialize 됩니다. 클라이언트 또는 서버에서 값을 deserialize 하려고 하면 `3`의 열거 정의에서 일치 항목을 찾지 못하고 결과가 `Region.None`됩니다.

Protobuf에서 여러 열거형 값으로 작업 하는 가장 좋은 방법은 열거형 형식의 `repeated` 필드를 사용 하는 것입니다.

>[!div class="step-by-step"]
>[이전](protobuf-any-oneof.md)
>[다음](protobuf-maps.md)
