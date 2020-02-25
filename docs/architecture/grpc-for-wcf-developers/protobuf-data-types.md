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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="2643b-103">Protobuf 스칼라 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-103">Protobuf scalar data types</span></span>

<span data-ttu-id="2643b-104">프로토콜 버퍼 (Protobuf)는 네이티브 스칼라 값 형식의 범위를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="2643b-105">다음 표에서는 모두 해당 C# 하는 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="2643b-106">Protobuf 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-106">Protobuf type</span></span> | <span data-ttu-id="2643b-107">C# 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-107">C# type</span></span>      | <span data-ttu-id="2643b-108">참고</span><span class="sxs-lookup"><span data-stu-id="2643b-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="2643b-109">1</span><span class="sxs-lookup"><span data-stu-id="2643b-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="2643b-110">1</span><span class="sxs-lookup"><span data-stu-id="2643b-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="2643b-111">1</span><span class="sxs-lookup"><span data-stu-id="2643b-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="2643b-112">1</span><span class="sxs-lookup"><span data-stu-id="2643b-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="2643b-113">2</span><span class="sxs-lookup"><span data-stu-id="2643b-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="2643b-114">2</span><span class="sxs-lookup"><span data-stu-id="2643b-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="2643b-115">2</span><span class="sxs-lookup"><span data-stu-id="2643b-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="2643b-116">2</span><span class="sxs-lookup"><span data-stu-id="2643b-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="2643b-117">3</span><span class="sxs-lookup"><span data-stu-id="2643b-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="2643b-118">4</span><span class="sxs-lookup"><span data-stu-id="2643b-118">4</span></span>     |

<span data-ttu-id="2643b-119">참고:</span><span class="sxs-lookup"><span data-stu-id="2643b-119">Notes:</span></span>

1. <span data-ttu-id="2643b-120">부호 있는 값으로 작업 하는 경우 `int32` 및 `int64`에 대 한 표준 인코딩은 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="2643b-121">필드에 음수가 포함 될 가능성이 있는 경우 대신 `sint32` 또는 `sint64`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="2643b-122">이러한 형식은 각각 C# `int` 및 `long` 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="2643b-123">`fixed` 필드는 값에 관계 없이 항상 동일한 바이트 수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="2643b-124">이 동작을 사용 하면 더 큰 값에 대해 serialization 및 deserialization 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="2643b-125">Protobuf 문자열은 u t f-8 (또는 7 비트 ASCII)로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="2643b-126">인코딩된 길이는 2<sup>32</sup>보다 클 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="2643b-127">Protobuf 런타임은 C# `byte[]` 배열과 쉽게 매핑되는 `ByteString` 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="2643b-128">기타 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="2643b-129">날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="2643b-129">Dates and times</span></span>

<span data-ttu-id="2643b-130">네이티브 스칼라 형식은 <xref:System.DateTimeOffset>, <xref:System.DateTime>및 <xref:System.TimeSpan>와 동일한 C#날짜 및 시간 값을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="2643b-131">Google의 "잘 알려진 형식" 확장 중 일부를 사용 하 여 이러한 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="2643b-132">이러한 확장은 지원 되는 플랫폼에서 복합 필드 형식에 대 한 코드 생성 및 런타임 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span> 

<span data-ttu-id="2643b-133">다음 표에서는 날짜 및 시간 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="2643b-134">C# 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-134">C# type</span></span> | <span data-ttu-id="2643b-135">Protobuf 잘 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="2643b-136">C# 클래스에서 생성 된 속성은 .net 날짜 및 시간 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="2643b-137">속성은 `Google.Protobuf.WellKnownTypes` 네임 스페이스의 `Timestamp` 및 `Duration` 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="2643b-138">이러한 클래스는 `DateTimeOffset`, `DateTime`및 `TimeSpan`변환 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="2643b-139">`Timestamp` 형식은 UTC 시간으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="2643b-140">`DateTimeOffset` 값의 오프셋은 항상 0 이며 `DateTime.Kind` 속성은 항상 `DateTimeKind.Utc`됩니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="2643b-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="2643b-141">System.Guid</span></span>

<span data-ttu-id="2643b-142">Protobuf는 다른 플랫폼에서 `UUID` 이라고 하는 <xref:System.Guid> 형식을 직접 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="2643b-143">잘 알려진 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-143">There's no well-known type for it.</span></span> 

<span data-ttu-id="2643b-144">가장 좋은 방법은 표준 `8-4-4-4-12` 16 진수 형식 (예: `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`)을 사용 하 여 `Guid` 값을 `string` 필드로 처리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="2643b-145">모든 언어 및 플랫폼에서 해당 형식을 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="2643b-146">`Guid` 값에는 `bytes` 필드를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2643b-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="2643b-147">*Endian* ([위키백과 정의](https://en.wikipedia.org/wiki/Endianness)) 문제가 있으면 Protobuf가 Java와 같은 다른 플랫폼과 상호 작용할 때 비정상적인 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="2643b-148">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-148">Nullable types</span></span>

<span data-ttu-id="2643b-149">Protobuf에 대 한 C# 코드 생성은 `int32``int`와 같은 네이티브 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="2643b-150">따라서 값은 항상 포함 되며 null 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-150">So the values are always included and can't be null.</span></span> 

<span data-ttu-id="2643b-151">C# 코드에 `int?`를 사용 하는 것과 같이 명시적 null이 필요한 값의 경우 Protobuf의 "잘 알려진 형식"은 nullable C# 형식으로 컴파일되는 래퍼를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="2643b-152">이를 사용 하려면 다음과 같이 `.proto` 파일에 `wrappers.proto`를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="2643b-153">Protobuf는 생성 된 메시지 속성에 단순 `T?` (예: `int?`)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="2643b-154">다음 표에서는 해당 C# 형식이 있는 래퍼 형식의 전체 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="2643b-155">C# 형식</span><span class="sxs-lookup"><span data-stu-id="2643b-155">C# type</span></span>   | <span data-ttu-id="2643b-156">잘 알려진 형식 래퍼</span><span class="sxs-lookup"><span data-stu-id="2643b-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="2643b-157">잘 알려진 형식 `Timestamp` 및 `Duration`은 .NET에서 클래스로 표현 되므로 nullable 버전이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="2643b-158">그러나 `DateTimeOffset` 또는 `TimeSpan`으로 변환 하는 경우 해당 형식의 속성에 대해 null을 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="2643b-159">소수 자릿수</span><span class="sxs-lookup"><span data-stu-id="2643b-159">Decimals</span></span>

<span data-ttu-id="2643b-160">Protobuf는 기본적으로 .NET `decimal` 형식을 지원 하지 않고 `double` 및 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="2643b-161">Protobuf 프로젝트에는 표준 `Decimal` 유형을 지 원하는 언어 및 프레임 워크에 대 한 플랫폼 지원과 함께 잘 알려진 형식에 추가할 수 있는 정보에 대 한 지속적인 토론이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="2643b-162">아직 구현 된 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="2643b-163">.NET 클라이언트와 서버 간에 안전 하 게 직렬화 하는 데 사용할 수 있는 `decimal` 형식을 나타내는 메시지 정의를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="2643b-164">그러나 다른 플랫폼의 개발자는 사용 되는 형식을 이해 하 고이에 대 한 자체 처리를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="2643b-165">Protobuf에 대 한 사용자 지정 10 진수 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="2643b-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="2643b-166">간단한 구현은 `currency` 필드 없이 일부 Google Api가 사용 하는 비표준 `Money` 형식과 유사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="2643b-167">`nanos` 필드는 `0.999_999_999`에서 `-0.999_999_999`값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="2643b-168">예를 들어 `decimal` 값 `1.5m` `{ units = 1, nanos = 500_000_000 }`표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="2643b-169">이는이 예제에서 `nanos` 필드가 더 큰 값에 대해 `int32` 보다 효율적으로 인코딩하는 `sfixed32` 형식을 사용 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="2643b-170">`units` 필드가 음수 이면 `nanos` 필드도 음수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="2643b-171">`decimal` 값을 바이트 문자열로 인코딩하기 위한 다른 여러 알고리즘이 있지만,이 메시지를 보다 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="2643b-172">값은 서로 다른 플랫폼에 있는 endian의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="2643b-173">이 형식과 BCL `decimal` 형식 간의 변환은 다음과 C# 같이 구현 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="2643b-174">이와 같은 사용자 지정 메시지 유형을 사용할 때마다 `.proto`주석을 사용 하 여 문서를 작성 *해야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="2643b-175">그러면 다른 개발자가 자체 언어나 프레임 워크에서 동등한 형식으로의 변환을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2643b-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2643b-176">[이전](protobuf-messages.md)
>[다음](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="2643b-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
