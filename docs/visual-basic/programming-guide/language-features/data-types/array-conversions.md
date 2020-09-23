---
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
ms.openlocfilehash: 375c75c954f3be535272d674d9b786cad46b1a01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077191"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="ce10e-102">배열 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce10e-102">Array Conversions (Visual Basic)</span></span>

<span data-ttu-id="ce10e-103">다음 조건을 충족 하는 경우 배열 형식을 다른 배열 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="ce10e-104">**같은 순위입니다.**</span><span class="sxs-lookup"><span data-stu-id="ce10e-104">**Equal Rank.**</span></span> <span data-ttu-id="ce10e-105">두 배열의 순위는 동일 해야 합니다. 즉, 동일한 수의 차수를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="ce10e-106">그러나 각 차원의 길이는 같을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="ce10e-107">**요소 데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="ce10e-107">**Element Data Type.**</span></span> <span data-ttu-id="ce10e-108">두 배열 요소의 데이터 형식은 모두 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="ce10e-109">`Integer` `Long` 하나 이상의 값 형식이 관련 되어 있으므로 배열을 배열 또는 배열로 변환할 수 없습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="ce10e-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="ce10e-110">자세한 내용은 [값 형식 및 참조 형식](value-types-and-reference-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce10e-110">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="ce10e-111">**Convertibility.**</span><span class="sxs-lookup"><span data-stu-id="ce10e-111">**Convertibility.**</span></span> <span data-ttu-id="ce10e-112">확대 또는 축소의 변환은 두 배열의 요소 형식 간에 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="ce10e-113">이 요구 사항을 충족 하지 않는 예제는 `String` 배열과에서 파생 된 클래스의 배열 간에 시도 된 변환입니다 <xref:System.Attribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ce10e-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ce10e-114">이러한 두 형식에는 공통 된 것이 없으며 두 형식 사이에는 어떠한 종류의 변환만 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="ce10e-115">한 배열 형식을 다른 형식으로 변환 하는 것은 각 요소의 변환이 확대 또는 축소 인지에 따라 확대 또는 축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="ce10e-116">자세한 내용은 [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce10e-116">For more information, see [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="ce10e-117">개체 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="ce10e-117">Conversion to an Object Array</span></span>  

 <span data-ttu-id="ce10e-118">`Object`배열을 초기화 하지 않고 선언 하는 경우 요소 형식은 초기화 되지 않은 `Object` 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="ce10e-119">특정 클래스의 배열로 설정 하면 해당 클래스의 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="ce10e-120">그러나 해당 기본 형식은 여전히 이며, `Object` 이후에는 관련 없는 클래스의 다른 배열로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="ce10e-121">모든 클래스는에서 파생 되므로 모든 `Object` 클래스에서 다른 클래스로 배열의 요소 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="ce10e-122">다음 예에서는 형식과 사이에는 변환이 `student` `String` 없지만 둘 다에서 파생 `Object` 되므로 모든 할당이 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
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
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="ce10e-123">배열의 내부 형식</span><span class="sxs-lookup"><span data-stu-id="ce10e-123">Underlying Type of an Array</span></span>  

 <span data-ttu-id="ce10e-124">원래 특정 클래스를 사용 하 여 배열을 선언 하는 경우 해당 기본 요소 형식은 해당 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="ce10e-125">이후에 다른 클래스의 배열로 설정 하는 경우 두 클래스 사이에 변환이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="ce10e-126">다음 예제에서 `students` 는 `student` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="ce10e-127">와 사이에 변환이 없기 때문에 `String` `student` 마지막 문이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce10e-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce10e-128">참조</span><span class="sxs-lookup"><span data-stu-id="ce10e-128">See also</span></span>

- [<span data-ttu-id="ce10e-129">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ce10e-129">Data Types</span></span>](index.md)
- [<span data-ttu-id="ce10e-130">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="ce10e-130">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="ce10e-131">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="ce10e-131">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="ce10e-132">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="ce10e-132">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="ce10e-133">방법: Visual Basic에서 Object를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="ce10e-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="ce10e-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ce10e-134">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="ce10e-135">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="ce10e-135">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ce10e-136">배열</span><span class="sxs-lookup"><span data-stu-id="ce10e-136">Arrays</span></span>](../arrays/index.md)
