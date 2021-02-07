---
title: ASP.NET Web Forms용 Blazor 개발자
description: Blazor 및 .NET Core를 사용하여 .NET을 통해 전체 스택 웹앱을 빌드하는 간단하고 친숙한 방법을 알아보세요.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 02/02/2021
ms.openlocfilehash: 267f7222865c5a92d20faaae41b052da08c284a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653474"
---
# <a name="blazor-for-aspnet-web-forms-developers"></a><span data-ttu-id="cb2eb-103">ASP.NET Web Forms용 Blazor 개발자</span><span class="sxs-lookup"><span data-stu-id="cb2eb-103">Blazor for ASP.NET Web Forms Developers</span></span>

![서버리스 앱 eBook 표지를 보여주는 스크린샷.](./media/index/blazor-for-aspnet-web-forms-developers.png)

> <span data-ttu-id="cb2eb-105">다운로드 위치: <https://aka.ms/blazor-ebook></span><span class="sxs-lookup"><span data-stu-id="cb2eb-105">DOWNLOAD available at: <https://aka.ms/blazor-ebook></span></span>

<span data-ttu-id="cb2eb-106">**버전 v1.0**</span><span class="sxs-lookup"><span data-stu-id="cb2eb-106">**EDITION v1.0**</span></span>

<span data-ttu-id="cb2eb-107">책 업데이트 및 커뮤니티 기여에 대한 자세한 내용은 [changelog](https://aka.ms/blazor-ebook-changelog)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-107">Refer [changelog](https://aka.ms/blazor-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="cb2eb-108">게시자:</span><span class="sxs-lookup"><span data-stu-id="cb2eb-108">PUBLISHED BY</span></span>

<span data-ttu-id="cb2eb-109">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="cb2eb-109">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="cb2eb-110">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="cb2eb-110">A division of Microsoft Corporation</span></span>

<span data-ttu-id="cb2eb-111">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="cb2eb-111">One Microsoft Way</span></span>

<span data-ttu-id="cb2eb-112">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="cb2eb-112">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="cb2eb-113">Copyright © 2021 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="cb2eb-113">Copyright © 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="cb2eb-114">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-114">All rights reserved.</span></span> <span data-ttu-id="cb2eb-115">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-115">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="cb2eb-116">이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-116">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="cb2eb-117">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-117">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="cb2eb-118">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-118">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="cb2eb-119">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-119">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="cb2eb-120">"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-120">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="cb2eb-121">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-121">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="cb2eb-122">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-122">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="cb2eb-123">작성자:</span><span class="sxs-lookup"><span data-stu-id="cb2eb-123">Authors:</span></span>

> <span data-ttu-id="cb2eb-124">**[Daniel Roth](https://github.com/danroth27)** , 수석 프로그램 관리자, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-124">**[Daniel Roth](https://github.com/danroth27)**, Principal Program Manager, Microsoft Corp.</span></span>

> <span data-ttu-id="cb2eb-125">**[Jeff Fritz](https://github.com/csharpfritz)** , 선임 프로그램 관리자, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-125">**[Jeff Fritz](https://github.com/csharpfritz)**, Senior Program Manager, Microsoft Corp.</span></span>

> <span data-ttu-id="cb2eb-126">**[Taylor Southwick](https://github.com/twsouthwick)** , 수석 소프트웨어 엔지니어, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-126">**[Taylor Southwick](https://github.com/twsouthwick)**, Senior Software Engineer, Microsoft Corp.</span></span>

> <span data-ttu-id="cb2eb-127">**[Scott Addie](https://github.com/scottaddie)** , 수석 콘텐츠 개발자, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-127">**[Scott Addie](https://github.com/scottaddie)**, Senior Content Developer, Microsoft Corp.</span></span>

> <span data-ttu-id="cb2eb-128">**[Steve “ardalis” Smith](https://ardalis.com)** , Ardalis Services LLC의 소프트웨어 설계자이자 강사</span><span class="sxs-lookup"><span data-stu-id="cb2eb-128">**[Steve "ardalis" Smith](https://ardalis.com)**, Software Architect and Trainer, Ardalis Services LLC</span></span>

## <a name="introduction"></a><span data-ttu-id="cb2eb-129">소개</span><span class="sxs-lookup"><span data-stu-id="cb2eb-129">Introduction</span></span>

<span data-ttu-id="cb2eb-130">.NET은 모든 종류의 웹앱을 빌드할 수 있는 포괄적인 프레임워크 및 도구 집합인 ASP.NET을 통해 수많은 웹앱의 개발을 지원해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-130">.NET has long supported web app development through ASP.NET, a comprehensive set of frameworks and tools for building any kind of web app.</span></span> <span data-ttu-id="cb2eb-131">ASP.NET에는 클래식 ASP(Active Server Page)를 사용하여 완전히 다시 시작하는 웹 프레임워크 및 기술의 고유한 계보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-131">ASP.NET has its own lineage of web frameworks and technologies starting all the way back with classic Active Server Pages (ASP).</span></span> <span data-ttu-id="cb2eb-132">ASP.NET Web Forms, ASP.NET MVC, ASP.NET 웹 페이지, 최신 ASP.NET Core 등과 같은 프레임워크는 *서버에서 렌더링된* 웹앱을 빌드하는 생산적이고 강력한 방법을 제공합니다. 여기서 UI 콘텐츠는 HTTP 요청에 응답하여 서버에서 동적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-132">Frameworks like ASP.NET Web Forms, ASP.NET MVC, ASP.NET Web Pages, and more recently ASP.NET Core, provide a productive and powerful way to build *server-rendered* web apps, where UI content is dynamically generated on the server in response to HTTP requests.</span></span> <span data-ttu-id="cb2eb-133">ASP.NET 프레임워크마다 사용 대상과 앱 빌드 철학이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-133">Each ASP.NET framework caters to a different audience and app building philosophy.</span></span> <span data-ttu-id="cb2eb-134">ASP.NET Web Forms는 .NET Framework의 원본 릴리스와 함께 제공되며, 간단한 이벤트 처리를 지원하는 재사용 가능한 UI 컨트롤과 같이 데스크톱 개발자에게 익숙한 많은 패턴을 사용하여 웹 개발을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-134">ASP.NET Web Forms shipped with the original release of the .NET Framework and enabled web development using many of the patterns familiar to desktop developers, like reusable UI controls with simple event handling.</span></span> <span data-ttu-id="cb2eb-135">하지만 ASP.NET 제품에서는 사용자의 브라우저에서 실행되는 코드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-135">However, none of the ASP.NET offerings provide a way to run code that executed in the user's browser.</span></span> <span data-ttu-id="cb2eb-136">이렇게 하려면 JavaScript를 작성하고 jQuery, Knockout, Angular, React 등과 같은 다양한 JavaScript 프레임워크 및 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-136">To do that requires writing JavaScript and using any of the many JavaScript frameworks and tools that have phased in and out of popularity over the years: jQuery, Knockout, Angular, React, and so on.</span></span>

<span data-ttu-id="cb2eb-137">[Blazor](https://blazor.net)는 .NET을 사용하여 웹앱을 빌드할 때 가능한 항목을 변경하는 새로운 웹 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-137">[Blazor](https://blazor.net) is a new web framework that changes what is possible when building web apps with .NET.</span></span> <span data-ttu-id="cb2eb-138">Blazor는 JavaScript 대신 C#을 기반으로 하는 클라이언트 쪽 웹 UI 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-138">Blazor is a client-side web UI framework based on C# instead of JavaScript.</span></span> <span data-ttu-id="cb2eb-139">Blazor를 사용하면 C#으로 클라이언트 쪽 논리 및 UI 구성 요소를 작성하여 일반 .NET 어셈블리로 컴파일한 다음, WebAssembly라는 새로운 개방형 웹 표준을 사용하여 브라우저에서 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-139">With Blazor you can write your client-side logic and UI components in C#, compile them into normal .NET assemblies, and then run them directly in the browser using a new open web standard called WebAssembly.</span></span> <span data-ttu-id="cb2eb-140">또는 Blazor가 서버에서 .NET UI 구성 요소를 실행하고 브라우저를 사용하여 실시간 연결을 통해 모든 UI 상호 작용을 유동적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-140">Or alternatively, Blazor can run your .NET UI components on the server and handle all UI interactions fluidly over a real-time connection with the browser.</span></span> <span data-ttu-id="cb2eb-141">서버에서 실행되는 .NET과 연결된 경우 Blazor는 .NET을 통해 전체 스택 웹 개발을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-141">When paired with .NET running on the server, Blazor enables full-stack web development with .NET.</span></span> <span data-ttu-id="cb2eb-142">Blazor는 ASP.NET Web Forms와 많은 공통점을 공유하고(예: 재사용 가능한 구성 요소 모델 사용, 사용자 이벤트를 처리하는 간단한 방법), .NET을 기반으로 빌드되어 최신의 고성능 웹 개발 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-142">While Blazor shares many commonalities with ASP.NET Web Forms, like having a reusable component model and a simple way to handle user events, it also builds on the foundations of .NET to provide a modern and high-performance web development experience.</span></span>

<span data-ttu-id="cb2eb-143">이 책에서는 ASP.NET Web Forms 개발자에게 친숙하고 편리한 방식으로 Blazor를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-143">This book introduces ASP.NET Web Forms developers to Blazor in a way that is familiar and convenient.</span></span> <span data-ttu-id="cb2eb-144">Blazor 개념을 ASP.NET Web Forms의 유사 개념과 함께 소개하는 한편, 친숙하지 않은 새로운 개념도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-144">It introduces Blazor concepts in parallel with analogous concepts in ASP.NET Web Forms while also explaining new concepts that may be less familiar.</span></span> <span data-ttu-id="cb2eb-145">구성 요소 제작, 라우팅, 레이아웃, 구성, 보안 등 광범위한 항목과 문제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-145">It covers a broad range of topics and concerns including component authoring, routing, layout, configuration, and security.</span></span> <span data-ttu-id="cb2eb-146">이 책의 내용은 주로 새로운 개발을 지원하기 위한 것이지만, 기존 앱을 현대화하려는 경우에 사용할 수 있도록 기존 ASP.NET Web Forms를 Blazor로 마이그레이션하기 위한 지침과 전략에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-146">And while the content of this book is primarily for enabling new development, it also covers guidelines and strategies for migrating existing ASP.NET Web Forms to Blazor for when you want to modernize an existing app.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="cb2eb-147">이 책의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="cb2eb-147">Who should use the book</span></span>

<span data-ttu-id="cb2eb-148">이 책은 기존 지식 및 기술과 관련된 Blazor를 도입하려는 ASP.NET Web Forms 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-148">This book is for ASP.NET Web Forms developers looking for an introduction to Blazor that relates to their existing knowledge and skills.</span></span> <span data-ttu-id="cb2eb-149">이 책을 활용하여 새 Blazor 기반 프로젝트를 빠르게 시작하거나 기존 ASP.NET Web Forms 애플리케이션의 현대화를 위한 로드맵 차트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-149">This book can help with quickly getting started on a new Blazor-based project or to help chart a roadmap for modernizing an existing ASP.NET Web Forms application.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="cb2eb-150">책 사용 방법</span><span class="sxs-lookup"><span data-stu-id="cb2eb-150">How to use the book</span></span>

<span data-ttu-id="cb2eb-151">이 책의 1부에서는 Blazor가 무엇인지를 설명하고 ASP.NET Web Forms를 사용한 웹앱 개발과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-151">The first part of this book covers what Blazor is and compares it to web app development with ASP.NET Web Forms.</span></span> <span data-ttu-id="cb2eb-152">그런 다음, 다양한 Blazor 항목을 장별로 설명하고 각 Blazor 개념을 ASP.NET Web Forms의 해당 개념과 관련시키거나 완전히 새로운 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-152">The book then covers a variety of Blazor topics, chapter by chapter, and relates each Blazor concept to the corresponding concept in ASP.NET Web Forms, or explains fully any completely new concepts.</span></span> <span data-ttu-id="cb2eb-153">또한 이 책에서는 ASP.NET Web Forms와 Blazor 둘 다로 구현된 전체 샘플 앱을 정기적으로 참조하여 Blazor 기능을 시연하고 ASP.NET Web Forms에서 Blazor로 마이그레이션하는 사례 연구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-153">The book also refers regularly to a complete sample app implemented in both ASP.NET Web Forms and Blazor to demonstrate Blazor features and to provide a case study for migrating from ASP.NET Web Forms to Blazor.</span></span> <span data-ttu-id="cb2eb-154">[GitHub](https://github.com/dotnet-architecture/eshoponblazor)에서 두 가지 샘플 앱 구현(ASP.NET Web Forms 및 Blazor 버전)을 모두 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-154">You can find both implementations of the sample app (ASP.NET Web Forms and Blazor versions) on [GitHub](https://github.com/dotnet-architecture/eshoponblazor).</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="cb2eb-155">이 책에서 다루지 않는 내용</span><span class="sxs-lookup"><span data-stu-id="cb2eb-155">What this book doesn't cover</span></span>

<span data-ttu-id="cb2eb-156">이 책은 Blazor를 소개하지만, 포괄적인 마이그레이션 가이드는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-156">This book is an introduction to Blazor, not a comprehensive migration guide.</span></span> <span data-ttu-id="cb2eb-157">ASP.NET Web Forms에서 Blazor로 프로젝트를 마이그레이션하는 방법에 대한 지침을 포함하고 있지만, 미묘한 차이나 세부 사항은 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-157">While it does include guidance on how to approach migrating a project from ASP.NET Web Forms to Blazor, it does not attempt to cover every nuance and detail.</span></span> <span data-ttu-id="cb2eb-158">ASP.NET에서 ASP.NET Core로 마이그레이션하는 방법에 대한 일반적인 지침은 ASP.NET Core 설명서의 [마이그레이션 지침](/aspnet/core/migration/proper-to-2x/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-158">For more general guidance on migrating from ASP.NET to ASP.NET Core, refer to the [migration guidance](/aspnet/core/migration/proper-to-2x/) in the ASP.NET Core documentation.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="cb2eb-159">추가 자료</span><span class="sxs-lookup"><span data-stu-id="cb2eb-159">Additional resources</span></span>

<span data-ttu-id="cb2eb-160"><https://blazor.net>에서 공식 Blazor 홈페이지 및 설명서를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-160">You can find the official Blazor home page and documentation at <https://blazor.net>.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="cb2eb-161">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="cb2eb-161">Send your feedback</span></span>

<span data-ttu-id="cb2eb-162">이 책과 관련 샘플은 지속적으로 진화합니다. 여러분의 피드백을 기다리고 있습니다!</span><span class="sxs-lookup"><span data-stu-id="cb2eb-162">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="cb2eb-163">이 책을 향상시킬 수 있는 방법에 대한 의견이 있으면 [GitHub 문제](https://github.com/dotnet/docs/issues)에 빌드된 페이지의 맨 아래에서 피드백 섹션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="cb2eb-163">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="cb2eb-164">다음</span><span class="sxs-lookup"><span data-stu-id="cb2eb-164">Next</span></span>](introduction.md)
