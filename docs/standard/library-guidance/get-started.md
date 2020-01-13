---
title: 고품질 .NET 라이브러리 만들기 시작
description: .NET 라이브러리 빌드를 시작합니다.
ms.date: 10/02/2018
ms.openlocfilehash: 10576219d8470a171ad0f1f347196999b2a2ee03
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706493"
---
# <a name="get-started"></a><span data-ttu-id="6a310-103">시작</span><span class="sxs-lookup"><span data-stu-id="6a310-103">Get started</span></span>

## <a name="cross-platform-targetingcross-platform-targetingmd"></a>[<span data-ttu-id="6a310-104">플랫폼 간 대상 지정</span><span class="sxs-lookup"><span data-stu-id="6a310-104">Cross-platform targeting</span></span>](./cross-platform-targeting.md)

<span data-ttu-id="6a310-105">.NET Standard 및 멀티 타기팅을 사용하여 플랫폼 간 라이브러리를 만드는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-105">How to use .NET Standard and multi-targeting to create cross-platform libraries.</span></span> <span data-ttu-id="6a310-106">.NET은 많은 장소에서 실행되며, 좋은 .NET 라이브러리는 가능한 한 많은 플랫폼과 개발자를 지원하려고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-106">.NET runs in many places, and good .NET libraries should strive to support as many platforms and developers as possible.</span></span>

## <a name="strong-namingstrong-namingmd"></a>[<span data-ttu-id="6a310-107">강력한 이름 지정</span><span class="sxs-lookup"><span data-stu-id="6a310-107">Strong naming</span></span>](./strong-naming.md)

<span data-ttu-id="6a310-108">강력한 이름 지정과 장점 및 단점에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-108">Learn about strong naming and its advantages and disadvantages.</span></span> <span data-ttu-id="6a310-109">.NET 라이브러리에 강력한 이름을 지정하면 대부분의 개발자가 라이브러리를 사용할 수 있으므로 권장되는 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-109">Strong naming a .NET library allows the most developers to use it and is a recommended best practice.</span></span>

## <a name="nuget-and-open-source-librariesnugetmd"></a>[<span data-ttu-id="6a310-110">NuGet 및 오픈 소스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="6a310-110">NuGet and open-source libraries</span></span>](./nuget.md)

<span data-ttu-id="6a310-111">NuGet.org에 공개적으로 게시된 모든 패키지에 대한 권장 메타데이터를 포함하여 오픈 소스 .NET 라이브러리용 NuGet 패키지를 만드는 최상의 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-111">The best way to create NuGet packages for open-source .NET libraries, including recommended metadata for all packages published publicly on NuGet.org.</span></span>

### <a name="dependenciesdependenciesmd"></a>[<span data-ttu-id="6a310-112">종속성</span><span class="sxs-lookup"><span data-stu-id="6a310-112">Dependencies</span></span>](./dependencies.md)

<span data-ttu-id="6a310-113">NuGet을 사용하면 .NET 라이브러리를 빌드할 때 기존 패키지를 쉽게 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-113">NuGet makes it easy to use existing packages when building a .NET library.</span></span> <span data-ttu-id="6a310-114">NuGet 종속성의 일반적인 마찰 소스와 이를 방지하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-114">Learn about NuGet dependencies' common sources of friction and how to avoid them.</span></span>

### <a name="source-linksourcelinkmd"></a>[<span data-ttu-id="6a310-115">소스 링크</span><span class="sxs-lookup"><span data-stu-id="6a310-115">Source Link</span></span>](./sourcelink.md)

<span data-ttu-id="6a310-116">소스 링크는 .NET 라이브러리의 사용자가 디버그하는 동안 해당 소스 코드를 한 단계씩 실행할 수 있게 해주는 훌륭한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-116">Source Link is a great tool that allows users of your .NET library to step into its source code while debugging.</span></span> <span data-ttu-id="6a310-117">이 문서는 소스 링크란 무엇이고 왜 사용해야 하는지에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-117">This article is an overview of what Source Link is and why you should use it.</span></span>

### <a name="publishingpublish-nuget-packagemd"></a>[<span data-ttu-id="6a310-118">게시</span><span class="sxs-lookup"><span data-stu-id="6a310-118">Publishing</span></span>](./publish-nuget-package.md)

<span data-ttu-id="6a310-119">NuGet.org가 가장 널리 알려지고 사용되는 리포지토리지만, NuGet 패키지는 여러 장소에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-119">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages.</span></span> <span data-ttu-id="6a310-120">사용할 수 있는 다양한 NuGet 패키지 리포지토리와 .NET 라이브러리 게시에 대한 보안 모범 사례를 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-120">Learn about the different NuGet package repositories available, and security best practices for publishing a .NET library.</span></span>

## <a name="versioningversioningmd"></a>[<span data-ttu-id="6a310-121">버전 관리</span><span class="sxs-lookup"><span data-stu-id="6a310-121">Versioning</span></span>](./versioning.md)

<span data-ttu-id="6a310-122">훌륭한 .NET 라이브러리는 시간이 지남에 따라 발전하며, 이후 릴리스에서 기능을 추가하고, 버그를 수정하고, 성능을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-122">Good .NET libraries evolve over time, adding features, fixing bugs, and improving performance in later releases.</span></span> <span data-ttu-id="6a310-123">다양한 버전 번호와 개발자에게 호환성이 손상되는 변경 사항을 전달하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-123">Learn about the various version numbers and how to communicate breaking changes to developers.</span></span>

### <a name="breaking-changesbreaking-changesmd"></a>[<span data-ttu-id="6a310-124">주요 변경 사항</span><span class="sxs-lookup"><span data-stu-id="6a310-124">Breaking changes</span></span>](./breaking-changes.md)

<span data-ttu-id="6a310-125">.NET 라이브러리에서 기존 사용자를 위한 안정성과 미래를 위한 혁신 간에 균형을 맞추는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-125">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="6a310-126">이전 버전과의 호환성을 유지하면서 새로운 기능을 추가하기 위한, 여러 종류의 호환성이 손상되는 변경 및 전략에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6a310-126">Learn about the different kinds of breaking changes and strategies for adding new features while maintaining backwards compatibility.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6a310-127">[이전](index.md)
>[다음](cross-platform-targeting.md)</span><span class="sxs-lookup"><span data-stu-id="6a310-127">[Previous](index.md)
[Next](cross-platform-targeting.md)</span></span>
