---
title: 세계화 관련 호환성이 손상되는 변경
description: .NET Core의 세계화 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 04/07/2020
ms.openlocfilehash: 0c3367cb3515c6f473f53be6062b54f2e836b8c5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702328"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="2ba3d-103">세계화 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="2ba3d-103">Globalization breaking changes</span></span>

<span data-ttu-id="2ba3d-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3d-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="2ba3d-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="2ba3d-105">Breaking change</span></span> | <span data-ttu-id="2ba3d-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="2ba3d-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="2ba3d-107">Windows에서 세계화 API가 ICU 라이브러리를 사용</span><span class="sxs-lookup"><span data-stu-id="2ba3d-107">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="2ba3d-108">5.0</span><span class="sxs-lookup"><span data-stu-id="2ba3d-108">5.0</span></span> |
| [<span data-ttu-id="2ba3d-109">StringInfo 및 TextElementEnumerator가 이제 UAX29 규격임</span><span class="sxs-lookup"><span data-stu-id="2ba3d-109">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="2ba3d-110">5.0</span><span class="sxs-lookup"><span data-stu-id="2ba3d-110">5.0</span></span> |
| [<span data-ttu-id="2ba3d-111">“C” 로캘이 고정 로캘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ba3d-111">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="2ba3d-112">3.0</span><span class="sxs-lookup"><span data-stu-id="2ba3d-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="2ba3d-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2ba3d-113">.NET 5.0</span></span>

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="2ba3d-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2ba3d-114">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
