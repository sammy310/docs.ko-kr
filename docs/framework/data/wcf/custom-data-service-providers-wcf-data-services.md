---
description: '자세한 정보: 사용자 지정 데이터 서비스 공급자 (WCF Data Services)'
title: 사용자 지정 데이터 서비스 공급자(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: df0cafae46cfdbd71a96341686a9200f032a9938
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766155"
---
# <a name="custom-data-service-providers-wcf-data-services"></a><span data-ttu-id="4437c-103">사용자 지정 데이터 서비스 공급자(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="4437c-103">Custom Data Service Providers (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="4437c-104">WCF Data Services에는 런타임에 바인딩된 데이터 형식을 기반으로 데이터 모델을 정의 하는 데 사용할 수 있는 공급자 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-104">WCF Data Services includes a set of providers that enables you to define a data model based on late-bound data types.</span></span>  
  
|<span data-ttu-id="4437c-105">공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-105">Provider</span></span>|<span data-ttu-id="4437c-106">설명</span><span class="sxs-lookup"><span data-stu-id="4437c-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4437c-107">메타데이터 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-107">Metadata provider</span></span>|<span data-ttu-id="4437c-108">이 공급자는 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 인터페이스를 구현하여 런타임에 사용자 지정 데이터 모델을 정의할 수 있도록 하는 핵심 사용자 지정 데이터 서비스 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-108">This is the core custom data service provider that enables you to define a custom data model at runtime by implementing the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span>|  
|<span data-ttu-id="4437c-109">쿼리 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-109">Query provider</span></span>|<span data-ttu-id="4437c-110">이 공급자를 사용하면 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 인터페이스를 사용하여 정의된 사용자 지정 데이터 모델에 대해 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-110">This provider enables you to execute queries against a custom data model that is defined by using the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span> <span data-ttu-id="4437c-111">쿼리 공급자는 <xref:System.Data.Services.Providers.IDataServiceQueryProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-111">The query provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceQueryProvider> interface.</span></span>|  
|<span data-ttu-id="4437c-112">업데이트 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-112">Update provider</span></span>|<span data-ttu-id="4437c-113">이 공급자를 사용하면 사용자 지정 데이터 서비스 공급자에 노출된 형식을 업데이트하고 동시성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-113">This provider enables you to make updates to types that are exposed in a custom data service provider and to manage concurrency.</span></span> <span data-ttu-id="4437c-114">업데이트 공급자는 <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-114">An update provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> interface</span></span>|  
|<span data-ttu-id="4437c-115">페이징 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-115">Paging provider</span></span>|<span data-ttu-id="4437c-116">이 공급자는 사용자 지정 데이터 서비스 공급자와 함께 사용되어 서버 기반 페이징 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-116">This provider is used with the custom data service provider to enable server-driven paging support.</span></span> <span data-ttu-id="4437c-117">사용자 지정 데이터 서비스용 페이징 공급자는 <xref:System.Data.Services.Providers.IDataServicePagingProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-117">A paging provider for a custom data service is created by implementing the <xref:System.Data.Services.Providers.IDataServicePagingProvider> interface.</span></span>|  
|<span data-ttu-id="4437c-118">스트리밍 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-118">Streaming provider</span></span>|<span data-ttu-id="4437c-119">이 공급자를 사용하면 BLOB(Binary Large Object) 데이터 형식을 스트림으로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-119">This provider enables you to expose binary large object data types as a stream.</span></span> <span data-ttu-id="4437c-120">스트리밍 공급자는 <xref:System.Data.Services.Providers.IDataServiceStreamProvider> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-120">A streaming provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceStreamProvider> interface.</span></span> <span data-ttu-id="4437c-121">스트리밍 공급자는 Entity Framework 및 리플렉션 데이터 소스 공급자와 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-121">The streaming provider can also be used with Entity Framework and reflection data source providers.</span></span> <span data-ttu-id="4437c-122">자세한 내용은 [스트리밍 공급자](streaming-provider-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4437c-122">For more information, see [Streaming Provider](streaming-provider-wcf-data-services.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4437c-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4437c-123">See also</span></span>

- [<span data-ttu-id="4437c-124">Data Services 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-124">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="4437c-125">Entity Framework 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-125">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)
- [<span data-ttu-id="4437c-126">리플렉션 공급자</span><span class="sxs-lookup"><span data-stu-id="4437c-126">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
