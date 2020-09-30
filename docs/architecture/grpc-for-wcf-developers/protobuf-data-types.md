---
title: Protobuf 스칼라 데이터 형식-WCF 개발자를 위한 gRPC
description: .NET Core에서 Protobuf 및 gRPC를 지 원하는 기본 및 잘 알려진 데이터 형식에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 5447067b953d257258950d020636e0b38245e20d
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91573646"
---
# <a name="protobuf-scalar-data-types"></a>Protobuf 스칼라 데이터 형식

프로토콜 버퍼 (Protobuf)는 네이티브 스칼라 값 형식의 범위를 지원 합니다. 모든 값 형식 및 이와 동등한 C# 형식이 다음 표에 나와 있습니다.

| Protobuf 형식 | C# 형식      | 메모 |
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

1. 부호 있는 값으로 작업 하는 경우 및에 대 한 표준 인코딩이 `int32` `int64` 비효율적입니다. 필드에 음수가 포함 될 가능성이 있는 경우 `sint32` 대신 또는를 사용 `sint64` 합니다. 이러한 형식은 각각 c # `int` 및 형식에 매핑됩니다 `long` .
2. `fixed`필드는 값에 관계 없이 항상 동일한 바이트 수를 사용 합니다. 이 동작을 사용 하면 더 큰 값에 대해 serialization 및 deserialization 속도가 더 빨라집니다.
3. Protobuf 문자열은 u t f-8 (또는 7 비트 ASCII)로 인코딩됩니다. 인코딩된 길이는 2<sup>32</sup>보다 클 수 없습니다.
4. Protobuf 런타임은 `ByteString` c # 배열에 대해 쉽게 매핑되는 형식을 제공 `byte[]` 합니다.

## <a name="other-net-primitive-types"></a>기타 .NET 기본 형식

### <a name="dates-and-times"></a>날짜 및 시간

네이티브 스칼라 형식은 c #의, 및에 해당 하는 날짜 및 시간 값을 제공 하지 않습니다 <xref:System.DateTimeOffset> <xref:System.DateTime> <xref:System.TimeSpan> . Google의 "잘 알려진 형식" 확장 중 일부를 사용 하 여 이러한 형식을 지정할 수 있습니다. 이 확장은 지원되는 플랫폼에서 복합 필드 형식을 위한 코드 생성과 런타임을 지원합니다.

다음 표에는 날짜 및 시간 형식이 나와 있습니다.

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

C# 클래스에서 생성되는 속성은 .NET 날짜 및 시간 형식이 아닙니다. 해당 속성은 `Google.Protobuf.WellKnownTypes` 네임스페이스의 `Timestamp` 클래스와 `Duration` 클래스를 사용하며, 이 클래스는 `DateTimeOffset`, `DateTime`, `TimeSpan`으로/에서 변환하는 메서드를 제공합니다.

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
> `Timestamp` 형식은 UTC 시간으로 작동합니다. `DateTimeOffset` 값의 오프셋은 항상 0이며 `DateTime.Kind` 속성은 항상 `DateTimeKind.Utc`입니다.

### <a name="systemguid"></a>System.Guid

Protobuf <xref:System.Guid> 는 다른 플랫폼에서 알려진 형식을 직접 지원 하지 않습니다 `UUID` . 잘 알려진 형식은 없습니다.

가장 좋은 방법은 `Guid` `string` 표준 `8-4-4-4-12` 16 진수 형식 (예:)을 사용 하 여 값을 필드로 처리 하는 것입니다 `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` . 모든 언어 및 플랫폼에서 해당 형식을 구문 분석할 수 있습니다.

값에 필드를 사용 하지 마세요 `bytes` `Guid` . *Endian* ([위키백과 정의](https://en.wikipedia.org/wiki/Endianness)) 문제가 있으면 Protobuf가 Java와 같은 다른 플랫폼과 상호 작용할 때 비정상적인 동작이 발생할 수 있습니다.

### <a name="nullable-types"></a>Nullable 유형

C#에 해당하는 Protobuf 코드를 생성하는 데에는 네이티브 형식을 사용합니다(예: `int32`에 대해 `int` 사용). 따라서 값은 항상 포함 되며 null 일 수 없습니다.

C # 코드에서를 사용 하는 경우와 같이 명시적 null이 필요한 값의 경우 `int?` Protobuf의 "잘 알려진 형식"에는 Nullable c # 형식으로 컴파일되는 래퍼가 포함 됩니다. 이를 사용 하려면 `wrappers.proto` `.proto` 다음과 같이 파일을 가져옵니다.

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf는 `T?` 생성 된 메시지 속성에 단순 (예:)을 사용 합니다 `int?` .

다음 표에는 래퍼 형식의 전체 목록 및 이와 동등한 C# 형식이 나와 있습니다.

| C# 형식   | 잘 알려진 형식 래퍼       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

잘 알려진 형식 및은 `Timestamp` `Duration` .net에서 클래스로 표현 됩니다. C # 8 이상에서 nullable 참조 형식을 사용할 수 있습니다. 그러나 또는로 변환 하는 경우 해당 형식의 속성에서 null을 확인 하는 것이 중요 합니다 `DateTimeOffset` `TimeSpan` .

## <a name="decimals"></a>10진수

Protobuf는 기본적으로 .NET `decimal` 형식을 지원하지 않으며 `double` 및 `float`만 지원합니다. Protobuf 프로젝트에는 표준 `Decimal` 유형을 지 원하는 언어 및 프레임 워크에 대 한 플랫폼 지원과 함께 잘 알려진 형식에 표준 유형을 추가할 수 있는 것에 대 한 지속적인 토론이 있습니다. 아직 아무것도 구현되지 않았습니다.

`decimal`.Net 클라이언트와 서버 간에 안전 하 게 직렬화 하는 데 사용할 형식을 나타내는 메시지 정의를 만들 수 있습니다. 그러나 다른 플랫폼의 개발자는 사용되는 형식을 이해하고 이 형식에 대한 고유한 처리를 구현해야 합니다.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Protobuf에 대한 사용자 지정 10진수 형식 만들기

간단한 구현은 `Money` 일부 Google api가 필드 없이 사용 하는 비표준 형식과 유사할 수 있습니다 `currency` .

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message DecimalValue {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

`nanos` 필드는 `0.999_999_999`부터 `-0.999_999_999`까지의 값을 나타냅니다. 예를 들어 `decimal` 값 `1.5m`은 `{ units = 1, nanos = 500_000_000 }`으로 표시됩니다. 이런 이유로 이 예제에서 비교적 큰 값에 대해 `int32`보다 더 효율적으로 인코딩 `sfixed32` 형식을 `nanos` 필드에 사용합니다. `units` 필드가 음수이면 `nanos` 필드도 음수여야 합니다.

> [!NOTE]
> `decimal` 값을 바이트 문자열로 인코딩하기 위한 다른 여러 알고리즘이 있지만, 이 메시지가 더 쉽게 이해됩니다. 값은 서로 다른 플랫폼에 있는 endian의 영향을 받지 않습니다.

이 형식과 BCL `decimal` 형식 간의 변환은 다음과 같이 C#로 구현될 수 있습니다.

```csharp
namespace CustomTypes
{
    public partial class DecimalValue
    {
        private const decimal NanoFactor = 1_000_000_000;
        public DecimalValue(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.DecimalValue grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.DecimalValue(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.DecimalValue(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> 이와 같은 사용자 지정 메시지 유형을 사용할 때마다의 주석을 사용 하 여 문서를 작성 *해야* 합니다 `.proto` . 그러면 다른 개발자가 자체 언어나 프레임 워크에서 동등한 형식으로의 변환을 구현할 수 있습니다.

>[!div class="step-by-step"]
>[이전](protobuf-messages.md)
>[다음](protobuf-nested-types.md)
