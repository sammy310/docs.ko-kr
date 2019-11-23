---
title: Protobuf 스칼라 데이터 형식-WCF 개발자를 위한 gRPC
description: .NET Core에서 Protobuf 및 gRPC가 지 원하는 기본 및 잘 알려진 데이터 형식에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: ae7f5f48099000dff0eefb36e23cb9b9f2ac517c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971548"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="bb5e3-103">Protobuf 스칼라 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-103">Protobuf scalar data types</span></span>

<span data-ttu-id="bb5e3-104">Protobuf는 네이티브 스칼라 값 형식의 범위를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-104">Protobuf supports a range of native scalar value types.</span></span> <span data-ttu-id="bb5e3-105">다음 표에서는 모두 해당 C# 하는 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="bb5e3-106">Protobuf 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-106">Protobuf type</span></span> | <span data-ttu-id="bb5e3-107">C# 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-107">C# type</span></span>      | <span data-ttu-id="bb5e3-108">참고</span><span class="sxs-lookup"><span data-stu-id="bb5e3-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="bb5e3-109">1</span><span class="sxs-lookup"><span data-stu-id="bb5e3-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="bb5e3-110">1</span><span class="sxs-lookup"><span data-stu-id="bb5e3-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="bb5e3-111">1</span><span class="sxs-lookup"><span data-stu-id="bb5e3-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="bb5e3-112">1</span><span class="sxs-lookup"><span data-stu-id="bb5e3-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="bb5e3-113">2</span><span class="sxs-lookup"><span data-stu-id="bb5e3-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="bb5e3-114">2</span><span class="sxs-lookup"><span data-stu-id="bb5e3-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="bb5e3-115">2</span><span class="sxs-lookup"><span data-stu-id="bb5e3-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="bb5e3-116">2</span><span class="sxs-lookup"><span data-stu-id="bb5e3-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="bb5e3-117">3</span><span class="sxs-lookup"><span data-stu-id="bb5e3-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="bb5e3-118">4</span><span class="sxs-lookup"><span data-stu-id="bb5e3-118">4</span></span>     |

## <a name="notes"></a><span data-ttu-id="bb5e3-119">참고</span><span class="sxs-lookup"><span data-stu-id="bb5e3-119">Notes</span></span>

1. <span data-ttu-id="bb5e3-120">`int32` 및 `int64`에 대 한 표준 인코딩은 서명 된 값으로 작업할 때 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-120">The standard encoding for `int32` and `int64` is inefficient when working with signed values.</span></span> <span data-ttu-id="bb5e3-121">필드에 음수가 포함 될 가능성이 있는 경우 대신 `sint32` 또는 `sint64`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="bb5e3-122">두 형식은 각각 C# `int` 및 `long` 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-122">Both types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="bb5e3-123">`fixed` 필드는 값에 관계 없이 항상 동일한 바이트 수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="bb5e3-124">이 동작을 사용 하면 더 큰 값에 대해 serialization 및 deserialization 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="bb5e3-125">Protobuf 문자열은 UTF-8 (또는 7 비트 ASCII)로 인코딩되고 인코딩된 길이는 2<sup>32</sup>보다 클 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded, and the encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="bb5e3-126">Protobuf 런타임은 C# `byte[]` 배열과 쉽게 매핑되는 `ByteString` 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-126">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="bb5e3-127">기타 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-127">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="bb5e3-128">날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="bb5e3-128">Dates and times</span></span>

<span data-ttu-id="bb5e3-129">네이티브 스칼라 형식은 <xref:System.DateTimeOffset>, <xref:System.DateTime>및 <xref:System.TimeSpan>와 동일한 C#날짜 및 시간 값을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-129">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="bb5e3-130">이러한 형식은 Google의 "잘 알려진 형식" 확장 중 일부를 사용 하 여 지정할 수 있습니다 .이 확장은 지원 되는 플랫폼에서 보다 복잡 한 필드 형식에 대 한 코드 생성 및 런타임 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-130">These types can be specified using some of Google's "Well Known Types" extensions, which provide code generation and runtime support for more complex field types across the supported platforms.</span></span> <span data-ttu-id="bb5e3-131">다음 표에서는 날짜 및 시간 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-131">The following table shows the date and time types:</span></span>

| <span data-ttu-id="bb5e3-132">C# 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-132">C# type</span></span> | <span data-ttu-id="bb5e3-133">Protobuf 잘 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-133">Protobuf well-known type</span></span> |
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

<span data-ttu-id="bb5e3-134">C# 클래스에서 생성 된 속성은 .net 날짜 및 시간 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-134">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="bb5e3-135">속성은 `DateTimeOffset`, `DateTime`및 `TimeSpan`로 변환 하는 메서드를 제공 하는 `Google.Protobuf.WellKnownTypes` 네임 스페이스의 `Timestamp` 및 `Duration` 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-135">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace, which provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="bb5e3-136">`Timestamp` 형식은 UTC 시간으로 작동 합니다. `DateTimeOffset` 값의 오프셋은 항상 0 이며 `DateTime.Kind` 속성은 항상 `DateTimeKind.Utc`됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-136">The `Timestamp` type works with UTC times; `DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property will always be `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="bb5e3-137">System.Guid</span><span class="sxs-lookup"><span data-stu-id="bb5e3-137">System.Guid</span></span>

<span data-ttu-id="bb5e3-138">다른 플랫폼에서 `UUID` 이라고 하는 <xref:System.Guid> 형식은 Protobuf에서 직접 지원 되지 않으며 잘 알려진 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-138">The <xref:System.Guid> type, known as `UUID` on other platforms, isn't directly supported by Protobuf and there's no well-known type for it.</span></span> <span data-ttu-id="bb5e3-139">가장 좋은 방법은 모든 언어 및 플랫폼에서 구문 분석할 수 있는 표준 `8-4-4-4-12` 16 진수 형식 (예: `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`)을 사용 하 여 `Guid` 값을 `string` 필드로 처리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-139">The best approach is to handle `Guid` values as `string` field, using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), which can be parsed by all languages and platforms.</span></span> <span data-ttu-id="bb5e3-140">Endian 관련 문제로 인해 Java와 같은 다른 플랫폼과 상호 작용할 때 비정상적인 동작이 발생할 수 있으므로 `Guid` 값에는 `bytes` 필드를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-140">Don't use a `bytes` field for `Guid` values, as problems with endianness can result in erratic behavior when interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="bb5e3-141">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-141">Nullable types</span></span>

<span data-ttu-id="bb5e3-142">Protobuf에 대 한 C# 코드 생성은 `int32``int`와 같은 네이티브 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-142">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="bb5e3-143">이는 값이 항상 포함 되 고 null 일 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-143">This means that the values are always included and can't be null.</span></span> <span data-ttu-id="bb5e3-144">C# 코드에 `int?`를 사용 하는 것과 같이 명시적 null이 필요한 값의 경우 Protobuf의 "잘 알려진 형식"은 nullable C# 형식으로 컴파일되는 래퍼를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-144">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="bb5e3-145">이를 사용 하려면 다음과 같이 `.proto` 파일에 `wrappers.proto`를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-145">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="bb5e3-146">Protobuf는 생성 된 메시지 속성에 단순 `T?` (예: `int?`)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-146">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="bb5e3-147">다음 표에서는 해당 C# 형식이 있는 래퍼 형식의 전체 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-147">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="bb5e3-148">C# 형식</span><span class="sxs-lookup"><span data-stu-id="bb5e3-148">C# type</span></span>   | <span data-ttu-id="bb5e3-149">잘 알려진 형식 래퍼</span><span class="sxs-lookup"><span data-stu-id="bb5e3-149">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="bb5e3-150">잘 알려진 형식 `Timestamp` 및 `Duration`은 .NET에서 클래스로 표현 되므로 nullable 버전이 필요 하지 않지만 `DateTimeOffset` 또는 `TimeSpan`변환할 때 이러한 형식의 속성에서 null을 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-150">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version, but it's important to check for null on properties of those types when converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="bb5e3-151">소수 자릿수</span><span class="sxs-lookup"><span data-stu-id="bb5e3-151">Decimals</span></span>

<span data-ttu-id="bb5e3-152">Protobuf는 기본적으로 .NET `decimal` 형식을 지원 하지 않고 `double` 및 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-152">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="bb5e3-153">Protobuf 프로젝트에는 표준 `Decimal` 형식을 잘 알려진 형식에 추가 하는 경우를 지 원하는 언어 및 프레임 워크에 대 한 플랫폼 지원을 제공 하지만 아직 구현 되지 않은 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-153">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it, but nothing has been implemented yet.</span></span>

<span data-ttu-id="bb5e3-154">.NET 클라이언트와 서버 간의 안전한 serialization에 사용할 수 있는 `decimal` 형식을 나타내는 메시지 정의를 만들 수 있지만, 다른 플랫폼의 개발자는 사용 되는 형식을 이해 하 고 자체 처리를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-154">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers, but developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="bb5e3-155">Protobuf에 대 한 사용자 지정 10 진수 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="bb5e3-155">Creating a custom Decimal type for Protobuf</span></span>

<span data-ttu-id="bb5e3-156">매우 간단한 구현은 `currency` 필드 없이 일부 Google Api에서 사용 되는 비표준 `Money` 형식과 유사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-156">A very simple implementation could be similar to the non-standard `Money` type used by some Google APIs, without the `currency` field.</span></span>

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

<span data-ttu-id="bb5e3-157">`nanos` 필드는 `0.999_999_999`에서 `-0.999_999_999`값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-157">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="bb5e3-158">예를 들어 `decimal` 값 `1.5m` `{ units = 1, nanos = 500_000_000 }`으로 표시 되는 이유는이 예의 `nanos` 필드는 `sfixed32` 형식을 사용 하 여 큰 값 `int32` 보다 효율적으로 인코딩하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-158">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }` (this is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values).</span></span> <span data-ttu-id="bb5e3-159">`units` 필드가 음수 이면 `nanos` 필드도 음수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-159">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="bb5e3-160">`decimal` 값을 바이트 문자열로 인코딩하기 위한 다른 여러 알고리즘이 있지만,이 메시지를 이해 하는 것이 더 쉬울 뿐만 아니라 값이 다른 플랫폼의 *[endian](https://en.wikipedia.org/wiki/Endianness)* 에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-160">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is much easier to understand than any of them, and the values are not affected by *[endianness](https://en.wikipedia.org/wiki/Endianness)* on different platforms.</span></span>

<span data-ttu-id="bb5e3-161">이 형식과 BCL `decimal` 형식 간의 변환은 C# 다음과 같이 구현 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5e3-161">Conversion between this type and the BCL `decimal` type could be implemented in C# like this.</span></span>

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
> <span data-ttu-id="bb5e3-162">이와 같은 사용자 지정 유틸리티 메시지 유형을 사용할 때마다 다른 개발자가 자체 언어나 프레임 워크에서 동등한 형식으로 변환 및 변환을 구현할 수 있도록 `.proto`에 주석을 포함 **해야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="bb5e3-162">Whenever you use custom utility message types like this, you **must** document them with comments in the `.proto` so that other developers can implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bb5e3-163">[이전](protobuf-messages.md)
>[다음](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="bb5e3-163">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
