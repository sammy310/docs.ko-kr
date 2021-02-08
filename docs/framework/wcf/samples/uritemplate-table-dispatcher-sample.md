---
description: '자세한 정보: UriTemplate 테이블 디스패처 샘플'
title: UriTemplate 테이블 디스패처 샘플
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 68cd7e87c9768995210f369e2d55a10ad048e338
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798201"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="cbd0f-103">UriTemplate 테이블 디스패처 샘플</span><span class="sxs-lookup"><span data-stu-id="cbd0f-103">UriTemplate Table Dispatcher Sample</span></span>

<span data-ttu-id="cbd0f-104"><xref:System.UriTemplateTable> 클래스는 <xref:System.UriTemplate> 인스턴스 집합으로 작업할 수 있도록 사전과 비슷한 연결 테이블 구조체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-104">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="cbd0f-105">이 샘플에서는 `UriTemplateTable`을 사용하여 빌드한 기본 디스패치 엔진을 보여 줍니다. `UriTemplateTable` 클래스의 일반적인 사용 시나리오에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-105">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="cbd0f-106">이 샘플에서는 `UriTemplateTable` 클래스의 다음 핵심 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-106">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="cbd0f-107">위임과 `UriTemplates`에 있는 `UriTemplateTable`의 연결</span><span class="sxs-lookup"><span data-stu-id="cbd0f-107">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="cbd0f-108"><xref:System.UriTemplateTable.MatchSingle%2A>을 사용하여 특성 URI의 올바른 처리기 위임 가져오기.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-108">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
- <span data-ttu-id="cbd0f-109">처리기 위임을 호출하여 요청 처리.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-109">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cbd0f-110">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cbd0f-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="cbd0f-111">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-111">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="cbd0f-112">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-112">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cbd0f-113">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbd0f-114">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-114">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="cbd0f-115">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbd0f-116">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-116">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="cbd0f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbd0f-117">See also</span></span>

- [<span data-ttu-id="cbd0f-118">UriTemplate 테이블</span><span class="sxs-lookup"><span data-stu-id="cbd0f-118">UriTemplate Table</span></span>](uritemplate-table-sample.md)
- [<span data-ttu-id="cbd0f-119">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="cbd0f-119">UriTemplate</span></span>](uritemplate-sample.md)
