---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 4e0831a045da5eb5798d10aeb977981ecae20040
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819540"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="63429-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="63429-102">Value Types and Reference Types</span></span>
<span data-ttu-id="63429-103">Visual Basic의 경우 데이터 형식은 분류에 따라 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63429-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="63429-104">Visual Basic 데이터 형식 특정 형식의 변수는 자체 데이터 또는 데이터에 대 한 포인터를 저장 하는 여부에 따라 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="63429-105">자체 데이터를 저장 하는 경우는 *값 형식*데이터는 메모리에 다른 곳에서 포인터를 보유 하는 경우를 *참조 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="63429-106">값 형식</span><span class="sxs-lookup"><span data-stu-id="63429-106">Value Types</span></span>  
 <span data-ttu-id="63429-107">데이터 형식은 *값 형식* 자신의 메모리 할당 데이터 보유 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="63429-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="63429-108">값 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="63429-109">모든 숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="63429-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="63429-110">`Boolean`, `Char`및 `Date`</span><span class="sxs-lookup"><span data-stu-id="63429-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="63429-111">해당 멤버 참조 형식인 경우에 모든 구조</span><span class="sxs-lookup"><span data-stu-id="63429-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="63429-112">해당 기본 형식이 항상 이므로 열거형 `SByte`, `Short`를 `Integer`, `Long`를 `Byte`를 `UShort`, `UInteger`, 또는 `ULong`</span><span class="sxs-lookup"><span data-stu-id="63429-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="63429-113">모든 구조체가 값 형식이 참조 형식 멤버를 포함 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="63429-114">이 따라서가에 대 한 값과 같은 형식이 `Char` 고 `Integer` .net 구조체에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63429-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="63429-115">예를 들어, 예약 된 키워드를 사용 하 여 값 형식을 선언할 수 있습니다 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="63429-116">사용할 수도 있습니다는 `New` 값 형식을 초기화 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="63429-117">형식 매개 변수를 사용 하는 생성자가 하는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="63429-118">이 예로 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> 새 빌드는 생성자 `Decimal` 에서 제공 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="63429-119">참조 형식</span><span class="sxs-lookup"><span data-stu-id="63429-119">Reference Types</span></span>  
 <span data-ttu-id="63429-120">A *유형을 참조* 데이터를 보유 하는 다른 메모리 위치에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="63429-121">참조 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="63429-122">모든 배열의 해당 요소 값 형식인 경우에</span><span class="sxs-lookup"><span data-stu-id="63429-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="63429-123">클래스 형식 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="63429-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="63429-124">대리자</span><span class="sxs-lookup"><span data-stu-id="63429-124">Delegates</span></span>  
  
 <span data-ttu-id="63429-125">클래스는 *유형을 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-125">A class is a *reference type*.</span></span> <span data-ttu-id="63429-126">이러한 이유로 같은 참조 형식이 `Object` 하 고 `String` 지 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="63429-127">모든 배열은 참조 형식 인지, 해당 멤버 값 형식인 경우에 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="63429-128">모든 참조 형식을 나타내므로 기본.NET Framework 클래스를 사용 해야 합니다 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 초기화할 때 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="63429-129">다음 문은 배열을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="63429-130">형식 없는 요소</span><span class="sxs-lookup"><span data-stu-id="63429-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="63429-131">그 중 하나에서 선언 된 요소에 대 한 데이터 형식으로 지정할 수 없으므로 다음 프로그래밍 요소 형식으로 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63429-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="63429-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="63429-132">Namespaces</span></span>  
  
-   <span data-ttu-id="63429-133">모듈</span><span class="sxs-lookup"><span data-stu-id="63429-133">Modules</span></span>  
  
-   <span data-ttu-id="63429-134">이벤트</span><span class="sxs-lookup"><span data-stu-id="63429-134">Events</span></span>  
  
-   <span data-ttu-id="63429-135">속성 및 절차</span><span class="sxs-lookup"><span data-stu-id="63429-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="63429-136">변수, 상수 및 필드</span><span class="sxs-lookup"><span data-stu-id="63429-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="63429-137">개체 데이터 형식 사용</span><span class="sxs-lookup"><span data-stu-id="63429-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="63429-138">참조 형식 또는 값 형식 변수에 할당할 수 있습니다는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="63429-139">`Object` 변수 항상 데이터를 데이터 자체에 대 한 포인터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="63429-140">그러나 값 형식을 할당 하는 경우는 `Object` 변수인 것 처럼 동작 자체 데이터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="63429-141">자세한 내용은 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63429-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="63429-142">여부를 확인할 수 있습니다는 `Object` 변수 역할을 하는 참조 형식 또는 값 형식을 전달 하 여는 <xref:Microsoft.VisualBasic.Information.IsReference%2A> 에서 메서드는 <xref:Microsoft.VisualBasic.Information> 의 클래스는 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="63429-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="63429-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 반환 `True` 경우의 콘텐츠는 `Object` 변수에 참조 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="63429-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63429-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="63429-144">See also</span></span>

- [<span data-ttu-id="63429-145">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="63429-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="63429-146">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="63429-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="63429-147">Structure 문</span><span class="sxs-lookup"><span data-stu-id="63429-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="63429-148">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="63429-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="63429-149">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="63429-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="63429-150">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="63429-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
