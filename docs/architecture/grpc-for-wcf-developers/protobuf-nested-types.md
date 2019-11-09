---
title: Protobuf 중첩 형식-WCF 개발자를 위한 gRPC
description: Protobuf 및 gRPC의 중첩 된 메시지 유형과 이러한 유형이에서 C#생성 되는 방법에 대해 알아봅니다.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: ec9fc522619230c1201bfef1e8128f7356936212
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841404"
---
# <a name="protobuf-nested-types"></a>Protobuf 중첩 형식

마찬가지로 C# , Protobuf를 사용 하면 다른 클래스 내에서 클래스를 선언할 수 있으며,이를 통해 다른 메시지 내에 메시지 정의를 중첩할 수 있습니다. 다음 예제에서는 중첩 된 메시지 유형을 만드는 방법을 보여 줍니다.

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

생성 C# 된 코드에서 `Inner` 형식은 `HelloRequest` 클래스 내의 중첩 된 정적 `Types` 클래스에서 선언 됩니다.

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[이전](protobuf-data-types.md)
>[다음](protobuf-repeated.md)
