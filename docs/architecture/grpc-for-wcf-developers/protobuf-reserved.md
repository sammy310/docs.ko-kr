---
title: 프로토부프 예약 필드 - WCF 개발자를 위한 gRPC
description: 버전 간 호환성을 위해 예약된 필드에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: bde658c671e970b7ec841d71d5b4284eb91195f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147947"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="80f8c-103">Protobuf 예약된 필드</span><span class="sxs-lookup"><span data-stu-id="80f8c-103">Protobuf reserved fields</span></span>

<span data-ttu-id="80f8c-104">프로토콜 버퍼(Protobuf)의 이전 버전과의 호환성 보장은 항상 동일한 데이터 항목을 나타내는 필드 번호에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="80f8c-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="80f8c-105">서비스의 새 버전의 메시지에서 필드가 제거된 경우 해당 필드 번호를 다시 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80f8c-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="80f8c-106">키워드를 `reserved` 사용하여 이를 인포미를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f8c-106">You can enfore this by using the `reserved` keyword.</span></span>

<span data-ttu-id="80f8c-107">앞에서 `displayName` 정의한 `marketId` `Stock` 메시지에서 및 필드가 제거된 경우 해당 필드 번호는 다음 예제와 같이 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f8c-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="80f8c-108">나중에 추가될 `reserved` 수 있는 필드의 자리 표시자로 키워드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f8c-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="80f8c-109">키워드를 사용하여 `to` 연속 필드 번호를 범위로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f8c-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="80f8c-110">[이전](protobuf-repeated.md)
>[다음](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="80f8c-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
