---
description: '자세히 알아보기: WCF Data Services 정의'
title: WCF Data Services 정의
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: 43a4887226b03e80c4a966a118f210fe8a28000d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766090"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="458e7-103">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="458e7-103">Defining WCF Data Services</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="458e7-104">이 섹션에서는 WCF Data Services을 만들고 구성 하 여 OData (Open Data Protocol) 피드로 데이터를 노출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-104">This section describes how to create and configure WCF Data Services to expose data as an Open Data Protocol (OData) feed.</span></span> <span data-ttu-id="458e7-105">데이터 서비스를 만드는 데 필요한 기본 단계에 대 한 자세한 내용은 데이터를 [서비스로 노출](exposing-your-data-as-a-service-wcf-data-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="458e7-105">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="458e7-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="458e7-106">In This Section</span></span>

 [<span data-ttu-id="458e7-107">데이터 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="458e7-107">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="458e7-108">WCF Data Services에서 제공 하는 데이터 서비스 구성 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-108">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="458e7-109">Data Services 공급자</span><span class="sxs-lookup"><span data-stu-id="458e7-109">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)

 <span data-ttu-id="458e7-110">데이터를 데이터 서비스로 노출하기 위한 공급자 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-110">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="458e7-111">서비스 작업</span><span class="sxs-lookup"><span data-stu-id="458e7-111">Service Operations</span></span>](service-operations-wcf-data-services.md)

 <span data-ttu-id="458e7-112">서버에서 메서드를 노출하는 서비스 작업을 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-112">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="458e7-113">피드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="458e7-113">Feed Customization</span></span>](feed-customization-wcf-data-services.md)

 <span data-ttu-id="458e7-114">데이터 서비스 공급자에 의해 정의된 데이터 모델의 엔터티 및 데이터 피드의 요소 간에 매핑을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-114">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="458e7-115">인터셉터</span><span class="sxs-lookup"><span data-stu-id="458e7-115">Interceptors</span></span>](interceptors-wcf-data-services.md)

 <span data-ttu-id="458e7-116">데이터 서비스에 대한 요청에서 사용자 지정 비즈니스 논리를 수행하는 인터셉터 메서드를 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-116">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="458e7-117">WCF Data Services 개발 및 배포</span><span class="sxs-lookup"><span data-stu-id="458e7-117">Developing and Deploying WCF Data Services</span></span>](developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="458e7-118">Visual Studio를 사용하여 데이터 서비스를 개발 및 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-118">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="458e7-119">WCF Data Services에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="458e7-119">Securing WCF Data Services</span></span>](securing-wcf-data-services.md)

 <span data-ttu-id="458e7-120">데이터 서비스에 대한 인증 및 권한 부여와 기타 보안 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-120">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="458e7-121">데이터 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="458e7-121">Hosting the Data Service</span></span>](hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="458e7-122">데이터 서비스용 호스트를 선택하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-122">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="458e7-123">데이터 서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="458e7-123">Data Service Versioning</span></span>](data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="458e7-124">다른 버전의 OData를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-124">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="458e7-125">WCF Data Services 프로토콜 구현 정보</span><span class="sxs-lookup"><span data-stu-id="458e7-125">WCF Data Services Protocol Implementation Details</span></span>](wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="458e7-126">WCF Data Services에서 현재 구현 하지 않는 OData 프로토콜의 선택적 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="458e7-126">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="458e7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="458e7-127">See also</span></span>

- [<span data-ttu-id="458e7-128">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="458e7-128">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="458e7-129">데이터 서비스 리소스 액세스</span><span class="sxs-lookup"><span data-stu-id="458e7-129">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="458e7-130">시작</span><span class="sxs-lookup"><span data-stu-id="458e7-130">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
