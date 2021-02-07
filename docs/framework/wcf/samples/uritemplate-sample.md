---
description: '자세한 정보: UriTemplate 샘플'
title: UriTemplate 샘플
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 80e932c06a6819ef7e1e289d9eacab6cd4e55f92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685441"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="c0625-103">UriTemplate 샘플</span><span class="sxs-lookup"><span data-stu-id="c0625-103">UriTemplate Sample</span></span>

<span data-ttu-id="c0625-104"><xref:System.UriTemplate> 클래스에서는 공통의 구조를 공유하는 URI 집합으로 작업하는 데 사용되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0625-104">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="c0625-105">이 샘플에서는 `UriTemplate`와 관련된 다음 핵심 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0625-105">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
- <span data-ttu-id="c0625-106">템플릿 만들기용 구문.</span><span class="sxs-lookup"><span data-stu-id="c0625-106">Syntax for creating templates.</span></span>  
  
- <span data-ttu-id="c0625-107">`UriTemplate`에서 <xref:System.UriTemplate.BindByName%2A> 및 <xref:System.UriTemplate.BindByPosition%2A>을 사용하여 URI 인스턴스화.</span><span class="sxs-lookup"><span data-stu-id="c0625-107">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
- <span data-ttu-id="c0625-108"><xref:System.UriTemplateTable.Match%2A> 및 `BindByName`의 역작업인 `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="c0625-108"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c0625-109">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c0625-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c0625-110">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c0625-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="c0625-111">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c0625-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c0625-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0625-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c0625-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c0625-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c0625-114">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0625-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c0625-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0625-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="c0625-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0625-116">See also</span></span>

- [<span data-ttu-id="c0625-117">UriTemplate 테이블</span><span class="sxs-lookup"><span data-stu-id="c0625-117">UriTemplate Table</span></span>](uritemplate-table-sample.md)
- [<span data-ttu-id="c0625-118">UriTemplate 테이블 디스패처</span><span class="sxs-lookup"><span data-stu-id="c0625-118">UriTemplate Table Dispatcher</span></span>](uritemplate-table-dispatcher-sample.md)
