---
title: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
description: Docker 및 Microsoft 플랫폼과 도구를 사용하여 컨테이너화된 애플리케이션을 개발하고 배포하는 개발 및 배포 프로세스의 대략적인 개요를 확인하세요.
ms.date: 11/10/2020
ms.openlocfilehash: cf20ea97ec252649cdb14add40ead67b6319520a
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506664"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a><span data-ttu-id="1bf9f-103">Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기</span><span class="sxs-lookup"><span data-stu-id="1bf9f-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools</span></span>

![책 표지](./media/devops-book-cover-large-we.png)

<span data-ttu-id="1bf9f-105">**EDITION v3.1** - ASP.NET Core 3.1로 업데이트되었습니다</span><span class="sxs-lookup"><span data-stu-id="1bf9f-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="1bf9f-106">책 업데이트 및 커뮤니티 기여에 대한 자세한 내용은 [changelog](https://aka.ms/DockerLifecycleEbookChangelog)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-106">Refer [changelog](https://aka.ms/DockerLifecycleEbookChangelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="1bf9f-107">이 가이드는 Docker와 Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 ASP.NET Core 애플리케이션을 개발하고 배포하기 위한 일반적인 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-107">This guide is a general overview for developing and deploying containerized ASP.NET Core applications with Docker, using the Microsoft platform and tools.</span></span> <span data-ttu-id="1bf9f-108">이 가이드는 CI/CD 파이프라인을 구현하기 위한 Azure DevOps뿐만 아니라 배포를 위한 ACR(Azure Container Registry) 및 AKS(Azure Kubernetes Service)도 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-108">The guide includes a high-level introduction to Azure DevOps, for implementing CI/CD pipelines, as well as Azure Container Registry (ACR), and Azure Kubernetes Services AKS for deployment.</span></span>

<span data-ttu-id="1bf9f-109">자세한 개발 관련 세부 정보는 [.NET 마이크로 서비스: 컨테이너화된 .NET 애플리케이션의 아키텍처](../microservices/index.md) 가이드 및 IT 관련 참조 애플리케이션 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-109">For low-level, development-related details you can see the [.NET Microservices: Architecture for Containerized .NET Applications](../microservices/index.md) guide and it related reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="1bf9f-110">피드백을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-110">Send us your feedback!</span></span>

<span data-ttu-id="1bf9f-111">이 가이드는 .NET에서 컨테이너화된 애플리케이션 및 마이크로 서비스의 아키텍처를 쉽게 이해할 수 있도록 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-111">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="1bf9f-112">가이드 및 관련 참조 애플리케이션은 계속 발전할 예정이므로, 피드백이 있으시면 언제든지 보내주세요!</span><span class="sxs-lookup"><span data-stu-id="1bf9f-112">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="1bf9f-113">이 가이드를 개선할 수 있는 방법에 대한 의견이 있으시면 <https://aka.ms/ebookfeedback>에서 피드백을 제출해주세요.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-113">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="1bf9f-114">크레딧</span><span class="sxs-lookup"><span data-stu-id="1bf9f-114">Credits</span></span>

<span data-ttu-id="1bf9f-115">만든 이:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-115">Author:</span></span>

> <span data-ttu-id="1bf9f-116">**Cesar de la Torre** , 선임 PM, .NET 제품 팀, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-116">**Cesar de la Torre** , Sr. PM, .NET product team, Microsoft Corp.</span></span>

<span data-ttu-id="1bf9f-117">위임 편집자:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-117">Acquisitions Editor:</span></span>

> <span data-ttu-id="1bf9f-118">**Janine Patrick**</span><span class="sxs-lookup"><span data-stu-id="1bf9f-118">**Janine Patrick**</span></span>

<span data-ttu-id="1bf9f-119">개발 편집자:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-119">Developmental Editor:</span></span>

> <span data-ttu-id="1bf9f-120">**Bob Russell** , 솔루션 전문가, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bf9f-120">**Bob Russell** , Solutions Professional at Microsoft</span></span>
>
> [<span data-ttu-id="1bf9f-121">**Octal Publishing, Inc.**</span><span class="sxs-lookup"><span data-stu-id="1bf9f-121">**Octal Publishing, Inc.**</span></span>](http://www.octalpub.com/)

<span data-ttu-id="1bf9f-122">편집 프로덕션:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-122">Editorial Production:</span></span>

> [<span data-ttu-id="1bf9f-123">Dianne Russell</span><span class="sxs-lookup"><span data-stu-id="1bf9f-123">Dianne Russell</span></span>](http://www.octalpub.com/)
>
> <span data-ttu-id="1bf9f-124">**Octal Publishing, Inc.**</span><span class="sxs-lookup"><span data-stu-id="1bf9f-124">**Octal Publishing, Inc.**</span></span>

<span data-ttu-id="1bf9f-125">교열 편집자:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-125">Copyeditor:</span></span>

> <span data-ttu-id="1bf9f-126">**Bob Russell** , 솔루션 전문가, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bf9f-126">**Bob Russell** , Solutions Professional at Microsoft</span></span>

<span data-ttu-id="1bf9f-127">참가자 및 검토자:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-127">Participants and reviewers:</span></span>

> <span data-ttu-id="1bf9f-128">**Nish Anil** , 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bf9f-128">**Nish Anil** , Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="1bf9f-129">**Miguel Veloso** , 소프트웨어 개발 엔지니어, Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="1bf9f-129">**Miguel Veloso** , Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="1bf9f-130">**Sumit Ghosh** , 주임 컨설턴트, Neudesic</span><span class="sxs-lookup"><span data-stu-id="1bf9f-130">**Sumit Ghosh** , Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="1bf9f-131">Copyright</span><span class="sxs-lookup"><span data-stu-id="1bf9f-131">Copyright</span></span>

<span data-ttu-id="1bf9f-132">게시자:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-132">PUBLISHED BY</span></span>

<span data-ttu-id="1bf9f-133">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="1bf9f-133">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="1bf9f-134">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="1bf9f-134">A division of Microsoft Corporation</span></span>

<span data-ttu-id="1bf9f-135">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1bf9f-135">One Microsoft Way</span></span>

<span data-ttu-id="1bf9f-136">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="1bf9f-136">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="1bf9f-137">Copyright &copy; 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1bf9f-137">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="1bf9f-138">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-138">All rights reserved.</span></span> <span data-ttu-id="1bf9f-139">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-139">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="1bf9f-140">이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-140">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="1bf9f-141">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-141">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="1bf9f-142">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-142">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="1bf9f-143">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-143">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="1bf9f-144">"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-144">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="1bf9f-145">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-145">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="1bf9f-146">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-146">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="1bf9f-147">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-147">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="1bf9f-148">다음</span><span class="sxs-lookup"><span data-stu-id="1bf9f-148">Next</span></span>](introduction-to-containers-and-docker.md)
