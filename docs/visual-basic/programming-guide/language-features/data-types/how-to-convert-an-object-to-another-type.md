---
title: '방법: Visual Basic에서 다른 형식으로 변환할 개체'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: d80dc542f71aaf3eec6891006d77c5d39c985abf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601000"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="cd8c3-102">방법: Visual Basic에서 다른 형식으로 변환할 개체</span><span class="sxs-lookup"><span data-stu-id="cd8c3-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="cd8c3-103">변환 하는 `Object` 같은 변환 키워드를 사용 하 여 다른 데이터 형식으로 변수 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8c3-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd8c3-104">예제</span><span class="sxs-lookup"><span data-stu-id="cd8c3-104">Example</span></span>  
 <span data-ttu-id="cd8c3-105">다음 예제는 `Object` 변수는 `Integer` 및 `String`.</span><span class="sxs-lookup"><span data-stu-id="cd8c3-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="cd8c3-106">있음을 알고 있는 경우 내용의 `Object` 변수는 특정 데이터 형식의 편이 변수의 데이터 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8c3-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="cd8c3-107">계속 사용 하는 경우는 `Object` 변수에 발생 하거나 *boxing* 하 고 *unboxing* (값 형식)에 대 한 또는 *런타임에 바인딩* (참조 형식)에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8c3-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="cd8c3-108">이러한 추가 실행 시간이 모든 작업과 하므로 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd8c3-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd8c3-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cd8c3-109">Compiling the Code</span></span>  
 <span data-ttu-id="cd8c3-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8c3-110">This example requires:</span></span>  
  
- <span data-ttu-id="cd8c3-111"><xref:System?displayProperty=nameWithType> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="cd8c3-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8c3-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="cd8c3-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="cd8c3-113">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="cd8c3-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="cd8c3-114">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="cd8c3-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="cd8c3-115">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="cd8c3-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="cd8c3-116">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="cd8c3-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="cd8c3-117">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="cd8c3-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="cd8c3-118">구조체</span><span class="sxs-lookup"><span data-stu-id="cd8c3-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="cd8c3-119">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cd8c3-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="cd8c3-120">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="cd8c3-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
