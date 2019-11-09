---
title: Protobuf 스칼라 데이터 형식-WCF 개발자를 위한 gRPC
description: .NET Core에서 Protobuf 및 gRPC가 지 원하는 기본 및 잘 알려진 데이터 형식에 대해 알아봅니다.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: cae9cc483ffb791a9b53e6a2d9d7c0924d725a67
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841458"
---
# <a name="protobuf-scalar-data-types"></a>Protobuf 스칼라 데이터 형식

Protobuf는 네이티브 스칼라 값 형식의 범위를 지원 합니다. 다음 표에서는 모두 해당 C# 하는 형식을 보여 줍니다.

| Protobuf 형식 | C# 형식      | 노트 |
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

## <a name="notes"></a>노트

1. `int32` 및 `int64`에 대 한 표준 인코딩은 서명 된 값으로 작업할 때 비효율적입니다. 필드에 음수가 포함 될 가능성이 있는 경우 대신 `sint32` 또는 `sint64`를 사용 합니다. 두 형식은 각각 C# `int` 및 `long` 형식에 매핑됩니다.
2. `fixed` 필드는 값에 관계 없이 항상 동일한 바이트 수를 사용 합니다. 이 동작을 사용 하면 더 큰 값에 대해 serialization 및 deserialization 속도가 더 빨라집니다.
3. Protobuf 문자열은 UTF-8 (또는 7 비트 ASCII)로 인코딩되고 인코딩된 길이는 2<sup>32</sup>보다 클 수 없습니다.
4. Protobuf 런타임은 C# `byte[]` 배열과 쉽게 매핑되는 `ByteString` 형식을 제공 합니다.

## <a name="other-net-primitive-types"></a>기타 .NET 기본 형식

### <a name="dates-and-times"></a>날짜 및 시간

네이티브 스칼라 형식은 <xref:System.DateTimeOffset>, <xref:System.DateTime>및 <xref:System.TimeSpan>와 동일한 C#날짜 및 시간 값을 제공 하지 않습니다. 이러한 형식은 Google의 "잘 알려진 형식" 확장 중 일부를 사용 하 여 지정할 수 있습니다 .이 확장은 지원 되는 플랫폼에서 보다 복잡 한 필드 형식에 대 한 코드 생성 및 런타임 지원을 제공 합니다. 다음 표에서는 날짜 및 시간 형식을 보여 줍니다.

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

C# 클래스에서 생성 된 속성은 .net 날짜 및 시간 형식이 아닙니다. 속성은 `DateTimeOffset`, `DateTime`및 `TimeSpan`로 변환 하는 메서드를 제공 하는 `Google.Protobuf.WellKnownTypes` 네임 스페이스의 `Timestamp` 및 `Duration` 클래스를 사용 합니다.

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

다른 플랫폼에서 `UUID` 이라고 하는 <xref:System.Guid> 형식은 Protobuf에서 직접 지원 되지 않으며 잘 알려진 형식이 아닙니다. 가장 좋은 방법은 모든 언어 및 플랫폼에서 구문 분석할 수 있는 표준 `8-4-4-4-12` 16 진수 형식 (예: `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`)을 사용 하 여 `Guid` 값을 `string` 필드로 처리 하는 것입니다. Endian 관련 문제로 인해 Java와 같은 다른 플랫폼과 상호 작용할 때 비정상적인 동작이 발생할 수 있으므로 `Guid` 값에는 `bytes` 필드를 사용 하지 마세요.

### <a name="nullable-types"></a>Nullable 형식

Protobuf에 대 한 C# 코드 생성은 `int32``int`와 같은 네이티브 형식을 사용 합니다. 이는 값이 항상 포함 되 고 null 일 수 없음을 의미 합니다. C# 코드에 `int?`를 사용 하는 것과 같이 명시적 null이 필요한 값의 경우 Protobuf의 "잘 알려진 형식"은 nullable C# 형식으로 컴파일되는 래퍼를 포함 합니다. 이를 사용 하려면 다음과 같이 `.proto` 파일에 `wrappers.proto`를 가져옵니다.

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

잘 알려진 형식 `Timestamp` 및 `Duration`은 .NET에서 클래스로 표현 되므로 nullable 버전이 필요 하지 않지만 `DateTimeOffset` 또는 `TimeSpan`변환할 때 이러한 형식의 속성에서 null을 확인 하는 것이 중요 합니다.

## <a name="decimals"></a>자릿수로

Protobuf는 기본적으로 .NET `decimal` 형식을 지원 하지 않고 `double` 및 `float`합니다. Protobuf 프로젝트에는 표준 `Decimal` 형식을 잘 알려진 형식에 추가 하는 경우를 지 원하는 언어 및 프레임 워크에 대 한 플랫폼 지원을 제공 하지만 아직 구현 되지 않은 것을 확인할 수 있습니다.

.NET 클라이언트와 서버 간의 안전한 serialization에 사용할 수 있는 `decimal` 형식을 나타내는 메시지 정의를 만들 수 있지만, 다른 플랫폼의 개발자는 사용 되는 형식을 이해 하 고 자체 처리를 구현 해야 합니다.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Protobuf에 대 한 사용자 지정 10 진수 형식 만들기

매우 간단한 구현은 `currency` 필드 없이 일부 Google Api에서 사용 되는 비표준 `Money` 형식과 유사할 수 있습니다.

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

`nanos` 필드는 `0.999_999_999`에서 `-0.999_999_999`값을 나타냅니다. 예를 들어 `decimal` 값 `1.5m` `{ units = 1, nanos = 500_000_000 }`으로 표시 되는 이유는이 예의 `nanos` 필드는 `sfixed32` 형식을 사용 하 여 큰 값 `int32` 보다 효율적으로 인코딩하는 것입니다. `units` 필드가 음수 이면 `nanos` 필드도 음수 여야 합니다.

> [!NOTE]
> `decimal` 값을 바이트 문자열로 인코딩하기 위한 다른 여러 알고리즘이 있지만,이 메시지를 이해 하는 것이 더 쉬울 뿐만 아니라 값이 다른 플랫폼의 *[endian](https://en.wikipedia.org/wiki/Endianness)* 에 의해 영향을 받지 않습니다.

이 형식과 BCL `decimal` 형식 간의 변환은 C# 다음과 같이 구현 될 수 있습니다.

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
> 이와 같은 사용자 지정 유틸리티 메시지 유형을 사용할 때마다 다른 개발자가 자체 언어나 프레임 워크에서 동등한 형식으로 변환 및 변환을 구현할 수 있도록 `.proto`에 주석을 포함 **해야 합니다** .

>[!div class="step-by-step"]
>[이전](protobuf-messages.md)
>[다음](protobuf-nested-types.md)
