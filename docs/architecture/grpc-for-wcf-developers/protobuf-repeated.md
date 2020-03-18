---
title: 목록 및 배열에 대한 반복 필드 - WCF 개발자를 위한 gRPC
description: Protobuf가 컬렉션을 처리하는 방법과 컬렉션이 .NET 컬렉션과 어떻게 관련되는지 이해합니다.
ms.date: 09/09/2019
ms.openlocfilehash: 63d99532d14deea7800673dd5a6350dd9362ad54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147973"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>목록 및 배열을 위한 반복 필드

접두사 키워드를 사용하여 프로토콜 버퍼(Protobuf)의 `repeated` 목록을 지정합니다. 다음 예제에서는 목록을 만드는 방법을 보여 주며 있습니다.

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

생성된 코드에서 `repeated` 필드는 기본 제공 `Google.Protobuf.Collections.RepeatedField<T>` .NET 컬렉션 형식이 아닌 제네릭 유형으로 표시됩니다.

형식에는 `RepeatedField<T>` 목록을 직렬화하고 이진 와이어 형식으로 직렬화하는 데 필요한 코드가 포함됩니다. <xref:System.Collections.Generic.IList%601> 와 <xref:System.Collections.Generic.IEnumerable%601>같은 모든 표준 .NET 컬렉션 인터페이스를 구현합니다. 따라서 LINQ 쿼리를 사용하거나 배열 또는 목록으로 쉽게 변환할 수 있습니다.

>[!div class="step-by-step"]
>[이전](protobuf-nested-types.md)
>[다음](protobuf-reserved.md)
