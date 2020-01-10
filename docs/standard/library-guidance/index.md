---
title: 오픈 소스 .NET 라이브러리 지침
description: 고품질 .NET 라이브러리를 만드는 개발자를 위한 모범 사례 권장 사항입니다.
ms.date: 10/17/2018
ms.openlocfilehash: c1e1c302eede86fd5555a8e84630e216e96f1ce7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706454"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="3c2cf-103">오픈 소스 라이브러리 지침</span><span class="sxs-lookup"><span data-stu-id="3c2cf-103">Open-source library guidance</span></span>

<span data-ttu-id="3c2cf-104">이 지침에서는 고품질 .NET 라이브러리를 만드는 개발자를 위한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="3c2cf-105">이 설명서는 .NET 라이브러리를 빌드하는 경우 *방법*이 아닌 *내용* 및 *이유*에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="3c2cf-106">고품질 오픈 소스 .NET 라이브러리의 측면:</span><span class="sxs-lookup"><span data-stu-id="3c2cf-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="3c2cf-107">**포괄적** - 우수한 .NET 라이브러리는 여러 플랫폼, 프로그래밍 언어 및 애플리케이션을 지원하기 위해 노력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="3c2cf-108">**안정적** - 우수한 .NET 라이브러리는 에코시스템에서 공존하며 다양한 라이브러리를 사용하여 빌드된 애플리케이션에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="3c2cf-109">**진화하도록 설계** - .NET 라이브러리는 시간이 지남에 따라 개선되고 진화하는 동시에 기존 사용자를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="3c2cf-110">**디버깅 가능** - .NET 라이브러리는 사용자에 대해 뛰어난 디버깅 환경을 만드는 최신 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="3c2cf-111">**신뢰할 수 있음** - .NET 라이브러리는 보안 모범 사례를 사용하는 NuGet에 게시하여 개발자의 신뢰를 얻고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3c2cf-112">시작</span><span class="sxs-lookup"><span data-stu-id="3c2cf-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="3c2cf-113">권장 사항 유형</span><span class="sxs-lookup"><span data-stu-id="3c2cf-113">Types of recommendations</span></span>

<span data-ttu-id="3c2cf-114">각 문서에는 네 가지 유형의 권장 사항이 나와 있습니다. **수행**, **고려**, **회피**, **금지**입니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="3c2cf-115">각 권장 사항 유형은 수행해야 하는 필요성의 정도를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="3c2cf-116">**수행** 권장 사항은 거의 항상 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="3c2cf-117">예:</span><span class="sxs-lookup"><span data-stu-id="3c2cf-117">For example:</span></span>

<span data-ttu-id="3c2cf-118">**✔️ 수행** NuGet 패키지를 사용하여 라이브러리를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-118">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="3c2cf-119">한편으로 **고려** 권장 사항은 일반적으로 따라야 하지만 규칙에 대한 정당한 예외가 있거나 지침을 따르지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="3c2cf-120">**✔️ 고려**[SemVer 2.0.0](https://semver.org/)을 사용하여 NuGet 패키지 버전을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-120">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="3c2cf-121">**회피** 권장 사항은 일반적으로 좋지는 않지만 규칙을 깨는 것이 적합한 경우를 언급합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="3c2cf-122">**❌회피** 정확한 버전을 요구하는 NuGet 패키지 참조는 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-122">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="3c2cf-123">마지막으로, **금지**는 수행하지 않아야 하는 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="3c2cf-124">**❌** 강력한 이름 및 강력하지 않은 이름이 지정된 버전의 라이브러리를 게시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-124">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="3c2cf-125">예를 들어 `Contoso.Api` 및 `Contoso.Api.StrongNamed`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2cf-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="3c2cf-126">다음</span><span class="sxs-lookup"><span data-stu-id="3c2cf-126">Next</span></span>](get-started.md)
