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
# <a name="protobuf-maps-for-dictionaries"></a>사전용 Protobuf 맵

메시지에 있는 명명 된 값의 컬렉션을 나타낼 수 있는 것이 중요 합니다. .NET에서는 일반적으로 사전 형식을 사용 하 여 처리 됩니다. Protobuf는 .NET <xref:System.Collections.Generic.IDictionary%602> 형식에 해당 하는 `map<key_type, value_type>` 형식입니다. 이 섹션에서는 Protobuf에서 `map`를 선언 하는 방법과 생성 된 코드를 사용 하는 방법을 보여 줍니다.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

생성 된 코드에서 `map` 필드는 <xref:System.Collections.Generic.IDictionary%602>를 포함 하 여 표준 .NET 컬렉션 인터페이스를 구현 하는 `Google.Protobuf.Collections.MapField<TKey, TValue>` 클래스를 사용 합니다.

맵 필드는 메시지 정의에서 직접 반복할 수 없지만 다음 예제와 같이 맵을 포함 하는 중첩 된 메시지를 만들고 메시지 유형에 `repeated`를 사용할 수 있습니다.

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>코드에서 MapField 속성 사용

`map` 필드에서 생성 된 `MapField` 속성은 읽기 전용 이며 `null`되지 않습니다. Map 속성을 설정 하려면 empty `MapField` 속성에 `Add(IDictionary<TKey,TValue> values)` 메서드를 사용 하 여 .NET 사전의 값을 복사 합니다.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>추가 정보

Protobuf에 대 한 자세한 내용은 공식 [Protobuf 설명서](https://developers.google.com/protocol-buffers/docs/overview)를 참조 하세요.

>[!div class="step-by-step"]
>[이전](protobuf-enums.md)
>[다음](wcf-services-to-grpc-comparison.md)
