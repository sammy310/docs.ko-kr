---
title: Workflow Discovery 샘플
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: b3a2d88028f3854746d4e1d2fad80aae4f6be7be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143488"
---
# <a name="workflow-discovery-sample"></a>Workflow Discovery 샘플
이 샘플에서는 워크플로 서비스를 검색 가능하게 만드는 방법과 특정 서비스를 검색하는 사용자 지정 코드 활동을 작성하는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>데모  
 찾기 활동 및 워크플로 사용  
  
## <a name="discussion"></a>토론  
 샘플의 첫 번째 부분에서는 구성을 사용하여 워크플로 서비스를 검색 가능하게 만듭니다. 또한 구성을 사용하여 범위와 같은 사용자 지정 메타데이터로 서비스를 적절하게 적용할 수도 있습니다. 클라이언트에서 이 샘플은 검색을 사용하여 특정 계약과 일치하는 서비스를 검색하는 사용자 지정 코드 활동을 사용합니다. 코드 활동은 URI를 출력하며 이 URI는 나중에 보내기 활동에서 사용됩니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. 이 샘플에서는 실행하려면 적절한 URL ACL이 있어야 하는 HTTP 끝점을 사용합니다(자세한 내용은 [HTTP 및 HTTPS 구성](../feature-details/configuring-http-and-https.md) 참조). 권한이 높은 명령 프롬프트에서 다음 명령을 실행하면 적절한 ACL이 추가됩니다. 셸이 변수 형식을 이해하지 못하는 경우 도메인 및 사용자 이름을 다음 인수로 대체합니다.  
  
     **netsh http urlaclhttp://+:8000/ url= 사용자=% DOMAIN%\\% 사용자 이름 %**  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
