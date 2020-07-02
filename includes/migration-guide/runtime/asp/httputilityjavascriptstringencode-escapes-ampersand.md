---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620145"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode가 앰퍼샌드를 이스케이프합니다.

#### <a name="details"></a>설명

.NET Framework 4.5부터 <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName>이 앰퍼샌드(&amp;) 문자를 이스케이프합니다.

#### <a name="suggestion"></a>제안 해결 방법

응용 프로그램이 이 메서드의 이전 동작에 종속되는 경우 aspnet:JavaScriptDoNotEncodeAmpersand 설정을 구성 파일에 있는 [ASP.NET appSettings 요소](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120))에 추가할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
