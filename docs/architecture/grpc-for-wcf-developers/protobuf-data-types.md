---
title: 프로토부프 스칼라 데이터 유형 - WCF 개발자를 위한 gRPC
description: .NET Core에서 Protobuf 및 gRPC가 지원하는 기본 및 잘 알려진 데이터 형식에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: ea3b53426ecf6f50f3bae22a537e227b07248508
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249437"
---
# <a name="protobuf-scalar-data-types"></a>Protobuf 스칼라 데이터 형식

프로토콜 버퍼(Protobuf)는 다양한 네이티브 스칼라 값 형식을 지원합니다. 다음 표에는 해당 C# 형식이 모두 나열되어 있습니다.

| 프로토부타입 | C# 형식      | 메모 |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

참고:

1. 서명된 값으로 `int32` `int64` 작업할 때 표준 인코딩이 비효율적이며 비효율적입니다. 필드에 음수가 포함될 가능성이 있는 `sint32` 경우 `sint64` 사용하거나 대신 사용합니다. 이러한 형식은 각각 `int` C# 및 `long` 유형에 매핑됩니다.
2. `fixed` 필드는 항상 값에 관계없이 동일한 바이트 수를 사용합니다. 이 동작은 더 큰 값에 대해 직렬화 및 직렬화를 더 빠르게 만듭니다.
3. 프로토부프 문자열은 UTF-8(또는 7비트 ASCII)으로 인코딩됩니다. 인코딩된 길이는 2<sup>32보다</sup>클 수 없습니다.
4. Protobuf 런타임은 `ByteString` C# `byte[]` 배열과 쉽게 매핑되는 형식을 제공합니다.

## <a name="other-net-primitive-types"></a>기타 .NET 기본 형식

### <a name="dates-and-times"></a>날짜 및 시간

네이티브 스칼라 형식은 날짜 및 시간 값(C#의 및 <xref:System.DateTimeOffset> <xref:System.DateTime> <xref:System.TimeSpan>에 해당)을 제공하지 않습니다. Google의 '잘 알려진 유형' 광고 확장을 사용하여 이러한 유형을 지정할 수 있습니다. 이러한 확장은 지원되는 플랫폼 전체에서 복잡한 필드 형식에 대한 코드 생성 및 런타임 지원을 제공합니다.

다음 표에서는 날짜 및 시간 유형을 보여 주며,

| C# 형식 | 프로토부프 잘 알려진 타입 |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

C# 클래스에서 생성된 속성은 .NET 날짜 및 시간 형식이 아닙니다. 속성은 네임스페이스에서 `Timestamp` 및 `Duration` 클래스를 `Google.Protobuf.WellKnownTypes` 사용합니다. 이러한 클래스는 에서 `DateTimeOffset` `DateTime`및 에서 변환하는 `TimeSpan`메서드를 제공합니다.

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> 형식은 `Timestamp` UTC 시간과 함께 작동합니다. `DateTimeOffset`값은 항상 오프셋이 0이고 속성은 `DateTime.Kind` 항상 `DateTimeKind.Utc`입니다.

### <a name="systemguid"></a>System.Guid

Protobuf는 다른 플랫폼에서 <xref:System.Guid> 알려진 `UUID` 형식을 직접 지원하지 않습니다. 잘 알려진 유형은 없습니다.

가장 좋은 방법은 `Guid` 표준 `string` `8-4-4-4-12` 헥사데피말 형식(예: `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`)을 사용하여 값을 필드로 처리하는 것입니다. 모든 언어와 플랫폼은 해당 형식을 구문 분석할 수 있습니다.

`Guid` 값에 `bytes` 필드를 사용하지 마십시오. Protobuf가 Java와 같은 다른 플랫폼과 상호 작용할 때 *endianness(위키백과* [정의)에](https://en.wikipedia.org/wiki/Endianness)문제가 발생할 수 있습니다.

### <a name="nullable-types"></a>Nullable 형식

C#에 대한 Protobuf 코드 생성은 `int` 에 `int32`대한 네이티브 형식을 사용합니다. 따라서 값은 항상 포함되며 null이 될 수 없습니다.

C# 코드에서 사용하는 `int?` 것과 같이 명시적 null이 필요한 값의 경우 Protobuf의 "잘 알려진 형식"에는 nullable C# 유형으로 컴파일되는 래퍼가 포함됩니다. 이를 사용하려면 `wrappers.proto` 다음과 `.proto` 같이 파일로 가져옵니다.

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf는 생성된 `T?` 메시지 속성에 `int?`대해 단순(예: )을 사용합니다.

다음 표에서는 동등한 C# 형식을 가진 래퍼 유형의 전체 목록을 보여 주었습니다.

| C# 형식   | 잘 알려진 타입 래퍼       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

잘 알려진 `Timestamp` 형식과 `Duration` .NET에서 클래스로 표시됩니다. C# 8 이상에서는 nullable 참조 형식을 사용할 수 있습니다. 그러나 `DateTimeOffset` 변환 할 `TimeSpan`때 해당 형식의 속성에 null을 확인하는 것이 중요합니다.

## <a name="decimals"></a>10진수

Protobuf는 기본적으로 .NET `decimal` 형식을 지원하지 `double` `float`않습니다. Protobuf 프로젝트에서는 잘 알려진 형식에 표준 `Decimal` 형식을 추가할 가능성에 대해 지속적으로 논의하고 있으며 이를 지원하는 언어 및 프레임워크에 대한 플랫폼 지원이 있습니다. 아직 구현된 것은 없습니다.

.NET 클라이언트와 서버 간에 안전한 `decimal` 직렬화를 위해 작동하는 형식을 나타내는 메시지 정의를 만들 수 있습니다. 그러나 다른 플랫폼의 개발자는 사용 중인 형식을 이해하고 해당 형식에 대한 자체 처리를 구현해야 합니다.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>프로토부프에 대한 사용자 지정 소수점 만들기

간단한 구현은 필드 없이 일부 `Money` Google API가 사용하는 비표준 `currency` 형식과 유사할 수 있습니다.

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message Decimal {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

`nanos` 필드는 에서 `0.999_999_999` 값을 `-0.999_999_999`나타냅니다. 예를 들어 `decimal` 값은 `1.5m` 로 `{ units = 1, nanos = 500_000_000 }`표시됩니다. 이 예제의 `nanos` 필드는 큰 값보다 `sfixed32` `int32` 더 효율적으로 인코딩하는 형식을 사용합니다. 필드가 `units` 음수이면 `nanos` 필드도 음수여야 합니다.

> [!NOTE]
> 값을 바이트 문자열로 인코딩하기 `decimal` 위한 다른 알고리즘이 여러 개 있지만 이 메시지는 그 어떤 알고리즘보다 이해하기 쉽습니다. 값은 다른 플랫폼의 endianness의 영향을 받지 않습니다.

이 형식과 BCL `decimal` 형식 간의 변환은 다음과 같이 C#에서 구현될 수 있습니다.

```csharp
namespace CustomTypes
{
    public partial class GrpcDecimal
    {
        private const decimal NanoFactor = 1_000_000_000;
        public GrpcDecimal(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.Decimal grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.Decimal(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.Decimal(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> 이와 같은 사용자 지정 메시지 유형을 사용할 때마다 `.proto`의 주석으로 *문서화해야 합니다.* 그런 다음 다른 개발자는 해당 언어 또는 프레임워크에서 해당 형식으로 변환을 구현할 수 있습니다.

>[!div class="step-by-step"]
>[이전](protobuf-messages.md)
>[다음](protobuf-nested-types.md)
