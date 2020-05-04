---
title: Azure용 클라우드 네이티브 .NET 애플리케이션 설계
description: Azure의 컨테이너, 마이크로 서비스 및 서버리스 기능을 활용하여 클라우드 네이티브 애플리케이션을 빌드하는 방법을 보여 주는 가이드입니다.
author: ardalis
ms.date: 04/23/2020
ms.openlocfilehash: 24d5c75fc5d2e5623892e8f83daea52553d13765
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507392"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="02310-103">Azure용 클라우드 네이티브 .NET 애플리케이션 설계</span><span class="sxs-lookup"><span data-stu-id="02310-103">Architecting Cloud Native .NET Applications for Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![표지 이미지](./media/cover.png)

<span data-ttu-id="02310-105">게시자:</span><span class="sxs-lookup"><span data-stu-id="02310-105">PUBLISHED BY</span></span>

<span data-ttu-id="02310-106">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="02310-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="02310-107">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="02310-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="02310-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="02310-108">One Microsoft Way</span></span>

<span data-ttu-id="02310-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="02310-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="02310-110">Copyright &copy; 2019 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="02310-110">Copyright &copy; 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="02310-111">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="02310-111">All rights reserved.</span></span> <span data-ttu-id="02310-112">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02310-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="02310-113">이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="02310-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="02310-114">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02310-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="02310-115">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="02310-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="02310-116">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02310-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="02310-117">"상표" 웹 페이지의 https://www.microsoft.com 에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="02310-117">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="02310-118">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="02310-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="02310-119">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02310-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="02310-120">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="02310-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="02310-121">작성자:</span><span class="sxs-lookup"><span data-stu-id="02310-121">Authors:</span></span>

> <span data-ttu-id="02310-122">**Rob Vettor**, 수석 클라우드 시스템 설계자/IP 설계자 - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span><span class="sxs-lookup"><span data-stu-id="02310-122">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="02310-123">**Steve "ardalis" Smith**, 소프트웨어 설계자이자 강사 - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="02310-123">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="02310-124">참가자 및 검토자:</span><span class="sxs-lookup"><span data-stu-id="02310-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="02310-125">**Cesar De la torre**, 수석 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="02310-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="02310-126">**Nish Anil**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="02310-126">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="02310-127">**Jeremy Likness**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="02310-127">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="02310-128">**Cecil Phillip**, 선임 Cloud Advocate, Microsoft</span><span class="sxs-lookup"><span data-stu-id="02310-128">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="02310-129">eShopOnContainers에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="02310-129">Learn more about eShopOnContainers</span></span>

<span data-ttu-id="02310-130">편집자:</span><span class="sxs-lookup"><span data-stu-id="02310-130">Editors:</span></span>

> <span data-ttu-id="02310-131">**Maira Wenzel**, 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="02310-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="02310-132">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="02310-132">Who should use this guide</span></span>

<span data-ttu-id="02310-133">이 가이드의 주요 대상 사용자는 클라우드용으로 설계된 애플리케이션을 구축하는 방법을 알아보려는 개발자, 개발 책임자 및 설계자입니다.</span><span class="sxs-lookup"><span data-stu-id="02310-133">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="02310-134">보조 대상은 클라우드 네이티브 접근 방법을 사용하여 애플리케이션을 빌드할지 여부를 선택하는 기술 의사 결정자입니다.</span><span class="sxs-lookup"><span data-stu-id="02310-134">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="02310-135">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="02310-135">How you can use this guide</span></span>

<span data-ttu-id="02310-136">이 가이드에서는 클라우드 네이티브를 정의하고 클라우드 네이티브 원칙 및 기술을 사용하여 빌드된 참조 애플리케이션을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="02310-136">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="02310-137">처음 두 장을 제외한 나머지 부분은 대부분의 클라우드 네이티브 애플리케이션에 공통된 항목을 중심으로 세부 장들로 분류되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02310-137">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="02310-138">해당 장으로 바로 이동하여 클라우드 네이티브 접근 방식에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02310-138">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="02310-139">데이터 및 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="02310-139">Data and data access</span></span>
- <span data-ttu-id="02310-140">통신 패턴</span><span class="sxs-lookup"><span data-stu-id="02310-140">Communication patterns</span></span>
- <span data-ttu-id="02310-141">크기 조정 및 확장성</span><span class="sxs-lookup"><span data-stu-id="02310-141">Scaling and scalability</span></span>
- <span data-ttu-id="02310-142">애플리케이션 복원력</span><span class="sxs-lookup"><span data-stu-id="02310-142">Application resiliency</span></span>
- <span data-ttu-id="02310-143">모니터링 및 상태</span><span class="sxs-lookup"><span data-stu-id="02310-143">Monitoring and health</span></span>
- <span data-ttu-id="02310-144">ID 및 보안</span><span class="sxs-lookup"><span data-stu-id="02310-144">Identity and security</span></span>
- <span data-ttu-id="02310-145">DevOps</span><span class="sxs-lookup"><span data-stu-id="02310-145">DevOps</span></span>

<span data-ttu-id="02310-146">이 가이드는 PDF 양식과 온라인에서 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02310-146">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="02310-147">이러한 항목에 관한 일반적인 이해를 돕기 위해 이 문서 또는 온라인 버전 링크를 팀에 전달하세요.</span><span class="sxs-lookup"><span data-stu-id="02310-147">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="02310-148">이러한 항목은 대부분은 기본 원칙 및 패턴에 대한 일관된 이해를 도와주고 항목 관련 결정에 포함되는 장단점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02310-148">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="02310-149">이 문서의 목표는 팀 및 리더에게 애플리케이션의 아키텍처, 개발 및 호스팅과 관련하여 올바른 결정을 내리는 데 필요한 정보를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02310-149">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="02310-150">다음</span><span class="sxs-lookup"><span data-stu-id="02310-150">Next</span></span>](introduction.md)
