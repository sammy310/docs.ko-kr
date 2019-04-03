---
title: 개체 데이터 형식 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 616110145db2796e05509094b1c023daacd68f03
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835572"
---
# <a name="object-data-type"></a><span data-ttu-id="73721-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="73721-102">Object Data Type</span></span>
<span data-ttu-id="73721-103">개체를 참조 하는 주소를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="73721-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="73721-104">참조 형식 (문자열, 배열, 클래스 또는 인터페이스)를 할당할 수 있습니다는 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="73721-105">`Object` 변수 값 형식의 데이터도 참조할 수 있습니다 (숫자 `Boolean`를 `Char`, `Date`, 구조체 또는 열거형)입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73721-106">설명</span><span class="sxs-lookup"><span data-stu-id="73721-106">Remarks</span></span>  
 <span data-ttu-id="73721-107">`Object` 데이터 형식은 응용 프로그램에서 인식 하는 모든 개체 인스턴스를 포함 하 여 모든 데이터 형식의 데이터를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73721-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="73721-108">사용 하 여 `Object` 컴파일 타임에 모르는 경우 어떤 데이터 형식 변수 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73721-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="73721-109">기본값인 `Object` 는 `Nothing` (null 참조).</span><span class="sxs-lookup"><span data-stu-id="73721-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="73721-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73721-110">Data Types</span></span>  
 <span data-ttu-id="73721-111">변수, 상수 또는 모든 데이터 형식의 식을 할당할 수는 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="73721-112">데이터 형식을 확인 하는 `Object` 참조 현재 변수를 사용할 수 있습니다 합니다 <xref:System.Type.GetTypeCode%2A> 메서드의 <xref:System.Type?displayProperty=nameWithType> 클래스.</span><span class="sxs-lookup"><span data-stu-id="73721-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="73721-113">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="73721-114">`Object` 데이터 형식은 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="73721-115">그러나 Visual Basic 처리는 `Object` 값 형식의 데이터를 참조할 때 값 형식으로 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="73721-116">스토리지</span><span class="sxs-lookup"><span data-stu-id="73721-116">Storage</span></span>  
 <span data-ttu-id="73721-117">참조 하는 데이터 형식에 관계 없이 `Object` 자체 이지만 값에 대 한 포인터 대신 변수 데이터 값이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73721-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="73721-118">항상 컴퓨터 메모리에 4 바이트를 사용 하지만이 변수의 값을 나타내는 데이터 저장소를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73721-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="73721-119">데이터를 찾는 데 포인터를 사용 하는 코드로 인해 `Object` 값 형식을 있는 변수는 형식화 된 변수 보다 명시적으로 액세스 하려면 다소 느립니다.</span><span class="sxs-lookup"><span data-stu-id="73721-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="73721-120">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="73721-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="73721-121">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="73721-121">**Interop Considerations.**</span></span> <span data-ttu-id="73721-122">예제에서는 자동화 개체나 COM 개체에 대 한.NET Framework 용으로 작성 되지 구성 요소와 상호 작용 하는 경우 염두에 포인터 형식이 다른 환경에서 Visual Basic을 사용 하 여 호환 되지 않음을 `Object` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="73721-123">**성능.**</span><span class="sxs-lookup"><span data-stu-id="73721-123">**Performance.**</span></span> <span data-ttu-id="73721-124">사용 하 여 선언 된 변수는 `Object` 형식은 모든 개체에 대 한 참조를 포함할 만큼 충분히 유연 합니다.</span><span class="sxs-lookup"><span data-stu-id="73721-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="73721-125">그러나 메서드 또는 속성에 이러한 변수를 호출 하면 항상 발생 *런타임에 바인딩* (런타임에).</span><span class="sxs-lookup"><span data-stu-id="73721-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="73721-126">강제로 *초기 바인딩* 컴파일 시간 및 성능 향상, 특정 클래스 이름 사용 하 여 변수를 선언 하거나 특정 데이터 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="73721-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="73721-127">개체 변수를 선언 하면 예를 들어 특정 클래스 형식을 사용 하려고 <xref:System.OperatingSystem>를 일반화 하는 대신 `Object` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="73721-128">와 같은 사용 가능한 가장 구체적인 클래스도 사용 해야 <xref:System.Windows.Forms.TextBox> 대신 <xref:System.Windows.Forms.Control>속성 및 메서드에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="73721-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="73721-129">일반적으로 사용할 수 있습니다 합니다 **클래스** 목록에 **개체 브라우저** 사용할 수 있는 클래스 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73721-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="73721-130">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="73721-130">**Widening.**</span></span> <span data-ttu-id="73721-131">모든 데이터 형식 및 모든 참조 형식으로 확장 된 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="73721-132">즉, 모든 형식을 변환할 수 있습니다 `Object` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="73721-133">그러나 값 형식 간에 변환 하는 경우 및 `Object`, 작업을 수행 하는 Visual Basic *boxing* 하 고 *unboxing*, 실행 속도가 느린를 활용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="73721-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="73721-134">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="73721-134">**Type Characters.**</span></span> <span data-ttu-id="73721-135">`Object` 에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73721-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="73721-136">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="73721-136">**Framework Type.**</span></span> <span data-ttu-id="73721-137">.NET Framework의 해당 형식은 <xref:System.Object?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73721-138">예제</span><span class="sxs-lookup"><span data-stu-id="73721-138">Example</span></span>  
 <span data-ttu-id="73721-139">다음 예제는 `Object` 개체 인스턴스를 가리키는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="73721-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="73721-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="73721-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="73721-141">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73721-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="73721-142">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="73721-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="73721-143">변환 요약</span><span class="sxs-lookup"><span data-stu-id="73721-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="73721-144">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="73721-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="73721-145">방법: 두 개체가 관련이 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73721-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="73721-146">방법: 두 개체가 동일한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73721-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
