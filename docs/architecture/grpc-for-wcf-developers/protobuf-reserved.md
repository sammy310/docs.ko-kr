---
title: Protobuf 예약 필드-WCF 개발자를 위한 gRPC
description: 버전 간 호환성을 위해 예약 된 필드에 대해 알아봅니다.
ms.date: 12/15/2020
ms.openlocfilehash: d82043d619c5b3b81091ae4ea381e4778c1cf6ba
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938522"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="20f4c-103">Protobuf 예약된 필드</span><span class="sxs-lookup"><span data-stu-id="20f4c-103">Protobuf reserved fields</span></span>

<span data-ttu-id="20f4c-104">Protobuf (프로토콜 버퍼)의 이전 버전과의 호환성 보장은 항상 동일한 데이터 항목을 나타내는 필드 번호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f4c-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="20f4c-105">새 버전의 서비스에 있는 메시지에서 필드를 제거 하는 경우 해당 필드 번호를 다시 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20f4c-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="20f4c-106">키워드를 사용 하 여이 동작을 적용할 수 있습니다 `reserved` .</span><span class="sxs-lookup"><span data-stu-id="20f4c-106">You can enforce this behavior by using the `reserved` keyword.</span></span>

<span data-ttu-id="20f4c-107">앞에서 `displayName` `marketId` 정의한 메시지에서 및 필드가 제거 된 경우 `Stock` 다음 예제와 같이 해당 필드 번호를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20f4c-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="20f4c-108">`reserved`키워드를 나중에 추가할 수 있는 필드에 대 한 자리 표시자로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f4c-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="20f4c-109">키워드를 사용 하 여 연속 필드 번호를 범위로 표현할 수 있습니다 `to` .</span><span class="sxs-lookup"><span data-stu-id="20f4c-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="20f4c-110">[이전](protobuf-repeated.md)
>[다음](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="20f4c-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
