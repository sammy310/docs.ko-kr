---
title: 배열 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 3c50c68c2a39aa04cff2dd43b5dfde709aec290f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349073"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="54fb0-102">배열 문제 해결(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54fb0-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="54fb0-103">이 페이지에서는 배열로 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="54fb0-104">컴파일 오류 배열 선언 및 초기화</span><span class="sxs-lookup"><span data-stu-id="54fb0-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="54fb0-105">배열의 선언, 생성 및 초기화에 대 한 규칙 있다면 오해에서 컴파일 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="54fb0-106">오류의 가장 일반적인 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="54fb0-107">배열 변수 선언에서 차원 길이를 지정한 후 [새 Operator](../../../../visual-basic/language-reference/operators/new-operator.md) 절을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="54fb0-108">다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="54fb0-109">가변 배열의 최상위 배열 보다 많은 차원 길이를 지정 하는 경우</span><span class="sxs-lookup"><span data-stu-id="54fb0-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="54fb0-110">다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="54fb0-111">요소 값을 지정할 때 `New` 키워드를 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="54fb0-112">다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="54fb0-113">중괄호 없이 `New` 절 제공 (`{}`)</span><span class="sxs-lookup"><span data-stu-id="54fb0-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="54fb0-114">다음 코드 줄에서는이 형식의 잘못 된 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="54fb0-115">범위를 벗어난 배열 액세스</span><span class="sxs-lookup"><span data-stu-id="54fb0-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="54fb0-116">배열을 초기화 하는 프로세스는 상한을 할당 하 고 각 차원에는 하한값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="54fb0-117">배열의 요소에 대 한 모든 액세스는 모든 차원에 대해 유효한 인덱스 또는 첨자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="54fb0-118">인덱스의 하 한이 낮거나 상한 보다 작으면 <xref:System.IndexOutOfRangeException> 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="54fb0-119">컴파일러는 이러한 오류를 검색할 수 없으므로 런타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="54fb0-120">범위 결정</span><span class="sxs-lookup"><span data-stu-id="54fb0-120">Determining Bounds</span></span>  
 <span data-ttu-id="54fb0-121">다른 구성 요소에서 코드에 배열을 전달 하는 경우 (예: 프로시저 인수) 해당 배열의 크기나 차원의 길이를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="54fb0-122">모든 요소에 액세스 하기 전에 항상 배열의 모든 차원에 대 한 상한을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="54fb0-123">Visual Basic `New` 절 이외의 방법으로 배열을 만든 경우 하한값은 0이 아닐 수 있으며, 그 하한값을 확인 하는 것이 가장 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="54fb0-124">차원 지정</span><span class="sxs-lookup"><span data-stu-id="54fb0-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="54fb0-125">다차원 배열의 범위를 결정할 때는 차원을 지정 하는 방법을 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="54fb0-126"><xref:System.Array.GetLowerBound%2A> 및 <xref:System.Array.GetUpperBound%2A> 메서드의 `dimension` 매개 변수는 0부터 사용 되지만 Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> 및 <xref:Microsoft.VisualBasic.Information.UBound%2A> 함수의 `Rank` 매개 변수는 1부터 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54fb0-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fb0-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54fb0-127">See also</span></span>

- [<span data-ttu-id="54fb0-128">배열</span><span class="sxs-lookup"><span data-stu-id="54fb0-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="54fb0-129">방법: Visual Basic에서 배열 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="54fb0-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
