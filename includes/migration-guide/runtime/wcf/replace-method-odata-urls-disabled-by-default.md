---
ms.openlocfilehash: b2fcacdb02c411c4dcb12051bf0c6759faccdea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620389"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>OData URL의 Replace 메서드는 기본적으로 비활성화되어 있음

#### <a name="details"></a>설명

.NET Framework 4.5를 시작할 때 OData URL의 Replace 메서드는 기본적으로 비활성화되어 있습니다. OData Replace가 비활성화되면(기본값) Replace 기능(일반적이지 않음)을 포함한 모든 사용자 요청이 실패합니다.

#### <a name="suggestion"></a>제안 해결 방법

Replace 메서드가 필요한 경우(일반적이지 않음) 구성 설정(<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>)을 통해 다시 사용할 수 있습니다. 그러나 활성화된 Replace 메서드는 보안 취약점을 열 수 있어 신중하게 검토한 후에 사용해야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
