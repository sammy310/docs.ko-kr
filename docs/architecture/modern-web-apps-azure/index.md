---
title: ASP.NET Core 및 Azure를 사용하여 현대식 웹 애플리케이션 설계
description: ASP.NET Core 및 Azure를 사용하여 모놀리식 웹 애플리케이션을 빌드하는 방법에 대한 포괄적인 지침을 제공하는 가이드입니다.
author: ardalis
ms.author: wiwagn
ms.date: 12/07/2020
ms.openlocfilehash: 90d092b2269315e5b6734430e82cc7211324479b
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851297"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="43cf0-103">ASP.NET Core 및 Azure를 사용하여 현대식 웹 애플리케이션 설계</span><span class="sxs-lookup"><span data-stu-id="43cf0-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![최신 웹 애플리케이션 설계자 가이드의 표지 이미지](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="43cf0-105">**EDITION v5.0** - ASP.NET Core 5.0으로 업데이트됨</span><span class="sxs-lookup"><span data-stu-id="43cf0-105">**EDITION v5.0** - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="43cf0-106">책 업데이트 및 커뮤니티 기여에 대한 자세한 내용은 [changelog](https://aka.ms/aspnet-ebook-changelog)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43cf0-106">Refer [changelog](https://aka.ms/aspnet-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="43cf0-107">게시자:</span><span class="sxs-lookup"><span data-stu-id="43cf0-107">PUBLISHED BY</span></span>

<span data-ttu-id="43cf0-108">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="43cf0-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="43cf0-109">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="43cf0-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="43cf0-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="43cf0-110">One Microsoft Way</span></span>

<span data-ttu-id="43cf0-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="43cf0-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="43cf0-112">Copyright © 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="43cf0-112">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="43cf0-113">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="43cf0-113">All rights reserved.</span></span> <span data-ttu-id="43cf0-114">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="43cf0-115">이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="43cf0-116">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-116">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="43cf0-117">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="43cf0-118">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="43cf0-119">"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="43cf0-120">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="43cf0-121">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-121">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="43cf0-122">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-122">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="43cf0-123">만든 이:</span><span class="sxs-lookup"><span data-stu-id="43cf0-123">Author:</span></span>

> <span data-ttu-id="43cf0-124">**Steve "ardalis" Smith** - 소프트웨어 설계자이자 강사 - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="43cf0-124">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="43cf0-125">편집자:</span><span class="sxs-lookup"><span data-stu-id="43cf0-125">Editors:</span></span>

> <span data-ttu-id="43cf0-126">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="43cf0-126">**Maira Wenzel**</span></span>

## <a name="action-links"></a><span data-ttu-id="43cf0-127">작업 링크</span><span class="sxs-lookup"><span data-stu-id="43cf0-127">Action links</span></span>

- <span data-ttu-id="43cf0-128">이 eBook은 PDF 형식으로도 제공됩니다(영어 버전에만 해당). [다운로드](https://aka.ms/webappebook)</span><span class="sxs-lookup"><span data-stu-id="43cf0-128">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/webappebook)</span></span>

- <span data-ttu-id="43cf0-129">GitHub에서 참조 애플리케이션안 [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb) 복제/포크</span><span class="sxs-lookup"><span data-stu-id="43cf0-129">Clone/Fork the reference application [eShopOnWeb on GitHub](https://github.com/dotnet-architecture/eShopOnWeb)</span></span>

## <a name="introduction"></a><span data-ttu-id="43cf0-130">소개</span><span class="sxs-lookup"><span data-stu-id="43cf0-130">Introduction</span></span>

<span data-ttu-id="43cf0-131">.NET 5와 ASP.NET Core는 기존의.NET 개발 방식에 비해 여러 가지 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-131">.NET 5 and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="43cf0-132">다음 중 일부 또는 전부가 애플리케이션의 성공에 중요한 경우 서버 애플리케이션에 .NET 5를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-132">You should use .NET 5 for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="43cf0-133">크로스 플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="43cf0-133">Cross-platform support.</span></span>

- <span data-ttu-id="43cf0-134">마이크로 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="43cf0-134">Use of microservices.</span></span>

- <span data-ttu-id="43cf0-135">Docker 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="43cf0-135">Use of Docker containers.</span></span>

- <span data-ttu-id="43cf0-136">고성능 및 확장성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="43cf0-136">High performance and scalability requirements.</span></span>

- <span data-ttu-id="43cf0-137">동일한 서버의 애플리케이션에서 .NET 버전 병렬 관리</span><span class="sxs-lookup"><span data-stu-id="43cf0-137">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="43cf0-138">기존 .NET 애플리케이션은 이러한 많은 요구 사항을 지원할 수 있지만 ASP.NET Core와 .NET 5는 위의 시나리오에 대한 개선된 지원 사항을 제공하도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-138">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET 5 have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="43cf0-139">점점 더 많은 조직에서 Microsoft Azure 같은 서비스를 사용하여 클라우드에 웹 애플리케이션을 호스팅하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-139">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="43cf0-140">애플리케이션이나 조직에서 다음 요구사항이 중요한 경우 클라우드에서 애플리케이션을 호스팅하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-140">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="43cf0-141">데이터 센터 비용에 대한 투자 감소(하드웨어, 소프트웨어, 공간, 유틸리티, 서버 관리 등)</span><span class="sxs-lookup"><span data-stu-id="43cf0-141">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="43cf0-142">유동적인 가격 책정(유휴 용량이 아닌 사용량을 기준으로 지불)</span><span class="sxs-lookup"><span data-stu-id="43cf0-142">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="43cf0-143">매우 뛰어난 안정성</span><span class="sxs-lookup"><span data-stu-id="43cf0-143">Extreme reliability.</span></span>

- <span data-ttu-id="43cf0-144">향상된 앱 이동성: 앱의 배포 위치와 방법을 쉽게 변경</span><span class="sxs-lookup"><span data-stu-id="43cf0-144">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="43cf0-145">유동적인 용량: 실제 요구 사항에 따라 규모 확장 또는 축소</span><span class="sxs-lookup"><span data-stu-id="43cf0-145">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="43cf0-146">Azure에서 호스팅되는 ASP.NET Core를 사용하여 웹 애플리케이션을 빌드하면 기존의 대안보다 많은 경쟁적 이점을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-146">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="43cf0-147">ASP.NET Core는 현대식 웹 애플리케이션 개발 사례 및 클라우드 호스팅 시나리오에 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-147">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="43cf0-148">이 가이드에서는 이러한 기능을 최대한 활용할 수 있도록 ASP.NET Core 애플리케이션을 설계하는 방법에 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-148">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="version"></a><span data-ttu-id="43cf0-149">버전</span><span class="sxs-lookup"><span data-stu-id="43cf0-149">Version</span></span>

<span data-ttu-id="43cf0-150">이 가이드는 .NET 5.0 릴리스와 동시에 **.NET 5.0** 버전을 다루도록 수정되었으며, 동일한 기술 “웨이브”(즉 Azure 및 추가 타사 기술)와 관련된 여러 추가 업데이트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-150">This guide has been revised to cover **.NET 5.0** version along with many additional updates related to the same "wave" of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET 5.0 release.</span></span> <span data-ttu-id="43cf0-151">이런 이유로 책 버전도 버전 **5.0** 으로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-151">That's why the book version has also been updated to version **5.0**.</span></span>

## <a name="purpose"></a><span data-ttu-id="43cf0-152">용도</span><span class="sxs-lookup"><span data-stu-id="43cf0-152">Purpose</span></span>

<span data-ttu-id="43cf0-153">이 가이드에서는 ASP.NET Core와 Azure를 사용하는 *모놀리식* 웹 애플리케이션을 만드는 방법에 대한 포괄적인 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-153">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="43cf0-154">여기서 "모놀리식"은 이러한 애플리케이션이 상호 작용하는 서비스와 애플리케이션의 컬렉션이 아니라 하나의 단위로 배포된다는 사실을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-154">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="43cf0-155">이 가이드는 엔터프라이즈 애플리케이션을 호스팅하는 Docker, 마이크로서비스 및 컨테이너의 배포에 중점을 둔 [" _.NET 마이크로서비스. 컨테이너화된 .NET 애플리케이션용 아키텍처_"](../microservices/index.md)를 보충 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-155">This guide is complementary to ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices/index.md), which focuses more on Docker, microservices, and deployment of containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="43cf0-156">.NET 마이크로 서비스.</span><span class="sxs-lookup"><span data-stu-id="43cf0-156">.NET Microservices.</span></span> <span data-ttu-id="43cf0-157">컨테이너화된 .NET 애플리케이션을 위한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="43cf0-157">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="43cf0-158">**eBook**</span><span class="sxs-lookup"><span data-stu-id="43cf0-158">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="43cf0-159">**예제 애플리케이션**</span><span class="sxs-lookup"><span data-stu-id="43cf0-159">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="43cf0-160">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="43cf0-160">Who should use this guide</span></span>

<span data-ttu-id="43cf0-161">이 가이드의 주요 대상 사용자는 클라우드에서 Microsoft 기술 및 서비스를 사용하여 현대식 웹 애플리케이션을 구축하는 데 관심 있는 개발자, 개발 책임자 및 설계자입니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-161">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="43cf0-162">그 다음 대상자는 이미 ASP.NET 또는 Azure에 익숙하고 신규 또는 기존 프로젝트를 ASP.NET Core로 업그레이드하는 것이 적절한지에 관한 정보를 찾고 있는 기술 의사 결정권자입니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-162">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="43cf0-163">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="43cf0-163">How you can use this guide</span></span>

<span data-ttu-id="43cf0-164">이 가이드는 현대식 .NET 기술 및 Azure로 웹 애플리케이션을 구축하는 방법에 중점을 둔, 비교적 작은 문서로 압축되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-164">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Azure.</span></span> <span data-ttu-id="43cf0-165">따라서 전제적으로 읽어보면 이러한 애플리케이션 및 해당 기술 고려 사항의 이해를 위한 기반을 마련할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-165">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="43cf0-166">이 가이드와 애플리케이션 예제는 출발점이나 참고 자료 역할도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-166">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="43cf0-167">관련 애플리케이션 예제를 자신의 애플리케이션을 위한 템플릿으로 사용하거나 애플리케이션의 구성 요소 부분을 구성하는 방법을 알아보는 용도로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="43cf0-167">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="43cf0-168">자신의 애플리케이션을 위한 옵션을 저울질할 때는 가이드의 원칙과 아키텍처 및 기술 옵션, 의사 결정 고려 사항에 대한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43cf0-168">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="43cf0-169">이 가이드를 팀에서 자유롭게 공유하고 이러한 여러가지 고려 사항과 기회에 대한 이해를 도모하세요.</span><span class="sxs-lookup"><span data-stu-id="43cf0-169">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="43cf0-170">모든 사람이 공통적인 용어와 기본 원칙으로 작업하도록 하면 아키텍처 패턴및 사례를 일관성 있게 적용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43cf0-170">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="43cf0-171">참조 항목</span><span class="sxs-lookup"><span data-stu-id="43cf0-171">References</span></span>

- <span data-ttu-id="43cf0-172">**서버 앱에 대해 .NET 5와 .NET Framework 중에서 선택**</span><span class="sxs-lookup"><span data-stu-id="43cf0-172">**Choosing between .NET 5 and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../../standard/choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="43cf0-173">다음</span><span class="sxs-lookup"><span data-stu-id="43cf0-173">Next</span></span>](modern-web-applications-characteristics.md)
