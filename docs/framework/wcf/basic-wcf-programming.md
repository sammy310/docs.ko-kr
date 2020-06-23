---
title: 기본 WCF 프로그래밍
description: 이러한 문서를 참조 하 여 기본 프로그래밍 수명 주기에서 문제 해결에 이르기까지 Windows Communication Foundation 응용 프로그램을 개발 하세요.
ms.date: 03/30/2017
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
ms.openlocfilehash: 6f4de39494902dcffcb25f75a6ff9f57b28547ff
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245520"
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="72a18-103">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="72a18-103">Basic WCF programming</span></span>

<span data-ttu-id="72a18-104">이 섹션에서는 WCF (Windows Communication Foundation) 응용 프로그램을 만들기 위한 기본 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-104">This section presents the fundamentals for creating Windows Communication Foundation (WCF) applications.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="72a18-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="72a18-105">In this section</span></span>

 <span data-ttu-id="72a18-106">[기본 프로그래밍 수명 주기](basic-programming-lifecycle.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-106">[Basic Programming Lifecycle](basic-programming-lifecycle.md)</span></span>\
 <span data-ttu-id="72a18-107">WCF 서비스 및 클라이언트 응용 프로그램을 디자인, 빌드 및 배포 하는 수명 주기를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-107">Describes the lifecycle of designing, building, and deploying WCF service and client applications.</span></span>

 <span data-ttu-id="72a18-108">[서비스 디자인 및 구현](designing-and-implementing-services.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-108">[Designing and Implementing Services](designing-and-implementing-services.md)</span></span>\
 <span data-ttu-id="72a18-109">서비스 계약을 디자인 및 구현하고 메시지 교환 패턴을 선택하고 오류 계약 및 기타 서비스 기본 사항을 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-109">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>

 <span data-ttu-id="72a18-110">[서비스 구성](configuring-services.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-110">[Configuring Services](configuring-services.md)</span></span>\
 <span data-ttu-id="72a18-111">계약 요구 사항을 지원 하도록 WCF 서비스를 구성 하 고, 로컬 런타임 동작을 사용자 지정 하 고, 서비스를 게시할 주소를 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-111">Describes how to configure a WCF service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>

 <span data-ttu-id="72a18-112">[호스팅 서비스](hosting-services.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-112">[Hosting Services](hosting-services.md)</span></span>\
 <span data-ttu-id="72a18-113">애플리케이션의 기본적인 호스팅 서비스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-113">Describes the basics of hosting services in an application.</span></span>

 <span data-ttu-id="72a18-114">[클라이언트 빌드](building-clients.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-114">[Building Clients](building-clients.md)</span></span>\
 <span data-ttu-id="72a18-115">서비스에서 메타 데이터를 가져오고, WCF 클라이언트 코드로 변환 하 고, 보안 문제를 처리 하 고, WCF 클라이언트를 빌드, 구성 및 호스트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-115">Describes how to obtain metadata from services, convert that into WCF client code, handle security issues, and build, configure, and host a WCF client.</span></span>

 <span data-ttu-id="72a18-116">[확장성 소개](introduction-to-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-116">[Introduction to Extensibility](introduction-to-extensibility.md)</span></span>\
 <span data-ttu-id="72a18-117">WCF를 확장 하 여 사용자 지정 솔루션을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-117">Describes how to extend WCF to create custom solutions.</span></span>

 <span data-ttu-id="72a18-118">[WCF 문제 해결 퀵 스타트](wcf-troubleshooting-quickstart.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-118">[WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md)</span></span>\
 <span data-ttu-id="72a18-119">발생하는 가장 일반적인 문제 중 일부, 이러한 문제를 해결하기 위해 수행할 수 있는 작업 및 문제에 대한 자세한 정보가 있는 위치에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-119">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>

 <span data-ttu-id="72a18-120">[WCF 및 ASP.NET Web API](wcf-and-aspnet-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="72a18-120">[WCF and ASP.NET Web API](wcf-and-aspnet-web-api.md)</span></span>\
 <span data-ttu-id="72a18-121">두 가지 기술과 이러한 기술의 관계 및 사용 시기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72a18-121">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>

## <a name="reference"></a><span data-ttu-id="72a18-122">참조</span><span class="sxs-lookup"><span data-stu-id="72a18-122">Reference</span></span>

- <xref:System.ServiceModel>
- <xref:System.ServiceModel.Channels>
- <xref:System.ServiceModel.Description>

## <a name="related-sections"></a><span data-ttu-id="72a18-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="72a18-123">Related sections</span></span>

- [<span data-ttu-id="72a18-124">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="72a18-124">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="72a18-125">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="72a18-125">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="72a18-126">지침 및 최선의 구현 방법</span><span class="sxs-lookup"><span data-stu-id="72a18-126">Guidelines and Best Practices</span></span>](guidelines-and-best-practices.md)
- [<span data-ttu-id="72a18-127">Windows Communication Foundation 도구</span><span class="sxs-lookup"><span data-stu-id="72a18-127">Windows Communication Foundation Tools</span></span>](tools.md)
- [<span data-ttu-id="72a18-128">WCF(Windows Communication Foundation) 샘플</span><span class="sxs-lookup"><span data-stu-id="72a18-128">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="72a18-129">시작</span><span class="sxs-lookup"><span data-stu-id="72a18-129">Getting Started</span></span>](./samples/getting-started-sample.md)
- [<span data-ttu-id="72a18-130">인라인 코드를 사용한 IIS 호스팅</span><span class="sxs-lookup"><span data-stu-id="72a18-130">IIS Hosting Using Inline Code</span></span>](./samples/iis-hosting-using-inline-code.md)
- [<span data-ttu-id="72a18-131">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="72a18-131">Self-Host</span></span>](./samples/self-host.md)
