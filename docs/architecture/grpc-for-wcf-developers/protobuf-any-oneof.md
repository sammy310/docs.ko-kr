---
title: Variant 형식의 Protobuf Any 및 중 필드-WCF 개발자를 위한 gRPC
description: 모든 형식 및 중 키워드를 사용 하 여 메시지에서 variant 개체 형식을 나타내는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: af3ba22c238aa80a8c6119f62d5d8914770cad68
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971610"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="91979-103">Variant 형식에 대 한 Protobuf Any 및 중 필드</span><span class="sxs-lookup"><span data-stu-id="91979-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="91979-104">WCF에서 동적 속성 형식 (즉, `object`형식의 속성)을 처리 하는 것은 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="91979-105">Serializer를 지정 하 고 [Knowntype](xref:System.Runtime.Serialization.KnownTypeAttribute) 특성을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="91979-106">Protobuf는 둘 이상의 형식이 될 수 있는 값을 처리 하는 두 가지 간단한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="91979-107">`Any` 형식은 알려진 Protobuf 메시지 유형을 나타낼 수 있지만 `oneof` 키워드를 사용 하면 지정 된 메시지에서 필드 범위 중 하나만 설정할 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91979-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="91979-108">Any</span><span class="sxs-lookup"><span data-stu-id="91979-108">Any</span></span>

<span data-ttu-id="91979-109">`Any`는 Protobuf의 "잘 알려진 형식" 중 하나 이며, 지원 되는 모든 언어의 구현이 포함 된 유용한 재사용 가능 메시지 유형을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="91979-110">`Any` 형식을 사용 하려면 `google/protobuf/any.proto` 정의를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

<span data-ttu-id="91979-111">C# 코드에서 `Any` 클래스는 필드를 설정 하 고, 메시지를 추출 하 고, 형식을 확인 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="91979-112">생성 된 각 형식의 `Descriptor` 정적 필드는 Protobuf의 내부 리플렉션 코드에서 `Any` 필드 형식을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91979-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="91979-113">`TryUnpack<T>` 메서드도 있지만 `T`의 초기화 되지 않은 인스턴스를 만든 후에도 `Is` 메서드를 위에 표시 된 대로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91979-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="91979-114">중</span><span class="sxs-lookup"><span data-stu-id="91979-114">Oneof</span></span>

<span data-ttu-id="91979-115">중 필드는 언어 기능입니다. `oneof` 키워드는 메시지 클래스를 생성할 때 컴파일러에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91979-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="91979-116">`oneof`를 사용 하 여 `ChangeNotification` 메시지를 지정 하는 것은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91979-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

<span data-ttu-id="91979-117">`oneof` 집합 내의 필드는 전체 메시지 선언 내에 고유한 필드 번호를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="91979-118">`oneof`사용 하는 경우 생성 C# 된 코드에는 설정 된 필드를 지정 하는 열거형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91979-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="91979-119">열거형을 테스트 하 여 설정 된 필드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91979-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="91979-120">설정 되지 않은 필드는 예외를 throw 하는 대신 `null` 또는 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="91979-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="91979-121">`oneof` 집합의 일부인 필드를 설정 하면 자동으로 집합의 다른 필드가 모두 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="91979-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="91979-122">`oneof`에서 `repeated`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91979-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="91979-123">대신이 제한 사항을 해결 하기 위해 반복 되는 필드 또는 `oneof` 집합을 사용 하 여 중첩 된 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91979-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="91979-124">[이전](protobuf-reserved.md)
>[다음](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="91979-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
