---
title: Object Data Type
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
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343960"
---
# <a name="object-data-type"></a><span data-ttu-id="792dd-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="792dd-102">Object Data Type</span></span>

<span data-ttu-id="792dd-103">개체를 참조 하는 주소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="792dd-104">참조 형식 (문자열, 배열, 클래스 또는 인터페이스)을 `Object` 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="792dd-105">`Object` 변수는 모든 값 형식 (숫자, `Boolean`, `Char`, `Date`, 구조체 또는 열거형)의 데이터를 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="792dd-106">설명</span><span class="sxs-lookup"><span data-stu-id="792dd-106">Remarks</span></span>

<span data-ttu-id="792dd-107">`Object` 데이터 형식은 응용 프로그램에서 인식 하는 모든 개체 인스턴스를 포함 하 여 모든 데이터 형식의 데이터를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="792dd-108">컴파일 시간에 변수가 가리키는 데이터 형식을 알 수 없는 경우 `Object`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="792dd-109">`Object`의 기본값은 `Nothing` (null 참조)입니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="792dd-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="792dd-110">Data Types</span></span>

<span data-ttu-id="792dd-111">모든 데이터 형식의 변수, 상수 또는 식을 `Object` 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="792dd-112">`Object` 변수가 현재 참조 하는 데이터 형식을 확인 하려면 <xref:System.Type?displayProperty=nameWithType> 클래스의 <xref:System.Type.GetTypeCode%2A> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="792dd-113">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="792dd-114">`Object` 데이터 형식은 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="792dd-115">그러나 Visual Basic는 값 형식의 데이터를 참조할 때 `Object` 변수를 값 형식으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="792dd-116">스토리지</span><span class="sxs-lookup"><span data-stu-id="792dd-116">Storage</span></span>

<span data-ttu-id="792dd-117">참조 하는 데이터 형식에 관계 없이 `Object` 변수는 데이터 값 자체를 포함 하지 않고 값에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="792dd-118">컴퓨터 메모리에서 항상 4 바이트를 사용 하지만 변수의 값을 나타내는 데이터의 저장소는 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="792dd-119">포인터를 사용 하 여 데이터를 찾는 코드로 인해 값 형식을 보유 하는 `Object` 변수는 명시적으로 형식화 된 변수에 액세스 하는 속도가 약간 느립니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="792dd-120">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="792dd-120">Programming Tips</span></span>

- <span data-ttu-id="792dd-121">**Interop 고려 사항**</span><span class="sxs-lookup"><span data-stu-id="792dd-121">**Interop Considerations.**</span></span> <span data-ttu-id="792dd-122">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우 다른 환경의 포인터 형식은 Visual Basic `Object` 형식과 호환 되지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="792dd-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="792dd-123">**성능.**</span><span class="sxs-lookup"><span data-stu-id="792dd-123">**Performance.**</span></span> <span data-ttu-id="792dd-124">`Object` 형식으로 선언 하는 변수는 개체에 대 한 참조를 포함할 수 있을 만큼 유연 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="792dd-125">그러나 이러한 변수에 대 한 메서드나 속성을 호출 하면 런타임에 *바인딩이* 항상 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="792dd-126">컴파일 시간에 *초기 바인딩을* 적용 하 고 성능을 향상 시키려면 특정 클래스 이름을 사용 하 여 변수를 선언 하거나 특정 데이터 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="792dd-127">개체 변수를 선언 하는 경우 일반화 된 `Object` 형식 대신 특정 클래스 형식 (예: <xref:System.OperatingSystem>)을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="792dd-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="792dd-128">또한 <xref:System.Windows.Forms.Control>대신 <xref:System.Windows.Forms.TextBox>와 같이 사용 가능한 가장 구체적인 클래스를 사용 하 여 해당 속성 및 메서드에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="792dd-129">일반적으로 **개체 브라우저** 의 **클래스** 목록을 사용 하 여 사용 가능한 클래스 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="792dd-130">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="792dd-130">**Widening.**</span></span> <span data-ttu-id="792dd-131">모든 데이터 형식과 모든 참조 형식은 `Object` 데이터 형식으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="792dd-132">즉, <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 모든 형식을 `Object`로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="792dd-133">그러나 값 형식과 `Object`간에 변환 하는 경우 Visual Basic *boxing* 및 *unboxing*이라는 작업을 수행 하 여 실행 속도를 느리게 합니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="792dd-134">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="792dd-134">**Type Characters.**</span></span> <span data-ttu-id="792dd-135">`Object`에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="792dd-136">**프레임 워크 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="792dd-136">**Framework Type.**</span></span> <span data-ttu-id="792dd-137">.NET Framework에서 해당 하는 형식은 <xref:System.Object?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="792dd-138">예제</span><span class="sxs-lookup"><span data-stu-id="792dd-138">Example</span></span>

<span data-ttu-id="792dd-139">다음 예제에서는 개체 인스턴스를 가리키는 `Object` 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="792dd-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="792dd-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="792dd-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="792dd-141">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="792dd-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="792dd-142">CString</span><span class="sxs-lookup"><span data-stu-id="792dd-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="792dd-143">변환 요약</span><span class="sxs-lookup"><span data-stu-id="792dd-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="792dd-144">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="792dd-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="792dd-145">방법: 두 개체가 관련이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="792dd-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="792dd-146">방법: 두 개체가 동일한지 확인</span><span class="sxs-lookup"><span data-stu-id="792dd-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
