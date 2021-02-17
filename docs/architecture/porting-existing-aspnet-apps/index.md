---
title: 기존 ASP.NET 앱을 .NET Core로 포팅
description: ASP.NET MVC 및 Web API 앱을 ASP.NET Core로 변환하기 위한 무료 가이드입니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 36c0cdbe03fb97ae82336d53e15be2108e9c6367
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488167"
---
# <a name="porting-existing-aspnet-apps-to-net-core"></a><span data-ttu-id="e77e3-103">기존 ASP.NET 앱을 .NET Core로 포팅</span><span class="sxs-lookup"><span data-stu-id="e77e3-103">Porting Existing ASP.NET Apps to .NET Core</span></span>

![표지 이미지](./media/index/porting-existing-aspnet-apps.png)

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e77e3-105">게시자:</span><span class="sxs-lookup"><span data-stu-id="e77e3-105">PUBLISHED BY</span></span>

<span data-ttu-id="e77e3-106">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="e77e3-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="e77e3-107">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="e77e3-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="e77e3-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e77e3-108">One Microsoft Way</span></span>

<span data-ttu-id="e77e3-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="e77e3-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="e77e3-110">Copyright &copy; 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="e77e3-110">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="e77e3-111">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="e77e3-111">All rights reserved.</span></span> <span data-ttu-id="e77e3-112">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-112">No part of this book's contents may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="e77e3-113">이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="e77e3-114">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="e77e3-115">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="e77e3-116">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="e77e3-117">"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="e77e3-118">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="e77e3-119">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="e77e3-120">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="e77e3-121">작성자:</span><span class="sxs-lookup"><span data-stu-id="e77e3-121">Authors:</span></span>

> <span data-ttu-id="e77e3-122">**Steve "ardalis" Smith**, 소프트웨어 설계자이자 강사 - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="e77e3-122">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="e77e3-123">참가자 및 검토자:</span><span class="sxs-lookup"><span data-stu-id="e77e3-123">Participants and Reviewers:</span></span>

> <span data-ttu-id="e77e3-124">**Nish Anil**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="e77e3-124">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="e77e3-125">**Mike Rousos**, 수석 소프트웨어 엔지니어, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="e77e3-125">**Mike Rousos**, Principal Software Engineer, .NET team, Microsoft</span></span>

> <span data-ttu-id="e77e3-126">**Scott Addie**, 선임 콘텐츠 개발자, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="e77e3-126">**Scott Addie**, Senior Content Developer, .NET team, Microsoft</span></span>

> <span data-ttu-id="e77e3-127">**David Pine**, 선임 콘텐츠 개발자, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="e77e3-127">**David Pine**, Senior Content Developer, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="e77e3-128">버전</span><span class="sxs-lookup"><span data-stu-id="e77e3-128">Version</span></span>

<span data-ttu-id="e77e3-129">이 가이드에서는 .NET Core 3.1 릴리스와 동일한 기술 "흐름"(Azure 및 기타 타사 기술)과 관련된 **.NET Core 3.1** 및 업데이트에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-129">This guide covers **.NET Core 3.1** and updates related to the same technology "wave" (that is, Azure and other third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span> <span data-ttu-id="e77e3-130">.NET Core 3.1에서 .NET 5.0(다음 버전)으로 업데이트하는 것은 비교적 간단하며, .NET Framework에서 .NET Core로 포팅하는 것보다 훨씬 수월합니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-130">Updating from .NET Core 3.1 to .NET 5.0 (the next version) is relatively straightforward and certainly will require substantially less effort than porting from .NET Framework to .NET Core.</span></span> <span data-ttu-id="e77e3-131">.NET Framework 4.x에서 .NET 5.0으로 마이그레이션하는 것은 .NET Core 3.1로 마이그레이션하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-131">Migrating from .NET Framework 4.x to .NET 5.0 will be similar to migrating to .NET Core 3.1.</span></span> <span data-ttu-id="e77e3-132">자세한 내용은 [적절한 .NET Core 버전 선택](choose-net-core-version.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e77e3-132">For more information, see [choosing the right .NET Core version](choose-net-core-version.md).</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="e77e3-133">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="e77e3-133">Who should use this guide</span></span>

<span data-ttu-id="e77e3-134">이 가이드의 대상 그룹은 ASP.NET MVC 및 Web API(.NET Framework 4.x)로 작성한 기존 앱을 .NET Core로 마이그레이션하는 데 관심이 있는 개발자, 개발 리드 및 설계자입니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-134">This guide's audience is developers, development leads, and architects who are interested in migrating their existing apps written for ASP.NET MVC and Web API (.NET Framework 4.x) to .NET Core.</span></span> <span data-ttu-id="e77e3-135">ASP.NET Web Forms 개발자는 이 가이드를 활용하되 [ASP.NET Web Forms 개발자를 위한 Blazor](https://docs.microsoft.com/dotnet/architecture/blazor-for-web-forms-developers/) eBook도 읽는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-135">ASP.NET Web Forms developers will benefit from this guide but should also read the [Blazor for ASP.NET Web Forms Developers](https://docs.microsoft.com/dotnet/architecture/blazor-for-web-forms-developers/) e-book.</span></span>

<span data-ttu-id="e77e3-136">보조 대상 그룹은 앱을 .NET Core로 옮기려고 계획 중인 기술 의사 결정자입니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-136">A secondary audience is technical decision-makers planning when to move their apps to .NET Core.</span></span>

<span data-ttu-id="e77e3-137">이 책의 대상 그룹은 큰 용량의 앱을 ASP.NET MVC 및 Web API에서 실행하는 .NET 개발자입니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-137">The target audience for this book is .NET developers with large, existing apps that run on ASP.NET MVC and Web API.</span></span> <span data-ttu-id="e77e3-138">ASP.NET Web Forms 기반으로 빌드된 앱은 이 책에서 다루지 않지만 .NET Framework와 .NET Core를 비교하는 대부분의 정보는 여전히 관련이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-138">Apps built on ASP.NET Web Forms are outside of the focus of this book, though much of the information comparing .NET Framework and .NET Core may still be relevant.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="e77e3-139">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="e77e3-139">How you can use this guide</span></span>

<span data-ttu-id="e77e3-140">다른 많은 독자들처럼 이 책을 바로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-140">You can read this book straight through, as we expect many readers to do.</span></span> <span data-ttu-id="e77e3-141">이 책에서는 앱을 포팅할 필요가 있는지에 대한 고려 사항을 먼저 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-141">This book will provide you first with considerations for whether you should port your app at all.</span></span> <span data-ttu-id="e77e3-142">해당 콘텐츠 다음으로 .NET Framework와 .NET Core의 아키텍처 차이를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-142">That content is followed by architectural differences between .NET Framework and .NET Core.</span></span> <span data-ttu-id="e77e3-143">여기에서 시간 경과에 따라 큰 솔루션을 마이그레이션하는 전략과 실제 앱을 포팅하는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-143">From there, you'll learn strategies for migrating a large solution over time and how to port a real app.</span></span> <span data-ttu-id="e77e3-144">그런 다음 사용자에게 단일 앱으로 표시되는 동안 여러 앱을 실행해야 하는 필요성을 설명하는 배포 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-144">Next, the book includes deployment scenarios that address the need to run different apps while appearing as a single app to users.</span></span> <span data-ttu-id="e77e3-145">ASP.NET MVC에서 ASP.NET Core로 마이그레이션된 실제 앱을 설명하는 두 가지 사례 연구를 다루며 이 책을 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-145">The book concludes with two case studies describing real apps that have migrated from ASP.NET MVC to ASP.NET Core.</span></span>

<span data-ttu-id="e77e3-146">첫 번째 챕터부터 시작하지 않더라도 다음 챕터 중 하나를 참조하여 특정 개념에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-146">Whether or not you choose to start from the first chapter, you can reference any of these chapters to learn about specific concepts:</span></span>

- [<span data-ttu-id="e77e3-147">아키텍처 차이점</span><span class="sxs-lookup"><span data-stu-id="e77e3-147">Architectural differences</span></span>](architectural-differences.md)
- [<span data-ttu-id="e77e3-148">대규모 솔루션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e77e3-148">Migrate large solutions</span></span>](migrate-large-solutions.md)
- [<span data-ttu-id="e77e3-149">샘플 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e77e3-149">Sample migration</span></span>](example-migration-eshop.md)
- [<span data-ttu-id="e77e3-150">배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="e77e3-150">Deployment scenarios</span></span>](deployment-scenarios.md)

<span data-ttu-id="e77e3-151">이 가이드는 [PDF 양식](https://aka.ms/aspnet-porting-ebook)과 온라인에서 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77e3-151">This guide is available both in [PDF form](https://aka.ms/aspnet-porting-ebook) and online.</span></span> <span data-ttu-id="e77e3-152">이러한 개념에 관한 일반적인 이해를 할 수 있도록 이 문서 또는 온라인 버전 링크를 팀에 전달하세요.</span><span class="sxs-lookup"><span data-stu-id="e77e3-152">Feel free to forward this document or links to its online version to your team to ensure a common understanding of these concepts.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="e77e3-153">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="e77e3-153">Send your feedback</span></span>

<span data-ttu-id="e77e3-154">이 책과 관련 샘플은 지속적으로 진화합니다. 여러분의 피드백을 기다리고 있습니다!</span><span class="sxs-lookup"><span data-stu-id="e77e3-154">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="e77e3-155">이 책을 향상시킬 수 있는 방법에 대한 의견이 있으면 [GitHub 문제](https://github.com/dotnet/docs/issues)에 빌드된 페이지의 맨 아래에서 피드백 섹션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e77e3-155">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="e77e3-156">다음</span><span class="sxs-lookup"><span data-stu-id="e77e3-156">Next</span></span>](introduction.md)
