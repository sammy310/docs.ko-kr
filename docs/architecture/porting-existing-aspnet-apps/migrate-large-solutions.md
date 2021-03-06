---
title: ASP.NET Core에 대 한 대량 솔루션 마이그레이션
description: ASP.NET Core로 large ASP.NET MVC 앱을 마이그레이션하는 방법에 대해 살펴봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: d3ebd71213e074ce80dc83fc3230c4e365275ad3
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401729"
---
# <a name="migrate-large-solutions-to-aspnet-core"></a>ASP.NET Core에 대 한 대량 솔루션 마이그레이션

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

.NET Framework에서 .NET Core로 규모가 많은 솔루션을 마이그레이션하려면 몇 가지 계획이 필요 합니다. 종속성은 해당 종속성을 기반으로 하는 프로젝트 보다 먼저 마이그레이션하거나 업데이트 해야 합니다. 종속성을 식별 하 고 .NET Core로 마이그레이션하는 데 도움을 줄 수 있는 도구를 제공 합니다. 앱, 해당 범위 및 현재 사용 패턴에 따라 마이그레이션할 때 다양 한 전략을 사용할 수 있습니다. 모든 작업을 한 번에 또는 현재 시스템과 함께 병렬로 마이그레이션 하나요? 현재 시스템을 새 시스템으로 래핑하고 해당 기능을 증분 방식으로 바꾸시겠습니까?

이 장에서는 대량 솔루션에 대 한 마이그레이션 계획을 만드는 방법, 마이그레이션에 도움이 되는 도구를 사용 하는 방법 및 마이그레이션 자체를 고려 하는 몇 가지 전략에 대해 알아봅니다.

## <a name="references"></a>참조

- [큰 MVC 및 Web API 앱을 .NET Core로 마이그레이션하는 데 중요 한 항목은 무엇 인가요?](https://twitter.com/ardalis/status/1313669040859217921)
- [.NET Framework에서 .NET Core로 이식](../../core/porting/index.md)

>[!div class="step-by-step"]
>[이전](testing-differences.md)
>[다음](identify-migration-sequence.md)
