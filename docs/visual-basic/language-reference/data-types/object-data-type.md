---
description: '자세히 알아보기: Object 데이터 형식'
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
ms.openlocfilehash: b1f169e4e590335a0879f5ecd9b68507a3fa2ccb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792156"
---
# <a name="object-data-type"></a><span data-ttu-id="4fd9a-103">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="4fd9a-103">Object Data Type</span></span>

<span data-ttu-id="4fd9a-104">개체를 참조 하는 주소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-104">Holds addresses that refer to objects.</span></span> <span data-ttu-id="4fd9a-105">변수에 모든 참조 형식 (문자열, 배열, 클래스 또는 인터페이스)을 할당할 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="4fd9a-105">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="4fd9a-106">`Object`변수는 모든 값 형식 (숫자,,,, `Boolean` `Char` `Date` 구조체 또는 열거형)의 데이터를 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-106">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="4fd9a-107">설명</span><span class="sxs-lookup"><span data-stu-id="4fd9a-107">Remarks</span></span>

<span data-ttu-id="4fd9a-108">`Object`데이터 형식은 응용 프로그램에서 인식 하는 모든 개체 인스턴스를 포함 하 여 모든 데이터 형식의 데이터를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-108">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="4fd9a-109">`Object`컴파일 시간에 변수가 가리키는 데이터 형식을 알 수 없는 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-109">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="4fd9a-110">의 기본값은 `Object` `Nothing` (null 참조)입니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-110">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="4fd9a-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4fd9a-111">Data Types</span></span>

<span data-ttu-id="4fd9a-112">모든 데이터 형식의 변수, 상수 또는 식을 변수에 할당할 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="4fd9a-112">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="4fd9a-113">변수가 현재 참조 하는 데이터 형식을 확인 하려면 `Object` <xref:System.Type.GetTypeCode%2A> 클래스의 메서드를 사용할 수 있습니다 <xref:System.Type?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4fd9a-113">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4fd9a-114">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-114">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="4fd9a-115">`Object`데이터 형식이 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-115">The `Object` data type is a reference type.</span></span> <span data-ttu-id="4fd9a-116">그러나 Visual Basic는 `Object` 값 형식의 데이터를 참조할 때 변수를 값 형식으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-116">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="4fd9a-117">스토리지</span><span class="sxs-lookup"><span data-stu-id="4fd9a-117">Storage</span></span>

<span data-ttu-id="4fd9a-118">참조 하는 데이터 형식에 관계 없이 `Object` 변수는 데이터 값 자체를 포함 하지 않고 값에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-118">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="4fd9a-119">컴퓨터 메모리에서 항상 4 바이트를 사용 하지만 변수의 값을 나타내는 데이터의 저장소는 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-119">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="4fd9a-120">포인터를 사용 하 여 데이터를 찾는 코드로 인해 `Object` 값 형식을 포함 하는 변수는 명시적으로 형식화 된 변수에 액세스 하는 속도가 약간 느립니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-120">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="4fd9a-121">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="4fd9a-121">Programming Tips</span></span>

- <span data-ttu-id="4fd9a-122">**Interop 고려 사항.**</span><span class="sxs-lookup"><span data-stu-id="4fd9a-122">**Interop Considerations.**</span></span> <span data-ttu-id="4fd9a-123">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우 다른 환경의 포인터 형식은 Visual Basic 형식과 호환 되지 않는다는 점에 유의 하세요 `Object` .</span><span class="sxs-lookup"><span data-stu-id="4fd9a-123">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="4fd9a-124">**성능.**</span><span class="sxs-lookup"><span data-stu-id="4fd9a-124">**Performance.**</span></span> <span data-ttu-id="4fd9a-125">형식을 사용 하 여 선언 하는 변수는 `Object` 개체에 대 한 참조를 포함할 수 있을 만큼 유연 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-125">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="4fd9a-126">그러나 이러한 변수에 대 한 메서드나 속성을 호출 하면 런타임에 *바인딩이* 항상 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-126">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="4fd9a-127">컴파일 시간에 *초기 바인딩을* 적용 하 고 성능을 향상 시키려면 특정 클래스 이름을 사용 하 여 변수를 선언 하거나 특정 데이터 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-127">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="4fd9a-128">개체 변수를 선언 하는 경우 <xref:System.OperatingSystem> 일반화 된 형식 대신 특정 클래스 형식 (예:)을 사용 하십시오 `Object` .</span><span class="sxs-lookup"><span data-stu-id="4fd9a-128">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="4fd9a-129">또한 <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Control> 속성 및 메서드에 액세스할 수 있도록 대신 사용 가능한 가장 구체적인 클래스 (예:)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-129">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="4fd9a-130">일반적으로 **개체 브라우저** 의 **클래스** 목록을 사용 하 여 사용 가능한 클래스 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-130">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="4fd9a-131">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="4fd9a-131">**Widening.**</span></span> <span data-ttu-id="4fd9a-132">모든 데이터 형식과 모든 참조 형식은 데이터 형식으로 확장 `Object` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-132">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="4fd9a-133">즉, `Object` 오류가 발생 하지 않고 모든 형식을로 변환할 수 있습니다 <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4fd9a-133">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="4fd9a-134">그러나 값 형식과 Visual Basic 사이를 변환 하 `Object` 는 경우 실행 속도가 느려질 수 있도록 *boxing* 및 *unboxing* 이라는 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-134">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="4fd9a-135">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4fd9a-135">**Type Characters.**</span></span> <span data-ttu-id="4fd9a-136">`Object` 에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-136">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="4fd9a-137">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="4fd9a-137">**Framework Type.**</span></span> <span data-ttu-id="4fd9a-138">.NET Framework에서 해당 하는 형식은 <xref:System.Object?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-138">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="4fd9a-139">예제</span><span class="sxs-lookup"><span data-stu-id="4fd9a-139">Example</span></span>

<span data-ttu-id="4fd9a-140">다음 예제에서는 `Object` 개체 인스턴스를 가리키는 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4fd9a-140">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="4fd9a-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fd9a-141">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="4fd9a-142">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4fd9a-142">Data Types</span></span>](index.md)
- [<span data-ttu-id="4fd9a-143">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="4fd9a-143">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="4fd9a-144">변환 요약</span><span class="sxs-lookup"><span data-stu-id="4fd9a-144">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="4fd9a-145">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="4fd9a-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="4fd9a-146">방법: 두 개체가 관련이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4fd9a-146">How to: Determine Whether Two Objects Are Related</span></span>](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="4fd9a-147">방법: 두 개체가 동일한지 확인</span><span class="sxs-lookup"><span data-stu-id="4fd9a-147">How to: Determine Whether Two Objects Are Identical</span></span>](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
