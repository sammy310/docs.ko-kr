---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616279"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>워크플로 XOML 정의 및 SqlTrackingService 캐시 키가 MD5에서 SHA256으로 변경됨

#### <a name="details"></a>설명

워크플로 런타임은 XOML에 정의된 워크플로 정의의 캐시를 유지합니다. 또한 SqlTrackingService는 문자열에 의해 키가 지정된 캐시를 유지합니다. 이러한 캐시는 체크섬 해시 값을 포함하는 값에 의해 키가 지정됩니다. .NET Framework 4.7.2 이전 버전에서 이 체크섬 해시는 MD5 알고리즘을 사용하여 FIPS 지원 시스템에 문제가 발생했습니다. .NET Framework 4.8부터 SHA256 알고리즘이 사용됩니다. 워크플로 런타임 및 SqlTrackingService를 시작할 때마다 값이 다시 계산되기 때문에 이 변경 내용과 호환성 문제가 없어야 합니다. 그러나 고객이 필요한 경우 레거시 해싱 알고리즘의 사용량으로 되돌릴 수 있는 쿼크를 제공했습니다.

#### <a name="suggestion"></a>제안 해결 방법

워크플로를 실행할 때 이 변경으로 인해 문제가 발생하는 경우 `AppContext` 스위치 중 하나 또는 둘 다를 설정해 보세요.

- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;를 true로 설정합니다.
- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;를 true로 설정합니다.
코드

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

또는 구성 파일(<xref:System.Workflow.Runtime.WorkflowRuntime> 개체를 만드는 애플리케이션의 구성 파일에 있어야 함):

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.8         |
| 형식    | 대상 변경 |
