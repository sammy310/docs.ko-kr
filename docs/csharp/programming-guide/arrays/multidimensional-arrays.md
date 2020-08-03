---
title: 다차원 배열 - C# 프로그래밍 가이드
description: C#의 배열에 둘 이상의 차원이 있을 수 있습니다. 이 예제에서는 선언을 사용하여 행 4개, 열 2개의 2차원 배열을 만듭니다.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a2f204c0866672b317569fbc620aa8af60829ffd
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475010"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="cc173-104">다차원 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="cc173-104">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="cc173-105">배열에 둘 이상의 차원이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-105">Arrays can have more than one dimension.</span></span> <span data-ttu-id="cc173-106">예를 들어 다음 선언은 행 4개, 열 2개의 2차원 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-106">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="cc173-107">다음 선언은 세 가지 차원 4, 2, 3의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-107">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="cc173-108">배열 초기화</span><span class="sxs-lookup"><span data-stu-id="cc173-108">Array Initialization</span></span>

 <span data-ttu-id="cc173-109">다음 예제와 같이 선언 시 배열을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-109">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="cc173-110">순위를 지정하지 않고 배열을 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-110">You can also initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="cc173-111">초기화하지 않고 배열 변수를 선언하도록 선택할 경우 `new` 연산자를 사용하여 변수에 배열을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-111">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="cc173-112">`new` 사용은 다음 예제에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-112">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="cc173-113">다음 예제에서는 특정 배열 요소에 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-113">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="cc173-114">마찬가지로, 다음 예제에서는 특정 배열 요소의 값을 가져와 `elementValue` 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-114">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="cc173-115">다음 코드 예제에서는 가변 배열을 제외하고 배열 요소를 기본 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="cc173-115">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="cc173-116">참조</span><span class="sxs-lookup"><span data-stu-id="cc173-116">See also</span></span>

- [<span data-ttu-id="cc173-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cc173-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cc173-118">배열</span><span class="sxs-lookup"><span data-stu-id="cc173-118">Arrays</span></span>](./index.md)
- [<span data-ttu-id="cc173-119">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="cc173-119">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="cc173-120">가변 배열</span><span class="sxs-lookup"><span data-stu-id="cc173-120">Jagged Arrays</span></span>](./jagged-arrays.md)
