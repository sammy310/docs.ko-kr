---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009062"
---
### <a name="xml-parsing-changes"></a>XML 구문 분석 변경 내용

| Name    | 값   |
|:--------|:--------|
| Scope   | 부   |
| 버전 | 4.5.2   |
| 형식    | 런타임 |

#### <a name="details"></a>세부 정보

보안상의 이유로 XML 구문 분석 API에 다음 변경 내용이 도입되었습니다.

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType>는 <xref:System.Xml.XmlReaderSettings>가 초기화될 때 1,000만으로 설정되어 있습니다.
- 기본적으로 <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType>은 `null`으로 설정되어 있습니다.

> [!NOTE]
> <xref:System.Xml.XmlReaderSettings>는 모든 XML 파서에서 사용되므로 이 변경 내용은 <xref:System.Xml.XmlReader> 사례에 도움이 되며 다른 시나리오에도 영향을 줍니다.

#### <a name="suggestion"></a>제안 해결 방법

이전 동작으로 되돌리려면 레지스트리에서 값을 설정할 수 있습니다. `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` 레지스트리 키에 `EnableLegacyXmlSettings`라는 DWORD 값을 추가하고 해당 값을 `1`로 설정합니다. 대신 HKEY_CURRENT_USER 하이브에서 레지스트리 값을 추가할 수도 있습니다.

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

또한 <xref:System.Xml.XmlResolver>에 직접 또는 간접적으로 종속된 모든 XML API가 영향을 받습니다.

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
