---
title: 목록 및 배열에 대 한 반복 되는 필드-WCF 개발자를 위한 gRPC
description: Protobuf에서 컬렉션을 처리 하는 방법과 .NET 컬렉션과의 관계를 이해 합니다.
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867505"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="d6775-103">목록 및 배열을 위한 반복 필드</span><span class="sxs-lookup"><span data-stu-id="d6775-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="d6775-104">Prefix 키워드를 사용 하 여 프로토콜 버퍼 (Protobuf)에서 목록을 지정 `repeated` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6775-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="d6775-105">다음 예에서는 목록을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6775-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="d6775-106">생성 된 코드에서 `repeated` 필드는 [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] 기본 제공 .net 컬렉션 형식이 아닌 형식의 읽기 전용 속성으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6775-106">In the generated code, `repeated` fields are represented by read-only properties of the [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="d6775-107">이 형식은 및 등의 모든 표준 .NET 컬렉션 인터페이스를 구현 <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IEnumerable%601> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6775-107">This type implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="d6775-108">따라서 LINQ 쿼리를 사용 하거나 배열이 나 목록으로 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6775-108">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

<span data-ttu-id="d6775-109">이 `RepeatedField<T>` 형식에는 목록을 이진 통신 형식으로 serialize 및 deserialize 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6775-109">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span>

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
><span data-ttu-id="d6775-110">[이전](protobuf-nested-types.md)
>[다음](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="d6775-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
