---
title: 개체 형식 배열 - C# 프로그래밍 가이드
description: C#의 배열은 추상 기본 형식 배열의 개체입니다. Length 속성과 같이 배열의 속성 및 다른 클래스 멤버를 사용할 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 984def3ef74b07d7099fae6cae6d6f8ce7e03e12
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474724"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="4ca1f-104">개체 형식 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4ca1f-104">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="4ca1f-105">C#의 배열은 C 및 C++와 같이 인접한 메모리의 주소 지정 가능한 영역이 아니라 실제로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca1f-105">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="4ca1f-106"><xref:System.Array>는 모든 배열 형식의 추상 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca1f-106"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="4ca1f-107"><xref:System.Array>에 포함된 속성 및 다른 클래스 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca1f-107">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="4ca1f-108">이러한 예로 <xref:System.Array.Length%2A> 속성을 사용하여 배열의 길이를 가져오는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca1f-108">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="4ca1f-109">다음 코드에서는 `numbers` 배열의 길이(`5`)를 `lengthOfNumbers`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca1f-109">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="4ca1f-110"><xref:System.Array> 클래스는 배열의 정렬, 검색 및 복사를 위한 다른 여러 유용한 메서드와 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca1f-110">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>

## <a name="example"></a><span data-ttu-id="4ca1f-111">예제</span><span class="sxs-lookup"><span data-stu-id="4ca1f-111">Example</span></span>

<span data-ttu-id="4ca1f-112">이 예제에서는 <xref:System.Array.Rank%2A> 속성을 사용하여 배열의 차원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca1f-112">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="4ca1f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ca1f-113">See also</span></span>

- [<span data-ttu-id="4ca1f-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4ca1f-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4ca1f-115">배열</span><span class="sxs-lookup"><span data-stu-id="4ca1f-115">Arrays</span></span>](./index.md)
- [<span data-ttu-id="4ca1f-116">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="4ca1f-116">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="4ca1f-117">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="4ca1f-117">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="4ca1f-118">가변 배열</span><span class="sxs-lookup"><span data-stu-id="4ca1f-118">Jagged Arrays</span></span>](./jagged-arrays.md)
