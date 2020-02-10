---
title: LINQ 메시지 쿼리 상관 관계
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: cd91a171f3242cfd7e8ac0404e24ac065919bcce
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094620"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="09095-102">LINQ 메시지 쿼리 상관 관계</span><span class="sxs-lookup"><span data-stu-id="09095-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="09095-103">이 샘플에서는 시스템에서 제공하는 <xref:System.ServiceModel.Dispatcher.MessageQuery> 대신 사용자 지정 <xref:System.ServiceModel.XPathMessageQuery> 구현을 사용하여 내용 기반 상관 관계를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09095-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="09095-104">데모 보기</span><span class="sxs-lookup"><span data-stu-id="09095-104">Demonstrates</span></span>  
 <span data-ttu-id="09095-105">사용자 지정 <xref:System.ServiceModel.Dispatcher.MessageQuery>, 내용 기반 상관 관계</span><span class="sxs-lookup"><span data-stu-id="09095-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="09095-106">토론</span><span class="sxs-lookup"><span data-stu-id="09095-106">Discussion</span></span>  
 <span data-ttu-id="09095-107">이 샘플에서는 상관 관계를 만들기 위해 <xref:System.ServiceModel.Dispatcher.MessageQuery> 기본 클래스를 확장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09095-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="09095-108">사용자 지정 `LinqMessageQuery`를 구현하면 XLinq를 사용하여 메시지 내에서 XName을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09095-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="09095-109">쿼리를 통해 검색한 데이터는 메시지를 적절한 워크플로 인스턴스로 디스패치하기 위한 상관 관계 키를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09095-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="09095-110">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="09095-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="09095-111">이 샘플에서는 HTTP 엔드포인트를 사용하여 워크플로 서비스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="09095-112">이 샘플을 실행 하려면 Visual Studio를 관리자 권한으로 실행 하거나 관리자 권한 프롬프트에서 다음 명령을 실행 하 여 적절 한 Acl을 추가 하 여 적절 한 URL Acl을 추가 해야 합니다 (자세한 내용은 [HTTP 및 HTTPS 구성](../../wcf/feature-details/configuring-http-and-https.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="09095-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](../../wcf/feature-details/configuring-http-and-https.md) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="09095-113">도메인과 사용자 이름이 대체되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="09095-114">URL ACL이 추가되었으면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="09095-115">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-115">Build the solution.</span></span>  
  
    2. <span data-ttu-id="09095-116">솔루션을 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트 설정**을 선택 하 여 여러 시작 프로젝트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="09095-117">**서비스** 와 **클라이언트** (해당 순서로)를 여러 시작 프로젝트로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3. <span data-ttu-id="09095-118">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-118">Run the application.</span></span> <span data-ttu-id="09095-119">주문서를 보내고 구매 주문서 ID를 받은 다음 주문을 확인하는 워크플로가 클라이언트 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="09095-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="09095-120">처리 중인 요청이 서비스 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="09095-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="09095-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09095-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="09095-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="09095-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="09095-123">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="09095-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="09095-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09095-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
