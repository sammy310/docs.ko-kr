---
title: Protobuf 스칼라 데이터 형식-WCF 개발자를 위한 gRPC
description: .NET Core에서 Protobuf 및 gRPC를 지 원하는 기본 및 잘 알려진 데이터 형식에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: f5215550a6a2d54dfe2e859c574a34f641fdb68d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543159"
---
# <a name="protobuf-scalar-data-types"></a>Protobuf 스칼라 데이터 형식

프로토콜 버퍼 (Protobuf)는 네이티브 스칼라 값 형식의 범위를 지원 합니다. 다음 표에서는 모두 해당 C# 하는 형식을 보여 줍니다.

| Protobuf 형식 | C# 형식      | 참고 |
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

1. 부호 있는 값으로 작업 하는 경우 `int32` 및 `int64`에 대 한 표준 인코딩은 비효율적입니다. 필드에 음수가 포함 될 가능성이 있는 경우 대신 `sint32` 또는 `sint64`를 사용 합니다. 이러한 형식은 각각 C# `int` 및 `long` 형식에 매핑됩니다.
2. `fixed` 필드는 값에 관계 없이 항상 동일한 바이트 수를 사용 합니다. 이 동작을 사용 하면 더 큰 값에 대해 serialization 및 deserialization 속도가 더 빨라집니다.
3. Protobuf 문자열은 u t f-8 (또는 7 비트 ASCII)로 인코딩됩니다. 인코딩된 길이는 2<sup>32</sup>보다 클 수 없습니다.
4. Protobuf 런타임은 C# `byte[]` 배열과 쉽게 매핑되는 `ByteString` 형식을 제공 합니다.

## <a name="other-net-primitive-types"></a>기타 .NET 기본 형식

### <a name="dates-and-times"></a>날짜 및 시간

네이티브 스칼라 형식은 <xref:System.DateTimeOffset>, <xref:System.DateTime>및 <xref:System.TimeSpan>와 동일한 C#날짜 및 시간 값을 제공 하지 않습니다. Google의 "잘 알려진 형식" 확장 중 일부를 사용 하 여 이러한 형식을 지정할 수 있습니다. 이러한 확장은 지원 되는 플랫폼에서 복합 필드 형식에 대 한 코드 생성 및 런타임 지원을 제공 합니다. 

다음 표에서는 날짜 및 시간 형식을 보여 줍니다.

| C# 형식 | Protobuf 잘 알려진 형식 |
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

C# 클래스에서 생성 된 속성은 .net 날짜 및 시간 형식이 아닙니다. 속성은 `Google.Protobuf.WellKnownTypes` 네임 스페이스의 `Timestamp` 및 `Duration` 클래스를 사용 합니다. 이러한 클래스는 `DateTimeOffset`, `DateTime`및 `TimeSpan`변환 하는 메서드를 제공 합니다.

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
> `Timestamp` 형식은 UTC 시간으로 작동 합니다. `DateTimeOffset` 값의 오프셋은 항상 0 이며 `DateTime.Kind` 속성은 항상 `DateTimeKind.Utc`됩니다.

### <a name="systemguid"></a>System.Guid

Protobuf는 다른 플랫폼에서 `UUID` 이라고 하는 <xref:System.Guid> 형식을 직접 지원 하지 않습니다. 잘 알려진 형식은 없습니다. 

가장 좋은 방법은 표준 `8-4-4-4-12` 16 진수 형식 (예: `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`)을 사용 하 여 `Guid` 값을 `string` 필드로 처리 하는 것입니다. 모든 언어 및 플랫폼에서 해당 형식을 구문 분석할 수 있습니다.

`Guid` 값에는 `bytes` 필드를 사용 하지 마세요. *Endian* ([위키백과 정의](https://en.wikipedia.org/wiki/Endianness)) 문제가 있으면 Protobuf가 Java와 같은 다른 플랫폼과 상호 작용할 때 비정상적인 동작이 발생할 수 있습니다.

### <a name="nullable-types"></a>Nullable 형식

Protobuf에 대 한 C# 코드 생성은 `int32``int`와 같은 네이티브 형식을 사용 합니다. 따라서 값은 항상 포함 되며 null 일 수 없습니다. 

C# 코드에 `int?`를 사용 하는 것과 같이 명시적 null이 필요한 값의 경우 Protobuf의 "잘 알려진 형식"은 nullable C# 형식으로 컴파일되는 래퍼를 포함 합니다. 이를 사용 하려면 다음과 같이 `.proto` 파일에 `wrappers.proto`를 가져옵니다.

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf는 생성 된 메시지 속성에 단순 `T?` (예: `int?`)를 사용 합니다.

다음 표에서는 해당 C# 형식이 있는 래퍼 형식의 전체 목록을 보여 줍니다.

| C# 형식   | 잘 알려진 형식 래퍼       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

잘 알려진 형식 `Timestamp` 및 `Duration`은 .NET에서 클래스로 표현 되므로 nullable 버전이 필요 하지 않습니다. 그러나 `DateTimeOffset` 또는 `TimeSpan`으로 변환 하는 경우 해당 형식의 속성에 대해 null을 확인 하는 것이 중요 합니다.

## <a name="decimals"></a>소수 자릿수

Protobuf는 기본적으로 .NET `decimal` 형식을 지원 하지 않고 `double` 및 `float`합니다. Protobuf 프로젝트에는 표준 `Decimal` 유형을 지 원하는 언어 및 프레임 워크에 대 한 플랫폼 지원과 함께 잘 알려진 형식에 추가할 수 있는 정보에 대 한 지속적인 토론이 있습니다. 아직 구현 된 항목이 없습니다.

.NET 클라이언트와 서버 간에 안전 하 게 직렬화 하는 데 사용할 수 있는 `decimal` 형식을 나타내는 메시지 정의를 만들 수 있습니다. 그러나 다른 플랫폼의 개발자는 사용 되는 형식을 이해 하 고이에 대 한 자체 처리를 구현 해야 합니다.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Protobuf에 대 한 사용자 지정 10 진수 형식 만들기

간단한 구현은 `currency` 필드 없이 일부 Google Api가 사용 하는 비표준 `Money` 형식과 유사할 수 있습니다.

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

`nanos` 필드는 `0.999_999_999`에서 `-0.999_999_999`값을 나타냅니다. 예를 들어 `decimal` 값 `1.5m` `{ units = 1, nanos = 500_000_000 }`표시 됩니다. 이는이 예제에서 `nanos` 필드가 더 큰 값에 대해 `int32` 보다 효율적으로 인코딩하는 `sfixed32` 형식을 사용 하기 때문입니다. `units` 필드가 음수 이면 `nanos` 필드도 음수 여야 합니다.

> [!NOTE]
> `decimal` 값을 바이트 문자열로 인코딩하기 위한 다른 여러 알고리즘이 있지만,이 메시지를 보다 쉽게 이해할 수 있습니다. 값은 서로 다른 플랫폼에 있는 endian의 영향을 받지 않습니다.

이 형식과 BCL `decimal` 형식 간의 변환은 다음과 C# 같이 구현 될 수 있습니다.

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
> 이와 같은 사용자 지정 메시지 유형을 사용할 때마다 `.proto`주석을 사용 하 여 문서를 작성 *해야* 합니다. 그러면 다른 개발자가 자체 언어나 프레임 워크에서 동등한 형식으로의 변환을 구현할 수 있습니다.

>[!div class="step-by-step"]
>[이전](protobuf-messages.md)
>[다음](protobuf-nested-types.md)
