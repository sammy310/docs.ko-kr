---
title: 사전에 대 한 Protobuf 지도-WCF 개발자를 위한 gRPC
description: Protobuf maps를 사용 하 여 .NET에서 사전 형식을 나타내는 방법을 알아봅니다.
ms.date: 12/15/2020
ms.openlocfilehash: d38270d4bc320cf1f758080c18843ed1d716b350
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938548"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="898e4-103">사전용 Protobuf 맵</span><span class="sxs-lookup"><span data-stu-id="898e4-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="898e4-104">메시지에 있는 명명 된 값의 컬렉션을 나타낼 수 있는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="898e4-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="898e4-105">.NET에서이 활동은 일반적으로 사전 유형을 통해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="898e4-105">In .NET, this activity is commonly handled through dictionary types.</span></span> <span data-ttu-id="898e4-106"><xref:System.Collections.Generic.IDictionary%602>프로토콜 버퍼의 .net 형식 (Protobuf)에 해당 하는 값은 `map<key_type, value_type>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="898e4-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="898e4-107">이 섹션에서는 Protobuf에서 형식을 선언 하는 방법과 생성 된 코드를 사용 하는 방법을 보여 줍니다 `map` .</span><span class="sxs-lookup"><span data-stu-id="898e4-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="898e4-108">생성 된 코드에서 `map` 필드는 형식의 읽기 전용 속성으로 표시 됩니다 [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] .</span><span class="sxs-lookup"><span data-stu-id="898e4-108">In the generated code, `map` fields are represented by read-only properties of the [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] type.</span></span> <span data-ttu-id="898e4-109">이 형식은를 비롯 한 표준 .NET 컬렉션 인터페이스를 구현 <xref:System.Collections.Generic.IDictionary%602> 합니다.</span><span class="sxs-lookup"><span data-stu-id="898e4-109">This type implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="898e4-110">맵 필드는 메시지 정의에서 직접 반복할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="898e4-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="898e4-111">그러나 `repeated` 다음 예제와 같이 맵을 포함 하 고 메시지 유형에 서를 사용 하는 중첩 된 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="898e4-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="898e4-112">코드에서 MapField 속성 사용</span><span class="sxs-lookup"><span data-stu-id="898e4-112">Using MapField properties in code</span></span>

<span data-ttu-id="898e4-113">`MapField`필드에서 생성 된 속성은 `map` 읽기 전용 이며이는 그렇지 않습니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="898e4-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="898e4-114">Map 속성을 설정 하려면 `Add(IDictionary<TKey,TValue> values)` empty 속성의 메서드를 사용 하 여 `MapField` .net 사전의 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="898e4-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="898e4-115">추가 참고 자료</span><span class="sxs-lookup"><span data-stu-id="898e4-115">Further reading</span></span>

<span data-ttu-id="898e4-116">Protobuf에 대 한 자세한 내용은 공식 [Protobuf 설명서](https://developers.google.com/protocol-buffers/docs/overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="898e4-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
><span data-ttu-id="898e4-117">[이전](protobuf-enums.md)
>[다음](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="898e4-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
