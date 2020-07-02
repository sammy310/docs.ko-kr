---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616089"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load가 기호 속성을 제거하지 않음

#### <a name="details"></a>설명

워크플로 디자이너에서 .NET Framework 4.5를 대상으로 하고 <xref:System.Activities.Presentation.WorkflowDesigner.Load> 메서드를 사용하여 다시 호스트된 3.5 워크플로를 로드하면 워크플로를 저장하는 동안 <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName>가 throw됩니다.

#### <a name="suggestion"></a>제안 해결 방법

이 버그는 Workflow Designer에서 .NET Framework 4.5를 대상으로 할 때에 매니페스트되므로 `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName`를 .NET Framework 4.0로 설정하여 해결할 수 있습니다. 또는 <xref:System.Activities.Presentation.WorkflowDesigner.Load> 대신 <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> 메서드를 사용하여 워크플로를 로드하여 문제를 방지할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 주요함       |
| 버전 | 4.5         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
