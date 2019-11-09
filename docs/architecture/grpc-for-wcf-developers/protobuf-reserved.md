---
title: Protobuf 예약 필드-WCF 개발자를 위한 gRPC
description: 버전 간 호환성을 위해 예약 된 필드에 대해 알아봅니다.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 34697371299bdc5d9a58c0696c1ce7d19816ca87
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841392"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="7f381-103">Protobuf 예약된 필드</span><span class="sxs-lookup"><span data-stu-id="7f381-103">Protobuf reserved fields</span></span>

<span data-ttu-id="7f381-104">Protobuf의 이전 버전과의 호환성 보장은 항상 동일한 데이터 항목을 나타내는 필드 번호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f381-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="7f381-105">새 버전의 서비스에 있는 메시지에서 필드를 제거 하는 경우 해당 필드 번호를 다시 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f381-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="7f381-106">이는 `reserved` 키워드를 사용 하 여 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f381-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="7f381-107">`displayName` 및 `marketId` 필드가 앞에서 정의한 `Stock` 메시지에서 제거 된 경우 다음 예제와 같이 해당 필드 번호를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f381-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="7f381-108">`reserved` 키워드는 나중에 추가 될 수 있는 필드에 대 한 자리 표시자로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f381-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="7f381-109">연속 필드 번호는 `to` 키워드를 사용 하 여 범위로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f381-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="7f381-110">[이전](protobuf-repeated.md)
>[다음](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="7f381-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
