---
ms.openlocfilehash: 77e9d28d79a92cf1523e4ef5779d78394b00ae80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622087"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM이 이벤트에 대해 ByRef SafeArray 매개 변수를 성공적으로 마샬링

#### <a name="details"></a>설명

.NET Framework 4.7.2 및 이전 버전에서 COM 이벤트에 대한 ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) 매개 변수가 네이티브 코드로 다시 마샬링하지 못합니다.  이 변경을 통해 이제 [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)가 성공적으로 마샬링되었습니다.<ul><li>[ x ] Quirked</li></ul>

#### <a name="suggestion"></a>제안 해결 방법

COM 이벤트에 대한 적절한 ByRef SafeArray 매개 변수 마샬링이 실행 중지될 경우 다음 구성 스위치를 애플리케이션 구성에 추가하여 이 코드를 비활성화할 수 있습니다.<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.8|
|형식|런타임|
