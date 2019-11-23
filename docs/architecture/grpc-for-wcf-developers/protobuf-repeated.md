---
title: 목록 및 배열에 대 한 반복 되는 필드-WCF 개발자를 위한 gRPC
description: Protobuf에서 수집을 처리 하는 방법 및 이러한 컬렉션이 .NET 컬렉션과 어떻게 관련 되는지를 이해 합니다.
ms.date: 09/09/2019
ms.openlocfilehash: 17c579bc98ba62ea74b9452bdb28efd96fc51406
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967360"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="deace-103">목록 및 배열을 위한 반복 필드</span><span class="sxs-lookup"><span data-stu-id="deace-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="deace-104">목록은 `repeated` prefix 키워드를 사용 하 여 Protobuf에 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="deace-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="deace-105">다음 예에서는 목록을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="deace-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="deace-106">생성 된 코드에서 `repeated` 필드는 기본 제공 .NET 컬렉션 형식이 아닌 `Google.Protobuf.Collections.RepeatedField<T>` 제네릭 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="deace-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="deace-107">`RepeatedField<T>` 형식에는 목록을 이진 통신 형식으로 serialize 및 deserialize 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deace-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="deace-108"><xref:System.Collections.Generic.IList%601> 및 <xref:System.Collections.Generic.IEnumerable%601>와 같은 모든 표준 .NET 컬렉션 인터페이스를 구현 하므로 LINQ 쿼리를 사용 하거나 배열 또는 목록으로 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deace-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="deace-109">[이전](protobuf-nested-types.md)
>[다음](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="deace-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
