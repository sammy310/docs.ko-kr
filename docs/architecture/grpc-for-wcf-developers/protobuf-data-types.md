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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="2ab21-103">Protobuf 스칼라 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2ab21-103">Protobuf scalar data types</span></span>

<span data-ttu-id="2ab21-104">프로토콜 버퍼(Protobuf)는 다양한 네이티브 스칼라 값 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="2ab21-105">다음 표에는 해당 C# 형식이 모두 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="2ab21-106">프로토부타입</span><span class="sxs-lookup"><span data-stu-id="2ab21-106">Protobuf type</span></span> | <span data-ttu-id="2ab21-107">C# 형식</span><span class="sxs-lookup"><span data-stu-id="2ab21-107">C# type</span></span>      | <span data-ttu-id="2ab21-108">메모</span><span class="sxs-lookup"><span data-stu-id="2ab21-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="2ab21-109">1</span><span class="sxs-lookup"><span data-stu-id="2ab21-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="2ab21-110">1</span><span class="sxs-lookup"><span data-stu-id="2ab21-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="2ab21-111">1</span><span class="sxs-lookup"><span data-stu-id="2ab21-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="2ab21-112">1</span><span class="sxs-lookup"><span data-stu-id="2ab21-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="2ab21-113">2</span><span class="sxs-lookup"><span data-stu-id="2ab21-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="2ab21-114">2</span><span class="sxs-lookup"><span data-stu-id="2ab21-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="2ab21-115">2</span><span class="sxs-lookup"><span data-stu-id="2ab21-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="2ab21-116">2</span><span class="sxs-lookup"><span data-stu-id="2ab21-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="2ab21-117">3</span><span class="sxs-lookup"><span data-stu-id="2ab21-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="2ab21-118">4</span><span class="sxs-lookup"><span data-stu-id="2ab21-118">4</span></span>     |

<span data-ttu-id="2ab21-119">참고:</span><span class="sxs-lookup"><span data-stu-id="2ab21-119">Notes:</span></span>

1. <span data-ttu-id="2ab21-120">서명된 값으로 `int32` `int64` 작업할 때 표준 인코딩이 비효율적이며 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="2ab21-121">필드에 음수가 포함될 가능성이 있는 `sint32` 경우 `sint64` 사용하거나 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="2ab21-122">이러한 형식은 각각 `int` C# 및 `long` 유형에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="2ab21-123">`fixed` 필드는 항상 값에 관계없이 동일한 바이트 수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="2ab21-124">이 동작은 더 큰 값에 대해 직렬화 및 직렬화를 더 빠르게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="2ab21-125">프로토부프 문자열은 UTF-8(또는 7비트 ASCII)으로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="2ab21-126">인코딩된 길이는 2<sup>32보다</sup>클 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="2ab21-127">Protobuf 런타임은 `ByteString` C# `byte[]` 배열과 쉽게 매핑되는 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="2ab21-128">기타 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="2ab21-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="2ab21-129">날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="2ab21-129">Dates and times</span></span>

<span data-ttu-id="2ab21-130">네이티브 스칼라 형식은 날짜 및 시간 값(C#의 및 <xref:System.DateTimeOffset> <xref:System.DateTime> <xref:System.TimeSpan>에 해당)을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="2ab21-131">Google의 '잘 알려진 유형' 광고 확장을 사용하여 이러한 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="2ab21-132">이러한 확장은 지원되는 플랫폼 전체에서 복잡한 필드 형식에 대한 코드 생성 및 런타임 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="2ab21-133">다음 표에서는 날짜 및 시간 유형을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="2ab21-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="2ab21-134">C# 형식</span><span class="sxs-lookup"><span data-stu-id="2ab21-134">C# type</span></span> | <span data-ttu-id="2ab21-135">프로토부프 잘 알려진 타입</span><span class="sxs-lookup"><span data-stu-id="2ab21-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="2ab21-136">C# 클래스에서 생성된 속성은 .NET 날짜 및 시간 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="2ab21-137">속성은 네임스페이스에서 `Timestamp` 및 `Duration` 클래스를 `Google.Protobuf.WellKnownTypes` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="2ab21-138">이러한 클래스는 에서 `DateTimeOffset` `DateTime`및 에서 변환하는 `TimeSpan`메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="2ab21-139">형식은 `Timestamp` UTC 시간과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="2ab21-140">`DateTimeOffset`값은 항상 오프셋이 0이고 속성은 `DateTime.Kind` 항상 `DateTimeKind.Utc`입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="2ab21-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="2ab21-141">System.Guid</span></span>

<span data-ttu-id="2ab21-142">Protobuf는 다른 플랫폼에서 <xref:System.Guid> 알려진 `UUID` 형식을 직접 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="2ab21-143">잘 알려진 유형은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-143">There's no well-known type for it.</span></span>

<span data-ttu-id="2ab21-144">가장 좋은 방법은 `Guid` 표준 `string` `8-4-4-4-12` 헥사데피말 형식(예: `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`)을 사용하여 값을 필드로 처리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="2ab21-145">모든 언어와 플랫폼은 해당 형식을 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="2ab21-146">`Guid` 값에 `bytes` 필드를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2ab21-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="2ab21-147">Protobuf가 Java와 같은 다른 플랫폼과 상호 작용할 때 *endianness(위키백과* [정의)에](https://en.wikipedia.org/wiki/Endianness)문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="2ab21-148">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="2ab21-148">Nullable types</span></span>

<span data-ttu-id="2ab21-149">C#에 대한 Protobuf 코드 생성은 `int` 에 `int32`대한 네이티브 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="2ab21-150">따라서 값은 항상 포함되며 null이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="2ab21-151">C# 코드에서 사용하는 `int?` 것과 같이 명시적 null이 필요한 값의 경우 Protobuf의 "잘 알려진 형식"에는 nullable C# 유형으로 컴파일되는 래퍼가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="2ab21-152">이를 사용하려면 `wrappers.proto` 다음과 `.proto` 같이 파일로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="2ab21-153">Protobuf는 생성된 `T?` 메시지 속성에 `int?`대해 단순(예: )을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="2ab21-154">다음 표에서는 동등한 C# 형식을 가진 래퍼 유형의 전체 목록을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="2ab21-155">C# 형식</span><span class="sxs-lookup"><span data-stu-id="2ab21-155">C# type</span></span>   | <span data-ttu-id="2ab21-156">잘 알려진 타입 래퍼</span><span class="sxs-lookup"><span data-stu-id="2ab21-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="2ab21-157">잘 알려진 `Timestamp` 형식과 `Duration` .NET에서 클래스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="2ab21-158">C# 8 이상에서는 nullable 참조 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="2ab21-159">그러나 `DateTimeOffset` 변환 할 `TimeSpan`때 해당 형식의 속성에 null을 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="2ab21-160">10진수</span><span class="sxs-lookup"><span data-stu-id="2ab21-160">Decimals</span></span>

<span data-ttu-id="2ab21-161">Protobuf는 기본적으로 .NET `decimal` 형식을 지원하지 `double` `float`않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="2ab21-162">Protobuf 프로젝트에서는 잘 알려진 형식에 표준 `Decimal` 형식을 추가할 가능성에 대해 지속적으로 논의하고 있으며 이를 지원하는 언어 및 프레임워크에 대한 플랫폼 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="2ab21-163">아직 구현된 것은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="2ab21-164">.NET 클라이언트와 서버 간에 안전한 `decimal` 직렬화를 위해 작동하는 형식을 나타내는 메시지 정의를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="2ab21-165">그러나 다른 플랫폼의 개발자는 사용 중인 형식을 이해하고 해당 형식에 대한 자체 처리를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="2ab21-166">프로토부프에 대한 사용자 지정 소수점 만들기</span><span class="sxs-lookup"><span data-stu-id="2ab21-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="2ab21-167">간단한 구현은 필드 없이 일부 `Money` Google API가 사용하는 비표준 `currency` 형식과 유사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="2ab21-168">`nanos` 필드는 에서 `0.999_999_999` 값을 `-0.999_999_999`나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="2ab21-169">예를 들어 `decimal` 값은 `1.5m` 로 `{ units = 1, nanos = 500_000_000 }`표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="2ab21-170">이 예제의 `nanos` 필드는 큰 값보다 `sfixed32` `int32` 더 효율적으로 인코딩하는 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="2ab21-171">필드가 `units` 음수이면 `nanos` 필드도 음수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="2ab21-172">값을 바이트 문자열로 인코딩하기 `decimal` 위한 다른 알고리즘이 여러 개 있지만 이 메시지는 그 어떤 알고리즘보다 이해하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="2ab21-173">값은 다른 플랫폼의 endianness의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="2ab21-174">이 형식과 BCL `decimal` 형식 간의 변환은 다음과 같이 C#에서 구현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="2ab21-175">이와 같은 사용자 지정 메시지 유형을 사용할 때마다 `.proto`의 주석으로 *문서화해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="2ab21-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="2ab21-176">그런 다음 다른 개발자는 해당 언어 또는 프레임워크에서 해당 형식으로 변환을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab21-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2ab21-177">[이전](protobuf-messages.md)
>[다음](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="2ab21-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
