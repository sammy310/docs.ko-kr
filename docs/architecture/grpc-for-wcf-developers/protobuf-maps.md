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
# <a name="protobuf-maps-for-dictionaries"></a>사전용 Protobuf 맵

메시지에 있는 명명 된 값의 컬렉션을 나타낼 수 있는 것이 중요 합니다. .NET에서이 활동은 일반적으로 사전 유형을 통해 처리 됩니다. <xref:System.Collections.Generic.IDictionary%602>프로토콜 버퍼의 .net 형식 (Protobuf)에 해당 하는 값은 `map<key_type, value_type>` 형식입니다. 이 섹션에서는 Protobuf에서 형식을 선언 하는 방법과 생성 된 코드를 사용 하는 방법을 보여 줍니다 `map` .

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

생성 된 코드에서 `map` 필드는 형식의 읽기 전용 속성으로 표시 됩니다 [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] . 이 형식은를 비롯 한 표준 .NET 컬렉션 인터페이스를 구현 <xref:System.Collections.Generic.IDictionary%602> 합니다.

맵 필드는 메시지 정의에서 직접 반복할 수 없습니다. 그러나 `repeated` 다음 예제와 같이 맵을 포함 하 고 메시지 유형에 서를 사용 하는 중첩 된 메시지를 만들 수 있습니다.

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>코드에서 MapField 속성 사용

`MapField`필드에서 생성 된 속성은 `map` 읽기 전용 이며이는 그렇지 않습니다 `null` . Map 속성을 설정 하려면 `Add(IDictionary<TKey,TValue> values)` empty 속성의 메서드를 사용 하 여 `MapField` .net 사전의 값을 복사 합니다.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>추가 참고 자료

Protobuf에 대 한 자세한 내용은 공식 [Protobuf 설명서](https://developers.google.com/protocol-buffers/docs/overview)를 참조 하세요.

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
>[이전](protobuf-enums.md)
>[다음](wcf-services-to-grpc-comparison.md)
