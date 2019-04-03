---
title: 배열 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 88002e2c099ed9503beddb190d243aadcc1087fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830203"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="b939b-102">배열 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b939b-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="b939b-103">다음 조건이 충족 되는 배열 형식 다른 배열 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="b939b-104">**동일한 차수입니다.**</span><span class="sxs-lookup"><span data-stu-id="b939b-104">**Equal Rank.**</span></span> <span data-ttu-id="b939b-105">두 배열의 차수가 동일 해야, 즉, 동일한 차원 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="b939b-106">그러나 각 차원의 길이 같이 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="b939b-107">**요소 데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="b939b-107">**Element Data Type.**</span></span> <span data-ttu-id="b939b-108">두 배열 요소의 데이터 형식에는 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="b939b-109">변환할 수 없습니다는 `Integer` 배열을 `Long` 배열 또는 심지어는 `Object` 하나 이상의 값 형식이 포함 되어 있으므로 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="b939b-110">자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b939b-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="b939b-111">**변환 가능성입니다.**</span><span class="sxs-lookup"><span data-stu-id="b939b-111">**Convertibility.**</span></span> <span data-ttu-id="b939b-112">두 배열의 요소 형식 간에 변환, 확대 또는 축소 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="b939b-113">이 요구 사항은 실패 하는 예제는 간의 변환 된 `String` 에서 파생 된 클래스의 배열 및 배열 <xref:System.Attribute?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b939b-114">이러한 두 형식 nothing 공통적으로 있고 어떤 종류의 변환 작업 없이 서로 간에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="b939b-115">다른 배열 형식 변환을 확대 되었거나 해당 요소의 변환을 확대 또는 축소 하는 여부에 따라 축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="b939b-116">자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b939b-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="b939b-117">개체 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="b939b-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="b939b-118">선언 하는 경우는 `Object` 초기화 하지 않고, 해당 요소 형식 배열이 `Object` 으로 초기화 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="b939b-119">특정 클래스의 배열에 설정 하는 경우 해당 클래스의 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="b939b-120">그러나 기본 형식과 여전히 `Object`, 및 관련된 클래스의 다른 배열에 이후에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="b939b-121">모든 클래스에서 파생 되므로 `Object`, 다른 클래스에 모든 클래스에서 배열의 요소 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="b939b-122">다음 예제에서는 형식 간의 변환이 존재 `student` 하 고 `String`에서 파생 되지만 `Object`이므로 모든 할당은 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="b939b-123">기본 형식의 배열</span><span class="sxs-lookup"><span data-stu-id="b939b-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="b939b-124">특정 클래스를 사용 하 여 배열, 원래 선언 하는 경우의 기본 요소 형식은 해당 클래스를입니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="b939b-125">이후에 설정 하면 다른 클래스의 배열에 두 클래스 간의 변환과 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="b939b-126">다음 예에서 `students` 되는 `student` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="b939b-127">변환 작업 없이 사이 존재 하므로 `String` 및 `student`, 마지막 문이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b939b-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="b939b-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="b939b-128">See also</span></span>

- [<span data-ttu-id="b939b-129">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b939b-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="b939b-130">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="b939b-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="b939b-131">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="b939b-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="b939b-132">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="b939b-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="b939b-133">방법: Visual Basic에서 다른 형식으로 변환할 개체</span><span class="sxs-lookup"><span data-stu-id="b939b-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="b939b-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b939b-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="b939b-135">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="b939b-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="b939b-136">배열</span><span class="sxs-lookup"><span data-stu-id="b939b-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
