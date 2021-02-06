---
description: '자세히 알아보기: WorkflowHostingEndpoint에 대 한 책갈피 확인자'
title: WorkflowHostingEndpoint에 대한 책갈피 확인자
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: fc2a21a33560452b141069e88b4d7ff816712d96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653812"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a>WorkflowHostingEndpoint에 대한 책갈피 확인자

이 샘플에서는 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 <xref:System.ServiceModel.Activities.WorkflowServiceHost>와 함께 사용하여 워크플로 인스턴스를 만드는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>데모  

 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>토론(Discussion)  

 이 샘플에서는 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 사용하여 워크플로 인스턴스를 만듭니다. 이 워크플로 인스턴스는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 통해 호스트됩니다. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>는 다음 시나리오에 사용할 수 있는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 대한 확장성 지점입니다.  
  
- 새 워크플로 인스턴스 만들기  
  
- <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트되는 워크플로 인스턴스에 대한 책갈피 다시 시작  
  
 여기에 포함되어 있는 샘플 엔드포인트는 워크플로를 만들고 인스턴스 ID를 반환하거나 특정 ID의 인스턴스를 만드는 작업을 제공하는 계약을 노출합니다. 샘플 콘솔 애플리케이션에서는 워크플로 정의를 사용하여 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 인스턴스를 만들고 호스트에 `CreationEndpoint`를 추가합니다. 그런 다음 엔드포인트에 대해 `Create` 작업을 호출하여 새 워크플로 인스턴스를 만듭니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 솔루션을 빌드합니다.  
  
2. 애플리케이션을 실행합니다. 워크플로 인스턴스를 만들 때 인스턴스 ID를 포함하는 메시지가 `CreationEndpoint` 콘솔에 표시됩니다. "헬로 월드!" 메시지 워크플로 인스턴스에 의해 인쇄 됩니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
