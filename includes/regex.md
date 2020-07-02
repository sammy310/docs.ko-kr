---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802855"
---

> [!WARNING]
> <xref:System.Text.RegularExpressions>를 사용하여 신뢰할 수 없는 입력을 처리하는 경우 시간 제한을 전달합니다. 악의적인 사용자가 `RegularExpressions`에 대한 입력을 제공하여 [서비스 거부 공격](https://www.us-cert.gov/ncas/tips/ST04-015)을 일으킬 수 있습니다. `RegularExpressions`를 사용하는 ASP.NET Core Framework API는 시간 제한을 전달합니다.
