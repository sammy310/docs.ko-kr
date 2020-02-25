---
title: 사전에 대 한 Protobuf 지도-WCF 개발자를 위한 gRPC
description: Protobuf maps를 사용 하 여 .NET에서 사전 형식을 나타내는 방법을 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: bf848bbc7e3618f6d78e280fcd85d5eb88d5cfae
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543133"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="7d6bd-103">사전용 Protobuf 맵</span><span class="sxs-lookup"><span data-stu-id="7d6bd-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="7d6bd-104">메시지에 있는 명명 된 값의 컬렉션을 나타낼 수 있는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="7d6bd-105">.NET에서이는 일반적으로 사전 형식을 통해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="7d6bd-106">Protobuf (프로토콜 버퍼)의 .NET <xref:System.Collections.Generic.IDictionary%602> 형식에 해당 하는 값은 `map<key_type, value_type>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="7d6bd-107">이 섹션에서는 Protobuf에서 `map` 형식을 선언 하는 방법과 생성 된 코드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="7d6bd-108">생성 된 코드에서 `map` 필드는 `Google.Protobuf.Collections.MapField<TKey, TValue>` 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class.</span></span> <span data-ttu-id="7d6bd-109">이 클래스는 <xref:System.Collections.Generic.IDictionary%602>을 포함 하 여 표준 .NET 컬렉션 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-109">This class implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="7d6bd-110">맵 필드는 메시지 정의에서 직접 반복할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="7d6bd-111">그러나 다음 예제와 같이 맵을 포함 하는 중첩 된 메시지를 만들고 메시지 유형에 `repeated`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="7d6bd-112">코드에서 MapField 속성 사용</span><span class="sxs-lookup"><span data-stu-id="7d6bd-112">Using MapField properties in code</span></span>

<span data-ttu-id="7d6bd-113">`map` 필드에서 생성 된 `MapField` 속성은 읽기 전용 이며 `null`되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="7d6bd-114">Map 속성을 설정 하려면 empty `MapField` 속성에 `Add(IDictionary<TKey,TValue> values)` 메서드를 사용 하 여 .NET 사전의 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="7d6bd-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7d6bd-115">Further reading</span></span>

<span data-ttu-id="7d6bd-116">Protobuf에 대 한 자세한 내용은 공식 [Protobuf 설명서](https://developers.google.com/protocol-buffers/docs/overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d6bd-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7d6bd-117">[이전](protobuf-enums.md)
>[다음](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="7d6bd-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
