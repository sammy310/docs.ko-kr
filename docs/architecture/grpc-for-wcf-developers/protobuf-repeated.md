---
title: 목록 및 배열에 대 한 반복 되는 필드-WCF 개발자를 위한 gRPC
description: Protobuf에서 컬렉션을 처리 하는 방법과 .NET 컬렉션과의 관계를 이해 합니다.
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542961"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="6ba9f-103">목록 및 배열을 위한 반복 필드</span><span class="sxs-lookup"><span data-stu-id="6ba9f-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="6ba9f-104">`repeated` prefix 키워드를 사용 하 여 프로토콜 버퍼 (Protobuf)에서 목록을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba9f-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="6ba9f-105">다음 예에서는 목록을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ba9f-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="6ba9f-106">생성 된 코드에서 `repeated` 필드는 기본 제공 .NET 컬렉션 형식이 아닌 `Google.Protobuf.Collections.RepeatedField<T>` 제네릭 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba9f-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> 

<span data-ttu-id="6ba9f-107">`RepeatedField<T>` 형식에는 목록을 이진 통신 형식으로 serialize 및 deserialize 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba9f-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="6ba9f-108"><xref:System.Collections.Generic.IList%601> 및 <xref:System.Collections.Generic.IEnumerable%601>와 같은 모든 표준 .NET 컬렉션 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba9f-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="6ba9f-109">따라서 LINQ 쿼리를 사용 하거나 배열이 나 목록으로 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba9f-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6ba9f-110">[이전](protobuf-nested-types.md)
>[다음](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="6ba9f-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
