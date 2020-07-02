---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620339"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기를 만드는 데 사용할 수 없습니다.

#### <a name="details"></a>설명

.NET Framework 4.5부터 MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기(<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 개체)를 만드는 데 사용할 수 없습니다. MEF 카탈로그를 serialize하려고 하면 예외가 throw됩니다.

#### <a name="suggestion"></a>제안 해결 방법

직렬 변환기를 만드는데 MEF를 더 이상 사용할 수 없음

| 이름    | 값       |
|:--------|:------------|
| Scope   |주요함|
|버전|4.5|
|형식|런타임|
