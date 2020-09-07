---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496921"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a>WPF는 마우스를 고정할 수 있는 wisptis.exe 프로세스를 생성함

#### <a name="details"></a>설명

마우스 입력을 고정할 수 있는 <code>wisptis.exe</code>가 생성되는 문제가 4.5.2에 도입되었습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 문제에 대한 픽스는 .NET Framework 4.5.2(핫픽스 롤업 3026376)의 서비스 릴리스에서 사용하거나 .NET Framework 4.6으로 업그레이드하여 사용할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |주요함|
|버전|4.5.2|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
