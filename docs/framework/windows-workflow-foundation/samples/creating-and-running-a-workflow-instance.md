---
title: 워크플로 인스턴스 만들기 및 실행
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: f2bdfce0b311da6dd20aac5e0fe4f5fbcd14f68a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62005305"
---
# <a name="creating-and-running-a-workflow-instance"></a>워크플로 인스턴스 만들기 및 실행
이 샘플에서는 워크플로 인스턴스를 실행하는 방법을 보여 줍니다. 동기적 실행 방법과 비동기적 실행 방법을 모두 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>토론  
 샘플의 첫 번째 부분에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용합니다. 이는 워크플로를 실행하는 가장 기본적인 방법입니다. <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용할 경우 워크플로를 동기적으로 실행할 수 있습니다.  
  
 샘플의 다음 부분에서는 <xref:System.Activities.WorkflowApplication> 클래스를 사용합니다. <xref:System.Activities.WorkflowApplication> 클래스를 사용하면 실행 중인 워크플로와 상호 작용하고 워크플로를 비동기적으로 실행하는 등 각 인스턴스를 보다 효과적으로 제어할 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>참고자료

- [WorkflowInvoker 및 WorkflowApplication 사용](../using-workflowinvoker-and-workflowapplication.md)
