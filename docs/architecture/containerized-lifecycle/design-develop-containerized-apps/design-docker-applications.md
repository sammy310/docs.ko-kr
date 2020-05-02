---
title: Docker 애플리케이션 설계
description: 이 가이드에서 자세히 설명하지 않은 주제이므로, 여기에서 마이크로서비스 아키텍처에 대한 심층적인 안내서를 참조하세요.
ms.date: 02/15/2019
ms.openlocfilehash: b8a08658ec6c3df3e1aed596a0240223768dd647
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738457"
---
# <a name="design-docker-applications"></a><span data-ttu-id="fc809-103">Docker 애플리케이션 설계</span><span class="sxs-lookup"><span data-stu-id="fc809-103">Design Docker applications</span></span>

<span data-ttu-id="fc809-104">1장에서는 컨테이너 및 Docker에 대한 기본 개념을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc809-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="fc809-105">해당 정보는 시작하는 데 필요한 기본적인 정보 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="fc809-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="fc809-106">그러나 엔터프라이즈 애플리케이션은 단일 서비스나 컨테이너 대신 여러 서비스로 구성되어 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc809-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="fc809-107">이러한 선택적 사용 사례의 경우 SOA(Service-Oriented Architecture), 고급 마이크로서비스 개념 및 컨테이너 오케스트레이션 개념과 같은 설계에 대한 추가 접근 방식을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc809-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="fc809-108">이 문서의 범위는 마이크로서비스에 국한되지 않고 모든 Docker 애플리케이션 수명 주기에 적용되므로 심층적으로 마이크로서비스 아키텍처를 탐색하지 않습니다. 컨테이너 및 Docker를 일반적인 SOA, 백그라운드 작업 또는 모놀리식 애플리케이션 배포 방법으로도 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fc809-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you can also use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="fc809-109">**추가 정보** 엔터프라이즈 애플리케이션 및 마이크로서비스 아키텍처에 대한 자세한 내용을 알아보려면 <https://aka.ms/MicroservicesEbook>에서 다운로드할 수도 있는 [NET 마이크로서비스: 컨테이너화된 .NET 애플리케이션을 위한 아키텍처](../../microservices/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc809-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="fc809-110">그러나 애플리케이션 수명 주기 및 DevOps를 시작하기 전에 애플리케이션을 설계하고 구성하는 방법과 디자인 선택 방법을 파악하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="fc809-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fc809-111">[이전](index.md)
>[다음](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="fc809-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
