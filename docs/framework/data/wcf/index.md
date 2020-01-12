---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 890f0ba25d8320008228c73660753b9899269fd7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900995"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="d1df7-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="d1df7-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="d1df7-103">WCF Data Services (이전의 "ADO.NET Data Services")는 [Representational State Transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)의 의미 체계를 사용 하 여 웹 또는 인트라넷을 통해 데이터를 노출 하 고 사용 하기 위해 Open Data Protocol (OData)를 사용 하는 서비스를 만들 수 있는 .NET Framework의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="d1df7-104">OData는 URI로 주소를 지정할 수 있는 리소스로 데이터를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="d1df7-105">데이터는 GET, PUT, POST 및 DELETE라는 표준 HTTP 동사를 사용하여 액세스되고 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="d1df7-106">OData는 [엔터티 데이터 모델](../adonet/entity-data-model.md) 의 엔터티-관계 규칙을 사용 하 여 리소스를 연결로 관련 된 엔터티 집합으로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="d1df7-107">WCF Data Services는 OData 프로토콜을 사용 하 여 리소스의 주소를 지정 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="d1df7-108">이러한 방식으로 OData를 지 원하는 모든 클라이언트에서 이러한 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="d1df7-109">OData를 사용 하면 데이터를 XML로 교환 및 업데이트 하기 위한 표준 집합인 Atom, AJAX에서 광범위 하 게 사용 되는 텍스트 기반 데이터 교환 형식인 JavaScript Object Notation (JSON)와 같이 잘 알려진 전송 형식을 사용 하 여 리소스를 요청 하 고 리소스에 데이터를 쓸 수 있습니다. 프로그램도.</span><span class="sxs-lookup"><span data-stu-id="d1df7-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="d1df7-110">WCF Data Services는 다양 한 원본에서 가져온 데이터를 OData 피드로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="d1df7-111">Visual Studio 도구를 사용 하면 ADO.NET Entity Framework 데이터 모델을 사용 하 여 OData 기반 서비스를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="d1df7-112">CLR (공용 언어 런타임) 클래스와 런타임에 바인딩된 데이터 나 형식화 되지 않은 데이터를 기반으로 하 여 OData 피드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="d1df7-113">또한 WCF Data Services에는 클라이언트 라이브러리 집합, 일반 .NET Framework 클라이언트 응용 프로그램 및 Silverlight 기반 응용 프로그램용 기타 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="d1df7-114">이러한 클라이언트 라이브러리는 .NET Framework 및 Silverlight와 같은 환경에서 OData 피드에 액세스할 때 개체 기반 프로그래밍 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="d1df7-115">시작 지점</span><span class="sxs-lookup"><span data-stu-id="d1df7-115">Where Should I Start?</span></span>

<span data-ttu-id="d1df7-116">관심 사항에 따라 다음 항목 중 하나를 사용 하 여 WCF Data Services 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="d1df7-117">바로 시작...</span><span class="sxs-lookup"><span data-stu-id="d1df7-117">I want to jump right in...</span></span>

- [<span data-ttu-id="d1df7-118">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="d1df7-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="d1df7-119">시작</span><span class="sxs-lookup"><span data-stu-id="d1df7-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="d1df7-120">코드를 표시 하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-120">Just show me some code...</span></span>

- [<span data-ttu-id="d1df7-121">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="d1df7-121">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="d1df7-122">방법: 데이터 서비스 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="d1df7-122">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="d1df7-123">방법: Windows Presentation Foundation 요소에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="d1df7-123">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="d1df7-124">OData에 대 한 자세한 내용을 확인 하려면 ...</span><span class="sxs-lookup"><span data-stu-id="d1df7-124">I want to know more about OData...</span></span>

- [<span data-ttu-id="d1df7-125">백서: OData 소개</span><span class="sxs-lookup"><span data-stu-id="d1df7-125">Whitepaper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="d1df7-126">Open Data Protocol 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="d1df7-126">Open Data Protocol Web site</span></span>](https://www.odata.org/)
- [<span data-ttu-id="d1df7-127">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="d1df7-127">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="d1df7-128">종단 간 샘플을 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-128">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="d1df7-129">[WCF Data Services 빠른 시작](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="d1df7-129">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="d1df7-130">OData SDK-샘플 코드</span><span class="sxs-lookup"><span data-stu-id="d1df7-130">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="d1df7-131">Visual Studio와의 통합 방식</span><span class="sxs-lookup"><span data-stu-id="d1df7-131">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="d1df7-132">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="d1df7-132">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="d1df7-133">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="d1df7-133">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="d1df7-134">Entity Framework 공급자</span><span class="sxs-lookup"><span data-stu-id="d1df7-134">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="d1df7-135">수행 가능 작업</span><span class="sxs-lookup"><span data-stu-id="d1df7-135">What can I do with it?</span></span>

- [<span data-ttu-id="d1df7-136">개요</span><span class="sxs-lookup"><span data-stu-id="d1df7-136">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="d1df7-137">애플리케이션 시나리오</span><span class="sxs-lookup"><span data-stu-id="d1df7-137">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="d1df7-138">LINQ를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-138">I want to use LINQ...</span></span>

- [<span data-ttu-id="d1df7-139">데이터 서비스 쿼리</span><span class="sxs-lookup"><span data-stu-id="d1df7-139">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="d1df7-140">LINQ 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d1df7-140">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="d1df7-141">방법: 데이터 서비스 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="d1df7-141">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="d1df7-142">추가 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-142">I still need some more information...</span></span>

- [<span data-ttu-id="d1df7-143">WCF Data Services 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="d1df7-143">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="d1df7-144">리소스</span><span class="sxs-lookup"><span data-stu-id="d1df7-144">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="d1df7-145">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d1df7-145">In This Section</span></span>

[<span data-ttu-id="d1df7-146">개요</span><span class="sxs-lookup"><span data-stu-id="d1df7-146">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="d1df7-147">WCF Data Services에서 사용 가능한 기능에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-147">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="d1df7-148">[WCF Data Services 5.0의 새로운 기능](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="d1df7-148">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="d1df7-149">WCF Data Services의 새로운 기능 및 새로운 OData 기능에 대 한 지원을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-149">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="d1df7-150">시작</span><span class="sxs-lookup"><span data-stu-id="d1df7-150">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="d1df7-151">WCF Data Services를 사용 하 여 OData 피드를 노출 하 고 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-151">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="d1df7-152">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="d1df7-152">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="d1df7-153">OData 피드를 노출 하는 데이터 서비스를 만들고 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-153">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="d1df7-154">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="d1df7-154">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="d1df7-155">클라이언트 라이브러리를 사용 하 여 .NET Framework 클라이언트 응용 프로그램에서 OData 피드를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1df7-155">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1df7-156">참조</span><span class="sxs-lookup"><span data-stu-id="d1df7-156">See also</span></span>

- [<span data-ttu-id="d1df7-157">REST(Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="d1df7-157">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
