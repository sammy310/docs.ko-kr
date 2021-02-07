---
description: '자세한 정보: 워크플로 검색 샘플'
title: Workflow Discovery 샘플
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: a44796aa37cc97a41c5af79484146601ebbda20f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715108"
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="fb0c1-103">Workflow Discovery 샘플</span><span class="sxs-lookup"><span data-stu-id="fb0c1-103">Workflow Discovery Sample</span></span>

<span data-ttu-id="fb0c1-104">이 샘플에서는 워크플로 서비스를 검색 가능하게 만드는 방법과 특정 서비스를 검색하는 사용자 지정 코드 활동을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-104">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="fb0c1-105">데모</span><span class="sxs-lookup"><span data-stu-id="fb0c1-105">Demonstrates</span></span>  

 <span data-ttu-id="fb0c1-106">찾기 활동 및 워크플로 사용</span><span class="sxs-lookup"><span data-stu-id="fb0c1-106">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="fb0c1-107">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="fb0c1-107">Discussion</span></span>  

 <span data-ttu-id="fb0c1-108">샘플의 첫 번째 부분에서는 구성을 사용하여 워크플로 서비스를 검색 가능하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-108">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="fb0c1-109">또한 구성을 사용하여 범위와 같은 사용자 지정 메타데이터로 서비스를 적절하게 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-109">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="fb0c1-110">클라이언트에서 이 샘플은 검색을 사용하여 특정 계약과 일치하는 서비스를 검색하는 사용자 지정 코드 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-110">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="fb0c1-111">코드 활동은 URI를 출력하며 이 URI는 나중에 보내기 활동에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-111">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fb0c1-112">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="fb0c1-112">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="fb0c1-113">이 샘플은 실행할 적절 한 URL Acl이 있어야 하는 HTTP 끝점을 사용 합니다 (자세한 내용은 [http 및 HTTPS 구성](../feature-details/configuring-http-and-https.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="fb0c1-113">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md) for details).</span></span> <span data-ttu-id="fb0c1-114">권한이 높은 명령 프롬프트에서 다음 명령을 실행하면 적절한 ACL이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-114">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="fb0c1-115">셸이 변수 형식을 인식 하지 못하는 경우 도메인 및 사용자 이름으로 다음 인수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-115">If your shell does not understand the variable format, substitute your Domain and Username for the following arguments.</span></span>  
  
    `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`
  
> [!IMPORTANT]
> <span data-ttu-id="fb0c1-116">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fb0c1-117">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-117">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="fb0c1-118">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fb0c1-119">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0c1-119">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
