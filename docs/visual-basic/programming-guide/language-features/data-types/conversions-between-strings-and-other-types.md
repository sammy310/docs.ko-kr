---
title: 문자열과 다른 형식 사이의 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 1e42fca7800a76cab10fd60058e34d31ae8b8830
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907324"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="141a6-102">문자열과 다른 형식 사이의 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="141a6-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="141a6-103">숫자를 변환할 수 있습니다 `Boolean`, 또는 날짜/시간 값을 `String`입니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="141a6-104">반대 방향으로 변환할 수도 있습니다-숫자 문자열 값에서 `Boolean`, 또는 `Date` -문자열의 내용을 대상 데이터 형식의 유효한 값으로 해석 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="141a6-105">그렇지 않을 경우 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="141a6-106">어느 방향으로 이러한 모든 할당에 대 한 변환을 축소 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="141a6-107">형식 변환 키워드를 사용 해야 (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`를 `CInt`, `CLng`를 `CSByte`, `CShort`를 `CSng`, `CStr`, `CUInt`, `CULng`하십시오 `CUShort`, 및 `CType`).</span><span class="sxs-lookup"><span data-stu-id="141a6-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="141a6-108">합니다 <xref:Microsoft.VisualBasic.Strings.Format%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Val%2A> 함수 문자열 및 숫자 간의 변환에 대 한 추가 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="141a6-109">클래스 또는 구조체를 정의 하는 경우 간의 형식 변환 연산자를 정의할 수 있습니다 `String` 및 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="141a6-110">자세한 내용은 [방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="141a6-111">숫자를 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="141a6-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="141a6-112">사용할 수는 `Format` 뿐만 아니라 적절 한 숫자를 포함할 수 있는 형식된 문자열을 숫자로 변환할 작동 하지만 또한 등의 통화 기호를 기호 서식 지정 (같은 `$`), 천 단위 구분 기호 또는 *자릿수 구분 기호* (같은 `,`), 및 소수 구분 기호 (같은 `.`).</span><span class="sxs-lookup"><span data-stu-id="141a6-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="141a6-113">`Format` 자동으로에 따라 적절 한 기호를 사용 하는 **국가별 옵션** 는 Windows에 지정 된 설정을 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="141a6-114">연결 (`&`) 연산자는 다음 예제와 같이 암시적으로 숫자를 문자열로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="141a6-115">문자열을 숫자로 변환</span><span class="sxs-lookup"><span data-stu-id="141a6-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="141a6-116">사용할 수는 `Val` 함수를 명시적으로 문자열의 숫자를 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="141a6-117">`Val` 숫자, 공백, 탭, 줄 바꿈 또는 마침표 이외의 문자를 발견할 때까지 문자열을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="141a6-118">시퀀스를 "& O" 및 "& H" 숫자 체계의 기본을 변경 하 고 검색을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="141a6-119">읽기를 중단 될 때까지 `Val` 모든 적절 한 문자는 숫자 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="141a6-120">다음 문은 값을 반환 하는 예를 들어 `141.825`합니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="141a6-121">문자열을 숫자 값으로 변환 하는 Visual Basic을 사용 하 여는 **국가별 옵션** 는 Windows에 지정 된 설정을 **제어판** 1000 단위를 해석 하 구분 기호, 소수 구분 기호 및 통화 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="141a6-122">즉, 설정 중 하나에 변환이 성공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="141a6-123">예를 들어 `"$14.20"` 허용 되는 모든 프랑스어 로캘이 있지만 영어 (미국) 로캘을에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a6-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141a6-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="141a6-124">See also</span></span>

- [<span data-ttu-id="141a6-125">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="141a6-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="141a6-126">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="141a6-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="141a6-127">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="141a6-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="141a6-128">방법: Visual Basic에서 다른 형식으로 변환할 개체</span><span class="sxs-lookup"><span data-stu-id="141a6-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="141a6-129">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="141a6-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="141a6-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="141a6-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="141a6-131">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="141a6-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="141a6-132">.NET Framework 기반의 국가별 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="141a6-132">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
