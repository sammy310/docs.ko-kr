---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617208"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>System.Uri 구문 분석이 RFC 3987을 준수

#### <a name="details"></a>설명

.NET Framework 4.5에서 URI 구문 분석은 여러 방법으로 변경되었습니다. 단, 이러한 변경 내용은 .NET Framework 4.5를 대상으로 하는 코드에 영향을 줍니다. 이진 파일이 .NET Framework 4.0을 대상으로 하는 경우, 이전 동작이 관찰됩니다. .NET Framework 4.5의 URI 구문 분석 변경 내용은 다음을 포함합니다.

- URI 구문 분석은 RFC 3987의 최신 IRI 규칙에 따라 정규화 및 문자 검사를 수행합니다.
- 유니코드 정규화 형식 C는 URI의 호스트 부분에서만 수행됩니다.
- 잘못된 mailto: URI가 예외를 발생시킵니다.
- 이제 패스 세그먼트 끝의 후행 점이 유지됩니다.
- `file://` URI는 `?` 문자를 이스케이프하지 않습니다.
- 유니코드 제어 문자 `U+0080`에서 `U+009F`는 지원되지 않습니다.
- 쉼표 문자 `,` 또는 `%2c`는 자동으로 이스케이프가 해제되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

이전 .NET Framework 4.0 URI 구문 분석 의미 체계가 필요한 경우(주로 필요하지 않음) .NET Framework 4.0을 대상으로 하여 사용할 수 있습니다. 이것은 어셈블리에서 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>를 사용하거나 '프로젝트 속성' 페이지에서 Visual Studio의 프로젝트 시스템 UI를 통해 수행할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 주요함       |
| 버전 | 4.5         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
