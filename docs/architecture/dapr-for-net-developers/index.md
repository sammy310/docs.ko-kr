---
title: .NET 개발자용 Dapr
description: Microsoft의 오픈 소스 Distributed Application Runtime의 전체 기능을 이해하고 활용하기 위한 .NET 개발자용 안내서입니다.
author: robvet
ms.date: 02/17/2021
ms.openlocfilehash: 2ab66257cca6f99074e2aa45a24869012b4976fe
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623722"
---
# <a name="dapr-for-net-developers"></a><span data-ttu-id="346e1-103">.NET 개발자용 Dapr</span><span class="sxs-lookup"><span data-stu-id="346e1-103">Dapr for .NET Developers</span></span>

![표지 이미지](./media/cover.png)

<span data-ttu-id="346e1-105">**미리 보기 버전**</span><span class="sxs-lookup"><span data-stu-id="346e1-105">**PREVIEW EDITION**</span></span>

<span data-ttu-id="346e1-106">게시자:</span><span class="sxs-lookup"><span data-stu-id="346e1-106">PUBLISHED BY</span></span>

<span data-ttu-id="346e1-107">Microsoft 개발자 부서, .NET 및 Azure Incubations 팀</span><span class="sxs-lookup"><span data-stu-id="346e1-107">Microsoft Developer Division, .NET, and Azure Incubations teams</span></span>

<span data-ttu-id="346e1-108">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="346e1-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="346e1-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="346e1-109">One Microsoft Way</span></span>

<span data-ttu-id="346e1-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="346e1-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="346e1-111">Copyright &copy; 2021 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="346e1-111">Copyright &copy; 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="346e1-112">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="346e1-112">All rights reserved.</span></span> <span data-ttu-id="346e1-113">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="346e1-114">이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="346e1-115">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="346e1-116">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="346e1-117">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="346e1-118">"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-118">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="346e1-119">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="346e1-120">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="346e1-121">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="346e1-122">작성자:</span><span class="sxs-lookup"><span data-stu-id="346e1-122">Authors:</span></span>

> <span data-ttu-id="346e1-123">**Rob Vettor**, 수석 클라우드 솔루션 설계자 - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span><span class="sxs-lookup"><span data-stu-id="346e1-123">**Rob Vettor**, Principal Cloud Solution Architect - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="346e1-124">**Sander Molenkamp**, 수석 클라우드 설계자/Microsoft MVP - [sandermolenkamp.com](https://www.sandermolenkamp.com), [정보 지원](https://www.infosupport.com/en/)</span><span class="sxs-lookup"><span data-stu-id="346e1-124">**Sander Molenkamp**, Principal Cloud Architect/Microsoft MVP - [sandermolenkamp.com](https://www.sandermolenkamp.com), [Info Support](https://www.infosupport.com/en/)</span></span>
>
> <span data-ttu-id="346e1-125">**Edwin van Wijk**, 수속 솔루션 설계자/Microsoft MVP - [defaultconstructor.com](https://defaultconstructor.com), [정보 지원](https://www.infosupport.com/en/)</span><span class="sxs-lookup"><span data-stu-id="346e1-125">**Edwin van Wijk**, Principal Solution Architect/Microsoft MVP - [defaultconstructor.com](https://defaultconstructor.com), [Info Support](https://www.infosupport.com/en/)</span></span>

<span data-ttu-id="346e1-126">참가자 및 검토자:</span><span class="sxs-lookup"><span data-stu-id="346e1-126">Participants and Reviewers:</span></span>

> <span data-ttu-id="346e1-127">**Mark Russinovich**, Azure CTO 및 기술자, Azure Office of CTO, Microsoft</span><span class="sxs-lookup"><span data-stu-id="346e1-127">**Mark Russinovich**, Azure CTO and Technical Fellow, Azure Office of CTO, Microsoft</span></span>
>
> <span data-ttu-id="346e1-128">**Nish Anil**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="346e1-128">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="346e1-129">**Mark Fussell**, 수석 프로그램 관리자, Azure Incubations, Microsoft</span><span class="sxs-lookup"><span data-stu-id="346e1-129">**Mark Fussell**, Principal Program Manager, Azure Incubations, Microsoft</span></span>
>
> <span data-ttu-id="346e1-130">**Yaron Schneider**, 수석 소프트웨어 엔지니어, Azure Incubations, Microsoft</span><span class="sxs-lookup"><span data-stu-id="346e1-130">**Yaron Schneider**, Principal Software Engineer, Azure Incubations, Microsoft</span></span>
>
> <span data-ttu-id="346e1-131">**Ori Zohar**, 선임 프로그램 관리자, Azure Incubations, Microsoft</span><span class="sxs-lookup"><span data-stu-id="346e1-131">**Ori Zohar**, Senior Program Manager, Azure Incubations, Microsoft</span></span>

<span data-ttu-id="346e1-132">편집자:</span><span class="sxs-lookup"><span data-stu-id="346e1-132">Editors:</span></span>

> <span data-ttu-id="346e1-133">**David Pine**, 선임 콘텐츠 개발자, Microsoft .NET 팀</span><span class="sxs-lookup"><span data-stu-id="346e1-133">**David Pine**, Senior Content Developer, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="346e1-134">**Maira Wenzel**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="346e1-134">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="346e1-135">버전</span><span class="sxs-lookup"><span data-stu-id="346e1-135">Version</span></span>

<span data-ttu-id="346e1-136">이 안내서는 **Dapr 1.0** 버전의 내용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-136">This guide has been written to cover the **Dapr 1.0** version.</span></span> <span data-ttu-id="346e1-137">.NET Core 샘플은 **.NET Core 3.1** 을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-137">.NET Core samples are based on **.NET Core 3.1**.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="346e1-138">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="346e1-138">Who should use this guide</span></span>

<span data-ttu-id="346e1-139">이 가이드의 주요 대상 사용자는 클라우드용으로 설계된 애플리케이션을 구축하는 방법을 알아보려는 개발자, 개발 책임자 및 설계자입니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-139">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="346e1-140">보조 대상은 클라우드 네이티브 접근 방법을 사용하여 애플리케이션을 빌드할지 여부를 선택하는 기술 의사 결정자입니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-140">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="346e1-141">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="346e1-141">How you can use this guide</span></span>

<span data-ttu-id="346e1-142">이 가이드는 [PDF](https://aka.ms/dapr-ebook) 양식과 온라인에서 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-142">This guide is available both in [PDF](https://aka.ms/dapr-ebook) form and online.</span></span> <span data-ttu-id="346e1-143">이러한 항목에 관한 일반적인 이해를 돕기 위해 이 문서 또는 온라인 버전 링크를 팀에 전달하세요.</span><span class="sxs-lookup"><span data-stu-id="346e1-143">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="346e1-144">이러한 항목은 대부분은 기본 원칙 및 패턴에 대한 일관된 이해를 도와주고 항목 관련 결정에 포함되는 장단점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-144">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="346e1-145">이 문서의 목표는 팀 및 리더에게 애플리케이션의 아키텍처, 개발 및 호스팅과 관련하여 올바른 결정을 내리는 데 필요한 정보를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="346e1-145">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="346e1-146">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="346e1-146">Send your feedback</span></span>

<span data-ttu-id="346e1-147">이 책과 관련 샘플은 지속적으로 진화합니다. 여러분의 피드백을 기다리고 있습니다!</span><span class="sxs-lookup"><span data-stu-id="346e1-147">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="346e1-148">이 책을 향상시킬 수 있는 방법에 대한 의견이 있으면 [GitHub 문제](https://github.com/dotnet/docs/issues)에 빌드된 페이지의 맨 아래에서 피드백 섹션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="346e1-148">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="346e1-149">다음</span><span class="sxs-lookup"><span data-stu-id="346e1-149">Next</span></span>](foreword.md)
