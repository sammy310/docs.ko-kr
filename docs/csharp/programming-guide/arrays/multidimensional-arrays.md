---
title: 다차원 배열 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: eb49f4386b6106328f1613b5ec70794ac26fc9b7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715046"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="fe5fb-102">다차원 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="fe5fb-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="fe5fb-103">배열에 둘 이상의 차원이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="fe5fb-104">예를 들어 다음 선언은 행 4개, 열 2개의 2차원 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="fe5fb-105">다음 선언은 세 가지 차원 4, 2, 3의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="fe5fb-106">배열 초기화</span><span class="sxs-lookup"><span data-stu-id="fe5fb-106">Array Initialization</span></span>

 <span data-ttu-id="fe5fb-107">다음 예제와 같이 선언 시 배열을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="fe5fb-108">차수를 지정하지 않고 배열을 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="fe5fb-109">초기화하지 않고 배열 변수를 선언하도록 선택할 경우 `new` 연산자를 사용하여 변수에 배열을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="fe5fb-110">`new` 사용은 다음 예제에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="fe5fb-111">다음 예제에서는 특정 배열 요소에 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="fe5fb-112">마찬가지로, 다음 예제에서는 특정 배열 요소의 값을 가져와 `elementValue` 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="fe5fb-113">다음 코드 예제에서는 가변 배열을 제외하고 배열 요소를 기본 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="fe5fb-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="fe5fb-114">참조</span><span class="sxs-lookup"><span data-stu-id="fe5fb-114">See also</span></span>

- [<span data-ttu-id="fe5fb-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fe5fb-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fe5fb-116">배열</span><span class="sxs-lookup"><span data-stu-id="fe5fb-116">Arrays</span></span>](./index.md)
- [<span data-ttu-id="fe5fb-117">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="fe5fb-117">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="fe5fb-118">가변 배열</span><span class="sxs-lookup"><span data-stu-id="fe5fb-118">Jagged Arrays</span></span>](./jagged-arrays.md)
