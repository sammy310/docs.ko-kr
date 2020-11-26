---
title: 절차적 워크플로
description: Workflow Foundation에서 절차적 워크플로는 절차적 언어에서와 비슷한 흐름 제어 방법을 사용 합니다.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 13d1b5e55b84687e2a78db1a94317b8b1e33328c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246032"
---
# <a name="procedural-workflows"></a>절차적 워크플로

절차적 워크플로에서는 절차적 언어에서 사용되는 것과 비슷한 흐름 제어 메서드를 사용합니다. 이러한 구조에는 `While` 및 `If`가 포함됩니다. <xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Sequence>와 같은 다른 흐름 제어 활동을 사용하여 이러한 워크플로를 자유롭게 구성할 수 있습니다.  
  
## <a name="controlling-execution-flow"></a>실행 흐름 제어  

 워크플로 활동 라이브러리에는 절차적 언어에서 사용되는 대부분의 흐름 제어 메서드를 모델링하기 위한 활동이 있습니다. 여기에는 다음이 포함됩니다.  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 흐름 제어 활동을 사용 하려면 **활동** 도구 상자에서 디자이너 창 내부의 복합 활동으로 끌어 놓습니다.  
  
> [!NOTE]
> Windows Server AppFabric의 호스팅 기능을 사용 하 여 웹 팜에서 워크플로를 호스트 하는 경우 AppFabric은 여러 AppFabric 서버 간에 인스턴스를 이동 합니다. 이 경우 모든 노드 간에 리소스가 공유될 수 있어야 합니다.  기본 NET 4 워크플로 활동 중 어떤 활동도 로컬 리소스에 액세스하는 작업을 포함하지 않습니다. AppFabric은 워크플로를 이동 불가능으로 표시하는 어떠한 메커니즘도 제공하지 않으므로 개발자는 워크플로가 이동할 때 실패할 수 있는 사용자 지정 활동을 만들지 않아야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [순서도 워크플로](flowchart-workflows.md)
