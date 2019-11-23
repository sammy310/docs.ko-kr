---
title: Protobuf 예약 필드-WCF 개발자를 위한 gRPC
description: 버전 간 호환성을 위해 예약 된 필드에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: e589cd38a712ce014fa2c4d847fbde359d538dd0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967308"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="b117c-103">Protobuf 예약된 필드</span><span class="sxs-lookup"><span data-stu-id="b117c-103">Protobuf reserved fields</span></span>

<span data-ttu-id="b117c-104">Protobuf의 이전 버전과의 호환성 보장은 항상 동일한 데이터 항목을 나타내는 필드 번호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b117c-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="b117c-105">새 버전의 서비스에 있는 메시지에서 필드를 제거 하는 경우 해당 필드 번호를 다시 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b117c-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="b117c-106">이는 `reserved` 키워드를 사용 하 여 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b117c-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="b117c-107">`displayName` 및 `marketId` 필드가 앞에서 정의한 `Stock` 메시지에서 제거 된 경우 다음 예제와 같이 해당 필드 번호를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b117c-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="b117c-108">`reserved` 키워드는 나중에 추가 될 수 있는 필드에 대 한 자리 표시자로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b117c-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="b117c-109">연속 필드 번호는 `to` 키워드를 사용 하 여 범위로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b117c-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="b117c-110">[이전](protobuf-repeated.md)
>[다음](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="b117c-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
