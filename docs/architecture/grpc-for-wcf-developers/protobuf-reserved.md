---
title: Protobuf 예약 필드-WCF 개발자를 위한 gRPC
description: 버전 간 호환성을 위해 예약 된 필드에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542978"
---
# <a name="protobuf-reserved-fields"></a>Protobuf 예약된 필드

Protobuf (프로토콜 버퍼)의 이전 버전과의 호환성 보장은 항상 동일한 데이터 항목을 나타내는 필드 번호를 사용 합니다. 새 버전의 서비스에 있는 메시지에서 필드를 제거 하는 경우 해당 필드 번호를 다시 사용 하면 안 됩니다. `reserved` 키워드를 사용 하 여이를 수행할 수 있습니다. 

`displayName` 및 `marketId` 필드가 앞에서 정의한 `Stock` 메시지에서 제거 된 경우 다음 예제와 같이 해당 필드 번호를 예약 해야 합니다.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

`reserved` 키워드를 나중에 추가할 수 있는 필드에 대 한 자리 표시자로 사용할 수도 있습니다. `to` 키워드를 사용 하 여 연속 필드 번호를 범위로 표현할 수 있습니다.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[이전](protobuf-repeated.md)
>[다음](protobuf-any-oneof.md)
