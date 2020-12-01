---
title: '방법: 리플렉션을 사용하여 형식 및 멤버 정보 가져오기'
description: System.Reflection 네임스페이스를 사용하여 리플렉션으로 형식 및 멤버 정보를 가져오는 방법에 대해 알아봅니다.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 771917bb2ae5cae56c775ae23119d5eda9701df1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266326"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="46b2e-103">방법: 리플렉션을 사용하여 형식 및 멤버 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="46b2e-103">How to: Get type and member information by using reflection</span></span>

<span data-ttu-id="46b2e-104"><xref:System.Reflection> 네임스페이스에는 형식 및 멤버에 관한 정보를 가져오는 여러 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b2e-104">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="46b2e-105">이 문서에서는 이러한 메서드 중 하나인 <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46b2e-105">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46b2e-106">자세한 내용은 [리플렉션 개요](reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46b2e-106">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="46b2e-107">예제</span><span class="sxs-lookup"><span data-stu-id="46b2e-107">Example</span></span>

<span data-ttu-id="46b2e-108">다음 예제에서는 리플렉션을 사용하여 형식 및 멤버 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46b2e-108">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="46b2e-109">참조</span><span class="sxs-lookup"><span data-stu-id="46b2e-109">See also</span></span>

- [<span data-ttu-id="46b2e-110">애플리케이션 도메인으로 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="46b2e-110">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="46b2e-111">리플렉션</span><span class="sxs-lookup"><span data-stu-id="46b2e-111">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="46b2e-112">애플리케이션 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="46b2e-112">Use application domains</span></span>](../app-domains/use.md)
