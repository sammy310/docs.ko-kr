---
title: Variant 형식의 Protobuf Any 및 중 필드-WCF 개발자를 위한 gRPC
description: 모든 형식 및 중 키워드를 사용 하 여 메시지에서 variant 개체 형식을 나타내는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543198"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="0562c-103">Variant 형식에 대 한 Protobuf Any 및 중 필드</span><span class="sxs-lookup"><span data-stu-id="0562c-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="0562c-104">WCF (Windows Communication Foundation)에서 동적 속성 형식 (`object`형식의 속성)을 처리 하는 것은 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-104">Handling dynamic property types (that is, properties of type `object`) in Windows Communication Foundation (WCF) is complicated.</span></span> <span data-ttu-id="0562c-105">예를 들어 serializer를 지정 하 고 [Knowntype](xref:System.Runtime.Serialization.KnownTypeAttribute) 특성을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-105">For example, you must specify serializers and provide [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes.</span></span>

<span data-ttu-id="0562c-106">프로토콜 버퍼 (Protobuf)는 둘 이상의 형식이 될 수 있는 값을 처리 하는 두 가지 간단한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-106">Protocol Buffer (Protobuf) provides two simpler options for dealing with values that might be of more than one type.</span></span> <span data-ttu-id="0562c-107">`Any` 형식은 알려진 Protobuf 메시지 유형을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-107">The `Any` type can represent any known Protobuf message type.</span></span> <span data-ttu-id="0562c-108">`oneof` 키워드를 사용 하 여 모든 메시지에서 필드 범위 중 하나만 설정할 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-108">And you can use the `oneof` keyword to specify that only one of a range of fields can be set in any message.</span></span>

## <a name="any"></a><span data-ttu-id="0562c-109">Any</span><span class="sxs-lookup"><span data-stu-id="0562c-109">Any</span></span>

<span data-ttu-id="0562c-110">`Any`는 Protobuf의 "잘 알려진 형식" 중 하나 이며, 지원 되는 모든 언어의 구현이 포함 된 유용한 재사용 가능 메시지 유형을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-110">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="0562c-111">`Any` 형식을 사용 하려면 `google/protobuf/any.proto` 정의를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-111">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="0562c-112">C# 코드에서 `Any` 클래스는 필드를 설정 하 고, 메시지를 추출 하 고, 형식을 확인 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-112">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="0562c-113">Protobuf의 내부 리플렉션 코드는 생성 된 각 형식에 대해 `Descriptor` 정적 필드를 사용 하 여 `Any` 필드 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-113">Protobuf's internal reflection code uses the `Descriptor` static field on each generated type to resolve `Any` field types.</span></span> <span data-ttu-id="0562c-114">`TryUnpack<T>` 메서드도 있지만에서 초기화 되지 않은 `T` 인스턴스를 만드는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-114">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails.</span></span> <span data-ttu-id="0562c-115">앞에서 설명한 대로 `Is` 메서드를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-115">It's better to use the `Is` method as shown earlier.</span></span>

## <a name="oneof"></a><span data-ttu-id="0562c-116">중</span><span class="sxs-lookup"><span data-stu-id="0562c-116">Oneof</span></span>

<span data-ttu-id="0562c-117">중 필드는 언어 기능입니다. 컴파일러는 메시지 클래스를 생성할 때 `oneof` 키워드를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-117">Oneof fields are a language feature: the compiler handles the `oneof` keyword when it generates the message class.</span></span> <span data-ttu-id="0562c-118">`oneof`를 사용 하 여 `ChangeNotification` 메시지를 지정 하는 것은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-118">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="0562c-119">`oneof` 집합 내의 필드는 전체 메시지 선언에 고유한 필드 번호를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-119">Fields within the `oneof` set must have unique field numbers in the overall message declaration.</span></span>

<span data-ttu-id="0562c-120">`oneof`사용 하는 경우 생성 C# 된 코드에는 설정 된 필드를 지정 하는 열거형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-120">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="0562c-121">열거형을 테스트 하 여 설정 된 필드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-121">You can test the enum to find which field is set.</span></span> <span data-ttu-id="0562c-122">설정 되지 않은 필드는 예외를 throw 하는 대신 `null` 또는 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-122">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="0562c-123">`oneof` 집합의 일부인 필드를 설정 하면 자동으로 집합의 다른 필드가 모두 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-123">Setting any field that's part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="0562c-124">`oneof`에서 `repeated`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-124">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="0562c-125">대신이 제한 사항을 해결 하기 위해 반복 되는 필드 또는 `oneof` 집합을 사용 하 여 중첩 된 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0562c-125">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0562c-126">[이전](protobuf-reserved.md)
>[다음](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="0562c-126">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
