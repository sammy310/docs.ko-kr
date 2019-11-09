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
# <a name="protobuf-reserved-fields"></a>Protobuf 예약된 필드

Protobuf의 이전 버전과의 호환성 보장은 항상 동일한 데이터 항목을 나타내는 필드 번호를 사용 합니다. 새 버전의 서비스에 있는 메시지에서 필드를 제거 하는 경우 해당 필드 번호를 다시 사용 하면 안 됩니다. 이는 `reserved` 키워드를 사용 하 여 적용할 수 있습니다. `displayName` 및 `marketId` 필드가 앞에서 정의한 `Stock` 메시지에서 제거 된 경우 다음 예제와 같이 해당 필드 번호를 예약 해야 합니다.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

`reserved` 키워드는 나중에 추가 될 수 있는 필드에 대 한 자리 표시자로 사용할 수도 있습니다. 연속 필드 번호는 `to` 키워드를 사용 하 여 범위로 표현할 수 있습니다.

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
