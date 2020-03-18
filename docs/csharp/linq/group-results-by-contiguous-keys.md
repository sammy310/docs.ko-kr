---
title: 연속 키를 기준으로 결과 그룹화(C#의 LINQ)
description: C#의 LINQ를 사용하여 연속 키를 기준으로 결과를 그룹화하는 방법입니다.
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659906"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="b2681-103">연속 키를 기준으로 결과 그룹화</span><span class="sxs-lookup"><span data-stu-id="b2681-103">Group results by contiguous keys</span></span>

<span data-ttu-id="b2681-104">다음 예제에서는 연속 키의 하위 시퀀스를 나타내는 청크로 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="b2681-105">예를 들어 키-값 쌍의 다음 시퀀스가 제공된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>

|<span data-ttu-id="b2681-106">Key</span><span class="sxs-lookup"><span data-stu-id="b2681-106">Key</span></span>|<span data-ttu-id="b2681-107">값</span><span class="sxs-lookup"><span data-stu-id="b2681-107">Value</span></span>|
|---------|-----------|
|<span data-ttu-id="b2681-108">A</span><span class="sxs-lookup"><span data-stu-id="b2681-108">A</span></span>|<span data-ttu-id="b2681-109">We</span><span class="sxs-lookup"><span data-stu-id="b2681-109">We</span></span>|
|<span data-ttu-id="b2681-110">A</span><span class="sxs-lookup"><span data-stu-id="b2681-110">A</span></span>|<span data-ttu-id="b2681-111">think</span><span class="sxs-lookup"><span data-stu-id="b2681-111">think</span></span>|
|<span data-ttu-id="b2681-112">A</span><span class="sxs-lookup"><span data-stu-id="b2681-112">A</span></span>|<span data-ttu-id="b2681-113">that</span><span class="sxs-lookup"><span data-stu-id="b2681-113">that</span></span>|
|<span data-ttu-id="b2681-114">B</span><span class="sxs-lookup"><span data-stu-id="b2681-114">B</span></span>|<span data-ttu-id="b2681-115">Linq</span><span class="sxs-lookup"><span data-stu-id="b2681-115">Linq</span></span>|
|<span data-ttu-id="b2681-116">C</span><span class="sxs-lookup"><span data-stu-id="b2681-116">C</span></span>|<span data-ttu-id="b2681-117">is</span><span class="sxs-lookup"><span data-stu-id="b2681-117">is</span></span>|
|<span data-ttu-id="b2681-118">A</span><span class="sxs-lookup"><span data-stu-id="b2681-118">A</span></span>|<span data-ttu-id="b2681-119">really</span><span class="sxs-lookup"><span data-stu-id="b2681-119">really</span></span>|
|<span data-ttu-id="b2681-120">B</span><span class="sxs-lookup"><span data-stu-id="b2681-120">B</span></span>|<span data-ttu-id="b2681-121">cool</span><span class="sxs-lookup"><span data-stu-id="b2681-121">cool</span></span>|
|<span data-ttu-id="b2681-122">B</span><span class="sxs-lookup"><span data-stu-id="b2681-122">B</span></span>|<span data-ttu-id="b2681-123">!</span><span class="sxs-lookup"><span data-stu-id="b2681-123">!</span></span>|

<span data-ttu-id="b2681-124">다음 그룹이 이 순서로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-124">The following groups will be created in this order:</span></span>

1. <span data-ttu-id="b2681-125">We, think, that</span><span class="sxs-lookup"><span data-stu-id="b2681-125">We, think, that</span></span>

2. <span data-ttu-id="b2681-126">Linq</span><span class="sxs-lookup"><span data-stu-id="b2681-126">Linq</span></span>

3. <span data-ttu-id="b2681-127">is</span><span class="sxs-lookup"><span data-stu-id="b2681-127">is</span></span>

4. <span data-ttu-id="b2681-128">really</span><span class="sxs-lookup"><span data-stu-id="b2681-128">really</span></span>

5. <span data-ttu-id="b2681-129">cool, !</span><span class="sxs-lookup"><span data-stu-id="b2681-129">cool, !</span></span>

<span data-ttu-id="b2681-130">솔루션은 스레드로부터 안전하고 결과를 스트리밍 방식으로 반환하는 확장 메서드로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="b2681-131">즉, 솔루션은 소스 시퀀스를 거치면서 그룹을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="b2681-132">`group` 또는 `orderby` 연산자와 달리 모든 시퀀스를 다 읽기 전에 그룹을 호출자에 반환하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>

<span data-ttu-id="b2681-133">스레드로부터의 안전성을 달성하려면 소스 코드 요소에 설명된 대로 소스 시퀀스가 반복됨에 따라 각 그룹 또는 청크의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="b2681-134">소스 시퀀스에 연속 항목의 큰 시퀀스가 포함된 경우 공용 언어 런타임이 <xref:System.OutOfMemoryException>을 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="b2681-135">예제</span><span class="sxs-lookup"><span data-stu-id="b2681-135">Example</span></span>

<span data-ttu-id="b2681-136">다음 예제에서는 확장 메서드 및 이를 사용하는 클라이언트 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-136">The following example shows both the extension method and the client code that uses it:</span></span>

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

<span data-ttu-id="b2681-137">프로젝트에서 확장 메서드를 사용하려면 `MyExtensions` 정적 클래스를 신규 또는 기존 소스 코드 파일에 복사하고, 필요한 경우 해당 메서드가 있는 네임스페이스에 대한 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b2681-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2681-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2681-138">See also</span></span>

- [<span data-ttu-id="b2681-139">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="b2681-139">Language Integrated Query (LINQ)</span></span>](index.md)
