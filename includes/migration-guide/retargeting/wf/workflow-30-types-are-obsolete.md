---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606280"
---
### <a name="workflow-30-types-are-obsolete"></a>워크플로 3.0 형식이 사용되지 않음

#### <a name="details"></a>설명

System.Workflow 네임스페이스의 Windows Workflow Foundation(WWF) 3.0 API는 이제 사용되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

System.Activities 새 WWF 4.0 API를 대신 사용해야 합니다. 새 API를 사용하는 예제는 [여기](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)에서 찾을 수 있으며 추가 참고 자료은 [여기](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5)에서 볼 수 있습니다. 또는 WWF 3.0 API가 계속 지원되므로 사용할 수 있으며, 빌드 시간 경고는 표시되지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 주요함       |
| 버전 | 4.5         |
| 형식    | 대상 변경 |
