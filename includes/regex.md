---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802855"
---

> [!WARNING]
> <span data-ttu-id="782a3-101"><xref:System.Text.RegularExpressions>를 사용하여 신뢰할 수 없는 입력을 처리하는 경우 시간 제한을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="782a3-101">When using <xref:System.Text.RegularExpressions> to process untrusted input, pass a timeout.</span></span> <span data-ttu-id="782a3-102">악의적인 사용자가 `RegularExpressions`에 대한 입력을 제공하여 [서비스 거부 공격](https://www.us-cert.gov/ncas/tips/ST04-015)을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782a3-102">A malicious user can provide input to `RegularExpressions` causing a [Denial-of-Service attack](https://www.us-cert.gov/ncas/tips/ST04-015).</span></span> <span data-ttu-id="782a3-103">`RegularExpressions`를 사용하는 ASP.NET Core Framework API는 시간 제한을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="782a3-103">ASP.NET Core framework APIs that use `RegularExpressions` pass a timeout.</span></span>
