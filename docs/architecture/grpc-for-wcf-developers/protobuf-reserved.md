---
title: 프로토부프 예약 필드 - WCF 개발자를 위한 gRPC
description: 버전 간 호환성을 위해 예약된 필드에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111038"
---
# <a name="protobuf-reserved-fields"></a>Protobuf 예약된 필드

프로토콜 버퍼(Protobuf)의 이전 버전과의 호환성 보장은 항상 동일한 데이터 항목을 나타내는 필드 번호에 의존합니다. 서비스의 새 버전의 메시지에서 필드가 제거된 경우 해당 필드 번호를 다시 사용해서는 안 됩니다. 키워드를 `reserved` 사용하여 이를 적용할 수 있습니다.

앞에서 `displayName` 정의한 `marketId` `Stock` 메시지에서 및 필드가 제거된 경우 해당 필드 번호는 다음 예제와 같이 예약해야 합니다.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

나중에 추가될 `reserved` 수 있는 필드의 자리 표시자로 키워드를 사용할 수도 있습니다. 키워드를 사용하여 `to` 연속 필드 번호를 범위로 표현할 수 있습니다.

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
