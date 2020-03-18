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
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="6a2ef-103">목록 및 배열을 위한 반복 필드</span><span class="sxs-lookup"><span data-stu-id="6a2ef-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="6a2ef-104">접두사 키워드를 사용하여 프로토콜 버퍼(Protobuf)의 `repeated` 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2ef-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="6a2ef-105">다음 예제에서는 목록을 만드는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2ef-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="6a2ef-106">생성된 코드에서 `repeated` 필드는 기본 제공 `Google.Protobuf.Collections.RepeatedField<T>` .NET 컬렉션 형식이 아닌 제네릭 유형으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a2ef-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span>

<span data-ttu-id="6a2ef-107">형식에는 `RepeatedField<T>` 목록을 직렬화하고 이진 와이어 형식으로 직렬화하는 데 필요한 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a2ef-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="6a2ef-108"><xref:System.Collections.Generic.IList%601> 와 <xref:System.Collections.Generic.IEnumerable%601>같은 모든 표준 .NET 컬렉션 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2ef-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="6a2ef-109">따라서 LINQ 쿼리를 사용하거나 배열 또는 목록으로 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2ef-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6a2ef-110">[이전](protobuf-nested-types.md)
>[다음](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="6a2ef-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
