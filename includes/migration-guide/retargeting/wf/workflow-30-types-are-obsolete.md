---
ms.openlocfilehash: 358103d5816eb61c88738e9626fb02c563b507f8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617248"
---
### <a name="workflow-30-types-are-obsolete"></a>워크플로 3.0 형식이 사용되지 않음

#### <a name="details"></a>설명

System.Workflow 네임스페이스의 Windows Workflow Foundation(WWF) 3.0 API는 이제 사용되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

System.Activities 새 WWF 4.0 API를 대신 사용해야 합니다. 새 API를 사용하는 예제는 [여기](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)에서 찾을 수 있으며 추가 참고 자료은 [여기](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5)에서 볼 수 있습니다. 또는 WWF 3.0 API가 계속 지원되므로 사용할 수 있으며, 빌드 시간 경고는 표시되지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 주요함       |
| 버전 | 4.5         |
| 형식    | 대상 변경 |
