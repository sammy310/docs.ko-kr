---
title: .NET 5를 사용하여 Windows 10의 데스크톱 앱 현대화
description: .NET 5를 사용하여 기존 데스크톱 앱을 현대화하는 방법 알아보기
ms.date: 01/06/2021
ms.openlocfilehash: de8a451b0598b5eabd99028d377c161dace61623
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615708"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-5"></a><span data-ttu-id="5225b-103">.NET 5를 사용하여 Windows 10의 데스크톱 앱 현대화</span><span class="sxs-lookup"><span data-stu-id="5225b-103">Modernizing Desktop Apps on Windows 10 with .NET 5</span></span>

![데스크톱 앱 현대화 eBook 표지를 보여 주는 스크린샷.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

<span data-ttu-id="5225b-105">**EDITION v1.0.1** - .NET 5로 업데이트됨</span><span class="sxs-lookup"><span data-stu-id="5225b-105">**EDITION v1.0.1** - Updated to .NET 5</span></span>

<span data-ttu-id="5225b-106">책 업데이트 및 커뮤니티 기여에 대한 자세한 내용은 [changelog](https://aka.ms/desktop-ebook-changelog)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5225b-106">Refer [changelog](https://aka.ms/desktop-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="5225b-107">게시자:</span><span class="sxs-lookup"><span data-stu-id="5225b-107">PUBLISHED BY</span></span>

<span data-ttu-id="5225b-108">Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀</span><span class="sxs-lookup"><span data-stu-id="5225b-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="5225b-109">Microsoft Corporation의 사업부</span><span class="sxs-lookup"><span data-stu-id="5225b-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="5225b-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="5225b-110">One Microsoft Way</span></span>

<span data-ttu-id="5225b-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="5225b-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="5225b-112">Copyright © 2021 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5225b-112">Copyright © 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="5225b-113">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="5225b-113">All rights reserved.</span></span> <span data-ttu-id="5225b-114">이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="5225b-115">이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="5225b-116">URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-116">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="5225b-117">여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="5225b-118">실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="5225b-119">"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="5225b-120">Mac 및 macOS는 Apple Inc.의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="5225b-121">기타 모든 표시와 로고는 해당 소유자의 자산입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="5225b-122">공동 작성자:</span><span class="sxs-lookup"><span data-stu-id="5225b-122">Co-Authors:</span></span>

> <span data-ttu-id="5225b-123">**Olia Gavrysh**, 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-123">**Olia Gavrysh**, Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5225b-124">**Miguel Angel Castejón Dominguez**, 혁신 설계자, Kabel</span><span class="sxs-lookup"><span data-stu-id="5225b-124">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span></span>

<span data-ttu-id="5225b-125">참가자 및 검토자:</span><span class="sxs-lookup"><span data-stu-id="5225b-125">Participants and reviewers:</span></span>

> <span data-ttu-id="5225b-126">**Maira Wenzel**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-126">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5225b-127">**Andy De Gorge**, 선임 콘텐츠 개발자, .NET 문서 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-127">**Andy De Gorge**, Senior Content Developer, .NET docs team, Microsoft</span></span>

> <span data-ttu-id="5225b-128">**Miguel Ramos**, 선임 프로그램 관리자, Windows 개발자 플랫폼 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-128">**Miguel Ramos**, Senior Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="5225b-129">**Adam Braden**, 수석 프로그램 관리자, Windows 개발자 플랫폼 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-129">**Adam Braden**, Principal Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="5225b-130">**Ricardo Minguez Pablos**, 선임 프로그램 관리자, Azure IoT 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-130">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT team, Microsoft</span></span>

> <span data-ttu-id="5225b-131">**Nish Anil**, 선임 프로그램 관리자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-131">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5225b-132">**Beth Massi**, 선임 제품 마케팅 관리자, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-132">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span></span>

> <span data-ttu-id="5225b-133">**Scott Hunter**, 파트너 프로그램 관리 책임자, .NET 팀, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5225b-133">**Scott Hunter**, Partner Director Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5225b-134">**Marta Fuentes Lara**, Kabel</span><span class="sxs-lookup"><span data-stu-id="5225b-134">**Marta Fuentes Lara**, Kabel</span></span>

> <span data-ttu-id="5225b-135">**Raúl Fernández de Córdoba**, Kabel</span><span class="sxs-lookup"><span data-stu-id="5225b-135">**Raúl Fernández de Córdoba**, Kabel</span></span>

> <span data-ttu-id="5225b-136">**Antonio Manuel Fernández Cantos**, Kabel</span><span class="sxs-lookup"><span data-stu-id="5225b-136">**Antonio Manuel Fernández Cantos**, Kabel</span></span>

## <a name="introduction"></a><span data-ttu-id="5225b-137">소개</span><span class="sxs-lookup"><span data-stu-id="5225b-137">Introduction</span></span>

<span data-ttu-id="5225b-138">현대화 과정을 통해 기존 데스크톱 애플리케이션을 이동하고 최신 런타임, 언어 및 플랫폼 기능을 통합하기 위해 채택할 수 있는 전략에 대한 책입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-138">This book is about strategies you can adopt to move your existing desktop applications through the path of modernization and incorporate the latest runtime, language, and platform features.</span></span> <span data-ttu-id="5225b-139">애플리케이션이 서로 다르고 사용자의 요구 사항 및 기본 설정도 다르기 때문에 고유한 레시피는 없다는 것을 알 수 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-139">You'll discover that there's no unique recipe as each application is different, and so are your requirements and preferences.</span></span> <span data-ttu-id="5225b-140">좋은 소식은, 애플리케이션에 새로운 기능을 추가하기 위해 적용할 수 있는 일반적인 방법이 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-140">The good news is that there are common approaches you can apply to add new features and capabilities to your applications.</span></span> <span data-ttu-id="5225b-141">심지어 그중 일부는 코드를 크게 수정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-141">Some of them won't even require major modifications of your code.</span></span> <span data-ttu-id="5225b-142">이 책에서는 모든 해당 기능이 백그라운드에서 어떻게 작동하는지 보여 주고 해당 기능의 구현 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-142">In this book, we'll reveal how all those features work behind the scenes and explain the mechanics of their implementations.</span></span> <span data-ttu-id="5225b-143">또한 프로젝트 개발에 대한 영감을 얻을 수 있도록 기존 데스크톱 애플리케이션을 현대화하는 과정을 구체적으로 보여 주는 일반적인 시나리오를 몇 가지 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-143">Moreover, you'll find some common scenarios for modernizing existing desktop applications shown in detail so you can find inspiration for evolving your projects.</span></span>

<span data-ttu-id="5225b-144">기존 애플리케이션을 현대화하는 Microsoft의 접근 방식은 사용자 지정 경로를 유연하게 만들 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-144">Microsoft's approach to modernizing existing applications is to give you the flexibility to create your own customized path.</span></span> <span data-ttu-id="5225b-145">이 책에서 설명하는 모든 현대화 전략은 대부분 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-145">All the modernization strategies described in this book are mostly independent.</span></span> <span data-ttu-id="5225b-146">애플리케이션과 관련된 항목을 선택하고 중요하지 않은 항목은 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-146">You can choose ones that are relevant for your application and skip others that aren't important for you.</span></span> <span data-ttu-id="5225b-147">즉, 여러 전략을 혼합하여 애플리케이션 요구를 가장 적절히 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-147">In other words, you can mix and match the strategies to best address your application needs.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="5225b-148">이 책의 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="5225b-148">Who should use the book</span></span>

<span data-ttu-id="5225b-149">이 책은 기존 Windows Forms 및 WPF 데스크톱 애플리케이션을 현대화하여 .NET 및 Windows 10의 이점을 활용하려는 개발자 및 솔루션 설계자를 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-149">This book for developers and solution architects who want to modernize existing Windows Forms and WPF desktop applications to leverage the benefits of .NET and Windows 10.</span></span>

<span data-ttu-id="5225b-150">또한 기존 데스크톱 애플리케이션 업데이트의 이점을 개괄적으로 알고자 하는 엔터프라이즈 설계자 또는 개발 리더나 디렉터와 같은 기술 의사 결정자인 경우 이 책을 유용하게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-150">You might also find this book useful if you're a technical decision maker, such as an enterprise architect or a development lead or director who wants an overview of the benefits of updating existing desktop applications.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="5225b-151">책 사용 방법</span><span class="sxs-lookup"><span data-stu-id="5225b-151">How to use the book</span></span>

<span data-ttu-id="5225b-152">이 책에서는 기존 애플리케이션을 현대화하는 “이유”를 설명하고, .NET 및 MSIX를 사용하여 데스크톱 앱을 현대화하는 경우에 얻게 되는 구체적인 이점을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-152">This book addresses the "why"—why you might want to modernize your existing applications, and the specific benefits you get from using NET and MSIX to modernize your desktop apps.</span></span> <span data-ttu-id="5225b-153">이 책의 내용은 개요를 알고 싶지만 구현과 기술적인 단계별 세부 정보에 대해 중점을 둘 필요가 없는 설계자와 기술 의사 결정자를 위해 고안되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-153">The content of the book is designed for architects and technical decision makers who want an overview, but who don't need to focus on implementation and technical, step-by-step details.</span></span>

<span data-ttu-id="5225b-154">애플리케이션 예제에 대한 완벽한 마이그레이션 프로세스를 소개하는 5장을 포함하여 챕터마다 샘플 구현 코드 조각과 스크린샷을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-154">Along the different chapters, sample implementation code snippets and screenshots are provided, with chapter 5 devoted to showcase a complete migration process for sample applications.</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="5225b-155">이 책에서 다루지 않는 내용</span><span class="sxs-lookup"><span data-stu-id="5225b-155">What this book doesn't cover</span></span>

<span data-ttu-id="5225b-156">이 책에서는 리프트 앤 시프트 시나리오에 중점을 둔 시나리오의 특정 하위 집합에 대해 설명하고, 코드를 다시 작성할 필요 없이 현대화의 이점을 얻는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-156">This book covers a specific subset of scenarios that are focused on lift-and-shift scenarios, outlining the way to gain the benefits of modernizing without the effort of rewriting code.</span></span>

<span data-ttu-id="5225b-157">이 책은 .NET을 사용하여 최신 애플리케이션을 처음부터 개발하는 방법 또는 Windows Forms 및 WPF를 시작하는 방법에 관한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-157">This book isn't about developing modern applications with .NET from scratch or about getting started with Windows Forms and WPF.</span></span> <span data-ttu-id="5225b-158">이 책은 데스크톱 개발을 위해 최신 기술로 기존 데스크톱 애플리케이션을 업데이트하는 방법에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-158">It focuses on how you can update existing desktop applications with the latest technologies for desktop development.</span></span>

## <a name="samples-used-in-this-book"></a><span data-ttu-id="5225b-159">이 책에서 사용하는 샘플</span><span class="sxs-lookup"><span data-stu-id="5225b-159">Samples used in this book</span></span>

<span data-ttu-id="5225b-160">현대화를 수행하는 데 필요한 단계를 강조하기 위해 `eShopModernizing`이라는 애플리케이션 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-160">To highlight the necessary steps to perform a modernization, we'll be using a sample application called `eShopModernizing`.</span></span> <span data-ttu-id="5225b-161">이 애플리케이션에는 Windows Forms와 WPF가 포함되어 있으며, 이 두 가지 모두에서 .NET으로의 현대화를 수행하는 방법에 대한 단계별 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-161">This application has two flavors, Windows Forms and WPF, and we'll show a step-by-step process on how to perform the modernization on both of them to .NET.</span></span>

<span data-ttu-id="5225b-162">또한 이 책의 GitHub 리포지토리에는 단계별 자습서를 수행하기로 결정한 경우에 참조할 수 있는 프로세스 결과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5225b-162">Also, on the GitHub repository for this book, you'll find the results of the process, which you can consult with if you decide to follow the step-by-step tutorial.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="5225b-163">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="5225b-163">Send your feedback</span></span>

<span data-ttu-id="5225b-164">이 책과 관련 샘플은 지속적으로 진화합니다. 여러분의 피드백을 기다리고 있습니다!</span><span class="sxs-lookup"><span data-stu-id="5225b-164">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="5225b-165">이 책을 향상시킬 수 있는 방법에 대한 의견이 있으면 [GitHub 문제](https://github.com/dotnet/docs/issues)에 빌드된 페이지의 맨 아래에서 피드백 섹션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5225b-165">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="5225b-166">다음</span><span class="sxs-lookup"><span data-stu-id="5225b-166">Next</span></span>](why-modern-applications.md)
