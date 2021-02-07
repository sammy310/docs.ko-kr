---
description: '자세한 정보: WF의 상태 시스템 활동'
title: WF의 상태 시스템 활동
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 4571bdbabc30e721523ae18449454627c0bf7319
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755254"
---
# <a name="state-machine-activities-in-wf"></a>WF의 상태 시스템 활동

.NET Framework 4.5는 상태 시스템 워크플로를 만들기 위한 여러 시스템 제공 활동 및 활동 디자이너를 제공 합니다.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|익숙한 상태 시스템 패러다임을 사용하여 포함된 활동을 실행합니다.|  
|<xref:System.Activities.Statements.State>|상태 시스템의 상태를 나타냅니다.|  
|<xref:System.Activities.Core.Presentation.FinalState>|상태 시스템의 종료 상태를 나타냅니다. <xref:System.Activities.Core.Presentation.FinalState>는 사용될 경우 종료 상태로 미리 구성되는 <xref:System.Activities.Statements.State>를 만드는 활동 디자이너입니다. 자세한 내용은 [상태 활동 디자이너](/visualstudio/workflow-designer/finalstate-activity-designer)를 참조 하세요.|  
|<xref:System.Activities.Statements.Transition>|두 상태 간 전환을 나타냅니다. 에 대 한 **도구 상자** 항목이 없습니다 <xref:System.Activities.Statements.Transition> . 전환은 워크플로 디자이너에서 두 상태 사이의 선을 끌어서 놓거나 한 상태가 다른 상태를 가리킬 때 표시 되는 삼각형에 상태를 삭제 하 여 만듭니다. 자세한 내용은 [전환 활동 디자이너](/visualstudio/workflow-designer/transition-activity-designer)를 참조 하세요.|  
  
## <a name="see-also"></a>참고 항목

- [초보자를 위한 자습서](getting-started-tutorial.md)
