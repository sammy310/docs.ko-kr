---
ms.openlocfilehash: a9011514c7c4393ec44de2c7fae88768cdccf435
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497092"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a>.NET Framework 4.6은 레지스트리에 등록될 때 4.5.x.x 버전을 사용하지 않습니다.

#### <a name="details"></a>세부 정보

예상할 수 있듯이 .NET Framework 4.6의 레지스트리(<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>)에 설정된 버전 키는 '4.5'가 아니라 '4.6'으로 시작합니다. 이러한 레지스트리 키를 사용하여 컴퓨터에 설치된 .NET Framework 버전을 확인하는 앱은 4.6이 가능한 새 버전이고 이전 4.5.x 릴리스와 호환된다는 것을 이해하도록 업데이트되어야 합니다.

#### <a name="suggestion"></a>제안 해결 방법

4\.5 레지스트리 키를 검색하여 4.6을 수락하도록 .NET Framework 4.5 설치를 검색하는 앱을 업데이트합니다.

| Name    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.6|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
