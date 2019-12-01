---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567749"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>HttpRequestMessage.Version의 기본값은 1.1로 변경되었습니다.

<xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성의 기본값은 2.0에서 1.1로 변경되었습니다.

#### <a name="version-introduced"></a>도입된 버전

.NET Core 3.0

#### <a name="change-description"></a>변경 내용 설명

.NET Core 1.0 ~ 2.0에서 <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성의 기본값은 1.1입니다. .NET Core 2.1부터 2.1로 변경되었습니다.

.NET Core 3.0부터 <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성에 의해 반환되는 기본 버전 번호는 다시 1.1입니다.

#### <a name="recommended-action"></a>권장 작업

2\.0 기본값을 반환하는 <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성에 따라 달라지는 경우 코드를 업데이트합니다.

#### <a name="category"></a>범주

네트워킹

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

