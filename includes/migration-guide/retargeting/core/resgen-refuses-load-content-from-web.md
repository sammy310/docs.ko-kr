---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614770"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a>Resgen에서 웹으로부터 콘텐츠 로드를 거부

#### <a name="details"></a>설명

.resx 파일에는 이진 형식의 입력이 포함될 수 있습니다. Resgen을 사용하여 신뢰할 수 없는 위치에서 다운로드한 파일을 로드하려고 하면 기본적으로 입력이 로드되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

신뢰할 수 없는 위치에서 이진 형식 입력을 로드해야 하는 Resgen 사용자는 입력 파일에서 웹 표시를 제거하거나 쿼크 옵트아웃을 적용할 수 있습니다. 컴퓨터 수준에서 쿼크 옵트아웃을 적용하려면 다음 레지스트리 설정을 추가합니다. [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |
