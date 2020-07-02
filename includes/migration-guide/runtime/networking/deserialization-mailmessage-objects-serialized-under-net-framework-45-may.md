---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620346"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>.NET Framework 4.5에서 직렬화된 MailMessage 개체의 역직렬화가 실패할 수 있음

#### <a name="details"></a>설명

.NET Framework 4.5부터는 <xref:System.Web.Mail.MailMessage> 개체에 비 ASCII 문자가 포함될 수 있습니다. .NET Framework 4에서는 ASCII 문자만 지원됩니다. ASCII가 아닌 문자를 포함하고 .NET Framework 4.5 이상에서 직렬화되는 <xref:System.Web.Mail.MailMessage> 개체는 .NET Framework 4에서 역직렬화될 수 없습니다.

#### <a name="suggestion"></a>제안 해결 방법

<xref:System.Web.Mail.MailMessage> 개체를 역직렬화할 때 코드가 예외 처리를 제공하는지 확인합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
