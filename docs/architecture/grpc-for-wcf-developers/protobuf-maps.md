---
title: 사전에 대 한 Protobuf 지도-WCF 개발자를 위한 gRPC
description: Protobuf maps를 사용 하 여를 나타내는 방법을 알아봅니다. NET의 사전 형식입니다.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: aef6b0f378e7a63f362ec42642cae15b32d49a08
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841452"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="47fca-103">사전용 Protobuf 맵</span><span class="sxs-lookup"><span data-stu-id="47fca-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="47fca-104">메시지에 있는 명명 된 값의 컬렉션을 나타낼 수 있는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="47fca-105">.NET에서는 일반적으로 사전 형식을 사용 하 여 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-105">In .NET this is commonly handled using dictionary types.</span></span> <span data-ttu-id="47fca-106">Protobuf는 .NET <xref:System.Collections.Generic.IDictionary%602> 형식에 해당 하는 `map<key_type, value_type>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-106">Protobuf's equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="47fca-107">이 섹션에서는 Protobuf에서 `map`를 선언 하는 방법과 생성 된 코드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-107">This section shows how to declare a `map` in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="47fca-108">생성 된 코드에서 `map` 필드는 <xref:System.Collections.Generic.IDictionary%602>를 포함 하 여 표준 .NET 컬렉션 인터페이스를 구현 하는 `Google.Protobuf.Collections.MapField<TKey, TValue>` 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class, which implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="47fca-109">맵 필드는 메시지 정의에서 직접 반복할 수 없지만 다음 예제와 같이 맵을 포함 하는 중첩 된 메시지를 만들고 메시지 유형에 `repeated`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-109">Map fields can't be directly repeated in a message definition, but you can create a nested message containing a map and use `repeated` on the message type, like in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="47fca-110">코드에서 MapField 속성 사용</span><span class="sxs-lookup"><span data-stu-id="47fca-110">Using MapField properties in code</span></span>

<span data-ttu-id="47fca-111">`map` 필드에서 생성 된 `MapField` 속성은 읽기 전용 이며 `null`되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-111">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="47fca-112">Map 속성을 설정 하려면 empty `MapField` 속성에 `Add(IDictionary<TKey,TValue> values)` 메서드를 사용 하 여 .NET 사전의 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="47fca-112">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="47fca-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="47fca-113">Further reading</span></span>

<span data-ttu-id="47fca-114">Protobuf에 대 한 자세한 내용은 공식 [Protobuf 설명서](https://developers.google.com/protocol-buffers/docs/overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47fca-114">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="47fca-115">[이전](protobuf-enums.md)
>[다음](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="47fca-115">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
