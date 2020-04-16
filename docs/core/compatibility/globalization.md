---
title: 세계화 관련 호환성이 손상되는 변경
description: .NET Core의 세계화 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 04/07/2020
ms.openlocfilehash: 1436f9e2ec540b0f8b1e710b25c2115646d4e5b4
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888173"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="bf26f-103">세계화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="bf26f-103">Globalization breaking changes</span></span>

<span data-ttu-id="bf26f-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf26f-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="bf26f-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="bf26f-105">Breaking change</span></span> | <span data-ttu-id="bf26f-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bf26f-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="bf26f-107">StringInfo 및 TextElementEnumerator가 이제 UAX29 규격임</span><span class="sxs-lookup"><span data-stu-id="bf26f-107">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="bf26f-108">5.0</span><span class="sxs-lookup"><span data-stu-id="bf26f-108">5.0</span></span> |
| [<span data-ttu-id="bf26f-109">“C” 로캘이 고정 로캘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf26f-109">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="bf26f-110">3.0</span><span class="sxs-lookup"><span data-stu-id="bf26f-110">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="bf26f-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="bf26f-111">.NET 5.0</span></span>

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="bf26f-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bf26f-112">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
