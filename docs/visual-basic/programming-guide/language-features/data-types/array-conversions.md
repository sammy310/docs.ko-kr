---
description: '자세한 정보: 배열 변환 (Visual Basic)'
title: 배열 규칙
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
ms.openlocfilehash: 1600042e1d41cbc2bd52468544db0e806e776d9c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466408"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="8c95b-103">배열 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c95b-103">Array Conversions (Visual Basic)</span></span>

<span data-ttu-id="8c95b-104">다음 조건을 충족 하는 경우 배열 형식을 다른 배열 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-104">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="8c95b-105">**같은 순위입니다.**</span><span class="sxs-lookup"><span data-stu-id="8c95b-105">**Equal Rank.**</span></span> <span data-ttu-id="8c95b-106">두 배열의 순위는 동일 해야 합니다. 즉, 동일한 수의 차수를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-106">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="8c95b-107">그러나 각 차원의 길이는 같을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-107">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="8c95b-108">**요소 데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="8c95b-108">**Element Data Type.**</span></span> <span data-ttu-id="8c95b-109">두 배열 요소의 데이터 형식은 모두 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-109">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="8c95b-110">`Integer` `Long` 하나 이상의 값 형식이 관련 되어 있으므로 배열을 배열 또는 배열로 변환할 수 없습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="8c95b-110">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="8c95b-111">자세한 내용은 [값 형식 및 참조 형식](value-types-and-reference-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8c95b-111">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="8c95b-112">**Convertibility.**</span><span class="sxs-lookup"><span data-stu-id="8c95b-112">**Convertibility.**</span></span> <span data-ttu-id="8c95b-113">확대 또는 축소의 변환은 두 배열의 요소 형식 간에 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-113">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="8c95b-114">이 요구 사항을 충족 하지 않는 예제는 `String` 배열과에서 파생 된 클래스의 배열 간에 시도 된 변환입니다 <xref:System.Attribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8c95b-114">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8c95b-115">이러한 두 형식에는 공통 된 것이 없으며 두 형식 사이에는 어떠한 종류의 변환만 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-115">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="8c95b-116">한 배열 형식을 다른 형식으로 변환 하는 것은 각 요소의 변환이 확대 또는 축소 인지에 따라 확대 또는 축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-116">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="8c95b-117">자세한 내용은 [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c95b-117">For more information, see [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="8c95b-118">개체 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="8c95b-118">Conversion to an Object Array</span></span>  

 <span data-ttu-id="8c95b-119">`Object`배열을 초기화 하지 않고 선언 하는 경우 요소 형식은 초기화 되지 않은 `Object` 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-119">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="8c95b-120">특정 클래스의 배열로 설정 하면 해당 클래스의 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-120">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="8c95b-121">그러나 해당 기본 형식은 여전히 이며, `Object` 이후에는 관련 없는 클래스의 다른 배열로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-121">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="8c95b-122">모든 클래스는에서 파생 되므로 모든 `Object` 클래스에서 다른 클래스로 배열의 요소 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-122">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="8c95b-123">다음 예에서는 형식과 사이에는 변환이 `student` `String` 없지만 둘 다에서 파생 `Object` 되므로 모든 할당이 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-123">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="8c95b-124">배열의 내부 형식</span><span class="sxs-lookup"><span data-stu-id="8c95b-124">Underlying Type of an Array</span></span>  

 <span data-ttu-id="8c95b-125">원래 특정 클래스를 사용 하 여 배열을 선언 하는 경우 해당 기본 요소 형식은 해당 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-125">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="8c95b-126">이후에 다른 클래스의 배열로 설정 하는 경우 두 클래스 사이에 변환이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-126">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="8c95b-127">다음 예제에서 `students` 는 `student` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-127">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="8c95b-128">와 사이에 변환이 없기 때문에 `String` `student` 마지막 문이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c95b-128">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c95b-129">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8c95b-129">See also</span></span>

- [<span data-ttu-id="8c95b-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c95b-130">Data Types</span></span>](index.md)
- [<span data-ttu-id="8c95b-131">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="8c95b-131">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="8c95b-132">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="8c95b-132">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="8c95b-133">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="8c95b-133">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="8c95b-134">방법: Visual Basic에서 Object를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="8c95b-134">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="8c95b-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c95b-135">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="8c95b-136">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="8c95b-136">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8c95b-137">배열</span><span class="sxs-lookup"><span data-stu-id="8c95b-137">Arrays</span></span>](../arrays/index.md)
