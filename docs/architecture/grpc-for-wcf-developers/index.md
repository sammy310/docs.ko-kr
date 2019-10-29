---
title: WCF 개발자를 위한 ASP.NET Core gRPC - WCF 개발자를 위한 gRPC
description: 작성할 항목
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6a5b4f6d0b47a272f7a753e22bfd61b06202944a
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919384"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="e8818-103">WCF 개발자를 위한 ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e8818-103">ASP.NET Core gRPC for WCF Developers</span></span>

![표지 이미지](./media/cover.png)

<span data-ttu-id="e8818-105">게시자:</span><span class="sxs-lookup"><span data-stu-id="e8818-105">PUBLISHED BY</span></span>

<span data-ttu-id="e8818-106">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="e8818-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="e8818-107">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="e8818-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="e8818-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e8818-108">One Microsoft Way</span></span>

<span data-ttu-id="e8818-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="e8818-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="e8818-110">Copyright © 2019 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="e8818-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="e8818-111">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="e8818-111">All rights reserved.</span></span> <span data-ttu-id="e8818-112">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="e8818-113">이 가이드는 작성자의 견해와 의견을 “있는 그대로” 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="e8818-114">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="e8818-115">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="e8818-116">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="e8818-117">“상표” 웹 페이지의 https://www.microsoft.com 에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="e8818-118">Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="e8818-119">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="e8818-120">만든 이:</span><span class="sxs-lookup"><span data-stu-id="e8818-120">Author:</span></span>

> <span data-ttu-id="e8818-121">**Mark Rendle** - 최고 기술 책임자 - [Visual Recode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="e8818-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="e8818-122">**Miranda Steiner** - 기술 작성자</span><span class="sxs-lookup"><span data-stu-id="e8818-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="e8818-123">편집자:</span><span class="sxs-lookup"><span data-stu-id="e8818-123">Editors:</span></span>

> <span data-ttu-id="e8818-124">**Maira Wenzel** - 선임 콘텐츠 개발자 - Microsoft</span><span class="sxs-lookup"><span data-stu-id="e8818-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="e8818-125">소개</span><span class="sxs-lookup"><span data-stu-id="e8818-125">Introduction</span></span>

<span data-ttu-id="e8818-126">TODO</span><span class="sxs-lookup"><span data-stu-id="e8818-126">TODO</span></span>

## <a name="purpose"></a><span data-ttu-id="e8818-127">용도</span><span class="sxs-lookup"><span data-stu-id="e8818-127">Purpose</span></span>

<span data-ttu-id="e8818-128">TODO</span><span class="sxs-lookup"><span data-stu-id="e8818-128">TODO</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="e8818-129">이 가이드의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="e8818-129">Who should use this guide</span></span>

<span data-ttu-id="e8818-130">**이 항목 업데이트**</span><span class="sxs-lookup"><span data-stu-id="e8818-130">**UPDATE THIS**</span></span>

<span data-ttu-id="e8818-131">이 가이드의 대상 사용자는 gRPC 서비스를 사용하여 .NET Framework 4 이전 버전의 WCF 솔루션을 ASP.NET Core 3.0으로 마이그레이션하려는 WCF 개발자, 개발 책임자 및 설계자입니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-131">The audience for this guide is WCF developers, development leads, and architects who are interested in migrating WCF solutions on .NET Framework 4 and earlier to ASP.NET Core 3.0 using gRPC services.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="e8818-132">이 가이드를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="e8818-132">How you can use this guide</span></span>

<span data-ttu-id="e8818-133">**이 항목 업데이트**</span><span class="sxs-lookup"><span data-stu-id="e8818-133">**UPDATE THIS**</span></span>

<span data-ttu-id="e8818-134">다음은 WCF에 대한 특정 참조를 유사한 플랫폼으로 사용하여 ASP.NET Core 3.0에서 gRPC 서비스를 빌드하는 방법에 대한 간략한 소개입니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-134">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="e8818-135">여기서는 각 개념을 WCF의 해당 기능과 연계하여 gRPC의 원칙을 설명하고 기존 WCF 애플리케이션을 gRPC로 마이그레이션하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-135">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="e8818-136">또한 WCF를 경험하고 새 서비스를 빌드하기 위해 gRPC를 알아보려는 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-136">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="e8818-137">애플리케이션 예제를 사용자 프로젝트를 위한 템플릿 또는 참조로 사용하고, 가이드 또는 샘플에서 코드를 복사하여 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-137">The sample application can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="e8818-138">이 가이드를 팀에서 자유롭게 공유하고 이러한 여러가지 고려 사항과 기회에 대한 이해를 도모하세요.</span><span class="sxs-lookup"><span data-stu-id="e8818-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="e8818-139">모든 사람이 공통적인 용어와 기본 원칙으로 작업하도록 하면 아키텍처 패턴및 사례를 일관성 있게 적용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8818-139">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="e8818-140">참조</span><span class="sxs-lookup"><span data-stu-id="e8818-140">References</span></span>

- <span data-ttu-id="e8818-141">**gRPC 웹 사이트**</span><span class="sxs-lookup"><span data-stu-id="e8818-141">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="e8818-142">**서버 앱에 대해 .NET Core와 .NET Framework 중에 선택**</span><span class="sxs-lookup"><span data-stu-id="e8818-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="e8818-143">다음</span><span class="sxs-lookup"><span data-stu-id="e8818-143">Next</span></span>](introduction.md)
