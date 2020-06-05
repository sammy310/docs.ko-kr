---
title: '방법: 개체를 다른 형식으로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393963"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="3e79c-102">방법: Visual Basic에서 Object를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="3e79c-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="3e79c-103">`Object` [CType 함수와](../../../language-reference/functions/ctype-function.md)같은 변환 키워드를 사용 하 여 변수를 다른 데이터 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e79c-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e79c-104">예제</span><span class="sxs-lookup"><span data-stu-id="3e79c-104">Example</span></span>  
 <span data-ttu-id="3e79c-105">다음 예제에서는 변수를 및으로 변환 합니다 `Object` `Integer` `String` .</span><span class="sxs-lookup"><span data-stu-id="3e79c-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="3e79c-106">`Object`변수의 내용이 특정 데이터 형식이 면 변수를 해당 데이터 형식으로 변환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e79c-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="3e79c-107">변수를 계속 사용 하는 경우 `Object` *boxing* 및 *unboxing* (값 형식) 또는 *런타임 바인딩* (참조 형식)이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e79c-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="3e79c-108">이러한 작업은 모두 추가 실행 시간을 사용 하 고 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e79c-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="3e79c-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3e79c-109">Compile the code</span></span>  
 <span data-ttu-id="3e79c-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e79c-110">This example requires:</span></span>  
  
- <span data-ttu-id="3e79c-111"><xref:System?displayProperty=nameWithType> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="3e79c-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e79c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e79c-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="3e79c-113">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="3e79c-113">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="3e79c-114">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="3e79c-114">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="3e79c-115">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="3e79c-115">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="3e79c-116">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="3e79c-116">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="3e79c-117">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="3e79c-117">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="3e79c-118">구조체</span><span class="sxs-lookup"><span data-stu-id="3e79c-118">Structures</span></span>](structures.md)
- [<span data-ttu-id="3e79c-119">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3e79c-119">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="3e79c-120">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="3e79c-120">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
