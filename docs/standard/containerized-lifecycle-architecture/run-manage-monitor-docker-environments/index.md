---
title: Docker 프로덕션 환경 실행, 관리 및 모니터링
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
ms.date: 02/15/2019
ms.openlocfilehash: 900c361d5604f7fdaf41613287aa48c5381a9af7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644875"
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="39f4a-103">Docker 프로덕션 환경 실행, 관리 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="39f4a-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="39f4a-104">목표: 엔터프라이즈 응용 프로그램 고가용성 및 높은 확장성을 사용 하 여 실행 해야 합니다. IT 운영 환경 및 응용 프로그램 자체 관리 및 모니터링 하는 일을 할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f4a-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="39f4a-105">컨테이너화된 Docker 애플리케이션 수명 주기의 이 마지막 단계에서는 확장 가능한 고가용성(HA) 프로덕션 환경에서 애플리케이션을 실행, 관리 및 모니터링할 수 있는 방법을 중점적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="39f4a-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="39f4a-106">프로덕션 환경 (인프라 아키텍처 및 플랫폼 기술)에서 컨테이너 화 된 응용 프로그램을 실행 하는 방법은 관련 된 거의 이며이 전자책의 챕터 1에서 설명한 선택한 아키텍처 및 개발 플랫폼을 기준 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f4a-106">The way you run your containerized applications in production (infrastructure architecture and platform technologies) is very much related and based on the chosen architecture and development platforms discussed in Chapter 1 of this e-book.</span></span>

<span data-ttu-id="39f4a-107">다른 공급 업체 효과적으로 확장 가능한를 실행 하는 데 사용할 수 있는 HA 분산 응용 프로그램 관리 IT 관점에서 모니터링 하는 방법 및 특정 제품 및 Microsoft의 기술이이 장의 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f4a-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="39f4a-108">[이전](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
>[다음](run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="39f4a-108">[Previous](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
[Next](run-microservices-based-applications-in-production.md)</span></span>
