---
title: 식 트리 요약
description: 식 트리를 사용하여 코드를 데이터로 해석하고 해당 코드를 기반으로 하는 새 기능을 빌드하는 동적 프로그램을 만드는 방법을 요약합니다.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: 43715c94b70f1cd7f758cde91ae7c8d1b2f70f9f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036750"
---
# <a name="expression-trees-summary"></a><span data-ttu-id="f623f-103">식 트리 요약</span><span class="sxs-lookup"><span data-stu-id="f623f-103">Expression Trees Summary</span></span>

[<span data-ttu-id="f623f-104">이전 -- 식 변환</span><span class="sxs-lookup"><span data-stu-id="f623f-104">Previous -- Translating Expressions</span></span>](expression-trees-translating.md)

<span data-ttu-id="f623f-105">이 시리즈에서는 *식 트리*를 사용하여 코드를 데이터로 해석하고 해당 코드에 기반한 새 기능을 구축하는 동적 프로그램을 만드는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-105">In this series, you've seen how you can use *expression trees* to create dynamic programs that interpret code as data and build new functionality based on that code.</span></span>

<span data-ttu-id="f623f-106">식 트리를 검사하여 알고리즘의 의도를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-106">You can examine expression trees to understand the intent of an algorithm.</span></span> <span data-ttu-id="f623f-107">해당 코드 검사 이상을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-107">You can not only examine that code.</span></span> <span data-ttu-id="f623f-108">원래 코드의 수정된 버전을 나타내는 새로운 식 트리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-108">You can build new expression trees that represent modified versions of the original code.</span></span>

<span data-ttu-id="f623f-109">또한 식 트리를 사용하여 알고리즘을 확인하고 해당 알고리즘을 다른 언어나 환경으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-109">You can also use expression trees to look at an algorithm, and translate that algorithm into another language or environment.</span></span> 

## <a name="limitations"></a><span data-ttu-id="f623f-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="f623f-110">Limitations</span></span>

<span data-ttu-id="f623f-111">식 트리로 잘 변환되지 않는 최신 C# 언어 요소가 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-111">There are some newer C# language elements that don't translate well into expression trees.</span></span> <span data-ttu-id="f623f-112">식 트리에는 `await` 식이나 `async` 람다 식이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-112">Expression trees cannot contain `await` expressions, or `async` lambda expressions.</span></span> <span data-ttu-id="f623f-113">C# 6 릴리스에서 추가된 많은 기능이 식 트리에 작성된 대로 정확하게 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-113">Many of the features added in the C# 6 release don't appear exactly as written in expression trees.</span></span> <span data-ttu-id="f623f-114">대신 최신 기능은 해당되는 이전 구문으로 식 트리에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-114">Instead, newer features will be exposed in expressions trees in the equivalent, earlier syntax.</span></span> <span data-ttu-id="f623f-115">생각만큼 큰 제한 사항이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-115">This may not be as much of a limitation as you might think.</span></span> <span data-ttu-id="f623f-116">실제로는 새로운 언어 기능이 도입되어도 식 트리를 해석하는 코드가 동일하게 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-116">In fact, it means that your code that interprets expression trees will likely still work the same when new language features are introduced.</span></span>

<span data-ttu-id="f623f-117">이러한 제한 사항에도 불구하고 식 트리를 사용하면 데이터 구조로 표시되는 코드를 해석하고 수정하는 동적 알고리즘을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-117">Even with these limitations, expression trees do enable you to create dynamic algorithms that rely on interpreting and modifying code that is represented as a data structure.</span></span> <span data-ttu-id="f623f-118">식 트리는 강력한 도구이며 기능을 수행하기 위해 Entity Framework와 같은 풍부한 라이브러리를 사용하는 .NET 에코시스템의 기능 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="f623f-118">It's a powerful tool, and it's one of the features of the .NET ecosystem that enables rich libraries such as Entity Framework to accomplish what they do.</span></span>
