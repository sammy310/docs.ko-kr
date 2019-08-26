---
title: 개체 형식 배열 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: fd4496e0f84953204ad8c3f40db699e911c3f477
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597355"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="259f9-102">개체 형식 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="259f9-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="259f9-103">C#의 배열은 C 및 C++와 같이 인접한 메모리의 주소 지정 가능한 영역이 아니라 실제로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="259f9-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="259f9-104"><xref:System.Array>는 모든 배열 형식의 추상 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="259f9-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="259f9-105"><xref:System.Array>에 포함된 속성 및 다른 클래스 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259f9-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="259f9-106">이러한 예로 <xref:System.Array.Length%2A> 속성을 사용하여 배열의 길이를 가져오는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259f9-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="259f9-107">다음 코드에서는 `numbers` 배열의 길이(`5`)를 `lengthOfNumbers`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="259f9-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 <span data-ttu-id="259f9-108"><xref:System.Array> 클래스는 배열의 정렬, 검색 및 복사를 위한 다른 여러 유용한 메서드와 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="259f9-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="259f9-109">예</span><span class="sxs-lookup"><span data-stu-id="259f9-109">Example</span></span>

 <span data-ttu-id="259f9-110">이 예제에서는 <xref:System.Array.Rank%2A> 속성을 사용하여 배열의 차원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="259f9-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="259f9-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="259f9-111">See also</span></span>

- [<span data-ttu-id="259f9-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="259f9-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="259f9-113">배열</span><span class="sxs-lookup"><span data-stu-id="259f9-113">Arrays</span></span>](./index.md)
- [<span data-ttu-id="259f9-114">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="259f9-114">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="259f9-115">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="259f9-115">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="259f9-116">가변 배열</span><span class="sxs-lookup"><span data-stu-id="259f9-116">Jagged Arrays</span></span>](./jagged-arrays.md)
