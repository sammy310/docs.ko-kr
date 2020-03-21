---
title: OperationContext 액세스
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 5a2731c7918c216221b0adcafd5c804e80f36dfb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182856"
---
# <a name="accessing-operationcontext"></a>OperationContext 액세스
이 샘플에서는 메시징 활동(및)을<xref:System.ServiceModel.Activities.Receive> <xref:System.ServiceModel.Activities.Send>사용자 지정 범위 활동과 <xref:System.ServiceModel.OperationContext.Current%2A> 함께 사용하여 나가는 메시지 또는 들어오는 메시지 내에서 사용자 지정 메시지 헤더에 액세스하고 연결하거나 검색하는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>데모  
 메시징 활동, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 메시징 활동에 확장성 지점(<xref:System.ServiceModel.Activities.ISendMessageCallback> 및 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>)을 사용하여 <xref:System.ServiceModel.OperationContext.Current%2A>에 액세스하는 방법을 보여 줍니다. 콜백은 실행 시 메시징 활동에서 선택하는 <xref:System.Activities.IExecutionProperty>의 구현으로 워크플로 런타임 내에 등록됩니다. 해당 <xref:System.Activities.IExecutionProperty> 구현과 동일한 범위의 모든 메시징 활동이 영향을 받습니다. 특히 이 샘플에서는 사용자 지정 범위 활동을 사용하여 콜백 동작을 적용합니다. 클라이언트 워크플로에서 <xref:System.ServiceModel.Activities.ISendMessageCallback>을 사용하여 워크플로의 <xref:System.Activities.WorkflowApplication.Id%2A>를 보내는 <xref:System.ServiceModel.Channels.MessageHeader>로 포함합니다. 그런 다음 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>을 사용하여 서비스에서 이 헤더를 선택하고 헤더 값을 콘솔에 출력합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 이 샘플에서는 HTTP 엔드포인트를 사용하여 워크플로 서비스를 노출합니다. 이 샘플을 실행하려면 Visual [Studio를](../../wcf/feature-details/configuring-http-and-https.md) 관리자로 실행하거나 높은 프롬프트에서 다음 명령을 실행하여 적절한 ACL을 추가해야 합니다(자세한 내용은 HTTP 및 HTTPS 구성 참조). 도메인과 사용자 이름이 대체되었는지 확인합니다.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. URL ACL이 추가되었으면 다음 단계를 사용합니다.  
  
    1. 솔루션을 빌드합니다.  
  
    2. 솔루션을 마우스 오른쪽 단추로 클릭하고 시작 프로젝트 설정을 선택하여 여러 **시작 프로젝트를**설정합니다.  
  
    3. **서비스** 및 **클라이언트를** 여러 시작 프로젝트로(해당 순서대로) 추가합니다.  
  
    4. 애플리케이션을 실행합니다. 클라이언트 콘솔에 워크플로가 두 번 실행되고 있다고 표시되고 서비스 창에는 해당 워크플로의 인스턴스 ID가 표시됩니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
