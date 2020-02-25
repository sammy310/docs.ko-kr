---
title: Protobuf 중첩 형식-WCF 개발자를 위한 gRPC
description: Protobuf 및 gRPC의 중첩 된 메시지 유형과 이러한 유형이에서 C#생성 되는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 7b9a331336ebe1ca7bc75fdd164b7b88ae4f9db2
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542848"
---
# <a name="protobuf-nested-types"></a><span data-ttu-id="eec52-103">Protobuf 중첩 형식</span><span class="sxs-lookup"><span data-stu-id="eec52-103">Protobuf nested types</span></span>

<span data-ttu-id="eec52-104">다른 클래스 C# 내에서 클래스를 선언할 수 있도록 하는 것과 마찬가지로 Protobuf (프로토콜 버퍼)를 사용 하면 다른 메시지 내에 메시지 정의를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eec52-104">Just as C# allows you to declare classes inside other classes, Protocol Buffer (Protobuf) allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="eec52-105">다음 예제에서는 중첩 된 메시지 유형을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eec52-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="eec52-106">생성 C# 된 코드에서 `Inner` 형식은 `HelloRequest` 클래스 내의 중첩 된 정적 `Types` 클래스에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eec52-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="eec52-107">[이전](protobuf-data-types.md)
>[다음](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="eec52-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
