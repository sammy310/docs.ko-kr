---
title: 클래스, 구조체 및 공용 구조체 마샬링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
ms.openlocfilehash: 708ed6a232950cb69796f105f6f198749ed53a24
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200017"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="eca3d-102">클래스, 구조체 및 공용 구조체 마샬링</span><span class="sxs-lookup"><span data-stu-id="eca3d-102">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="eca3d-103">.NET Framework에서는 클래스와 구조체가 서로 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="eca3d-104">둘 다 필드, 속성 및 이벤트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="eca3d-105">또한 정적 및 비정적 메서드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="eca3d-106">한 가지 주목할 만한 차이점은 구조체는 값 형식이고 클래스는 참조 형식이라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-106">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="eca3d-107">다음 표에서는 클래스, 구조체 및 공용 구조체에 대한 마샬링 옵션을 나열하고 용도를 설명하며 해당하는 플랫폼 호출 샘플에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="eca3d-108">형식</span><span class="sxs-lookup"><span data-stu-id="eca3d-108">Type</span></span>|<span data-ttu-id="eca3d-109">설명</span><span class="sxs-lookup"><span data-stu-id="eca3d-109">Description</span></span>|<span data-ttu-id="eca3d-110">예제</span><span class="sxs-lookup"><span data-stu-id="eca3d-110">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="eca3d-111">값 방식 클래스.</span><span class="sxs-lookup"><span data-stu-id="eca3d-111">Class by value.</span></span>|<span data-ttu-id="eca3d-112">관리되는 사례와 같이 정수 멤버를 In/Out 매개 변수로 사용하여 클래스를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="eca3d-113">SysTime 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-113">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="eca3d-114">값 방식 구조체.</span><span class="sxs-lookup"><span data-stu-id="eca3d-114">Structure by value.</span></span>|<span data-ttu-id="eca3d-115">구조체를 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-115">Passes structures as In parameters.</span></span>|[<span data-ttu-id="eca3d-116">구조체 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-116">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="eca3d-117">참조 방식 구조체.</span><span class="sxs-lookup"><span data-stu-id="eca3d-117">Structure by reference.</span></span>|<span data-ttu-id="eca3d-118">구조체를 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="eca3d-119">[OSInfo 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eca3d-119">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="eca3d-120">중첩 구조체를 포함하는 구조체(결합).</span><span class="sxs-lookup"><span data-stu-id="eca3d-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="eca3d-121">관리되지 않는 함수에서 중첩 구조체를 포함하는 구조체를 나타내는 클래스를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="eca3d-122">관리되는 프로토타입에서는 구조체가 하나의 큰 구조체로 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-122">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="eca3d-123">FindFile 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-123">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="eca3d-124">다른 구조체에 대한 포인터를 포함하는 구조체.</span><span class="sxs-lookup"><span data-stu-id="eca3d-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="eca3d-125">두 번째 구조체에 대한 포인터를 멤버로 포함하는 구조체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="eca3d-126">구조체 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-126">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="eca3d-127">값 형식 정수를 포함하는 구조체 배열.</span><span class="sxs-lookup"><span data-stu-id="eca3d-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="eca3d-128">정수만 포함하는 구조체 배열을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="eca3d-129">배열의 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-129">Members of the array can be changed.</span></span>|[<span data-ttu-id="eca3d-130">배열 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-130">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="eca3d-131">참조 형식 정수 및 문자열을 포함하는 구조체 배열.</span><span class="sxs-lookup"><span data-stu-id="eca3d-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="eca3d-132">정수 및 문자열을 포함하는 구조체 배열을 Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="eca3d-133">호출된 함수가 배열에 대한 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-133">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="eca3d-134">OutArrayOfStructs 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-134">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="eca3d-135">값 형식을 포함하는 공용 구조체.</span><span class="sxs-lookup"><span data-stu-id="eca3d-135">Unions with value types.</span></span>|<span data-ttu-id="eca3d-136">값 형식(정수 및 double)을 포함하는 공용 구조체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-136">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="eca3d-137">Unions 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-137">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="eca3d-138">혼합된 형식을 포함하는 공용 구조체.</span><span class="sxs-lookup"><span data-stu-id="eca3d-138">Unions with mixed types.</span></span>|<span data-ttu-id="eca3d-139">혼합된 형식(정수 및 문자열)을 포함하는 공용 구조체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-139">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="eca3d-140">Unions 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-140">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="eca3d-141">플랫폼별 레이아웃을 사용하는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-141">Struct with platform-specific layout.</span></span>|<span data-ttu-id="eca3d-142">네이티브 압축 정의를 사용하여 형식을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-142">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="eca3d-143">플랫폼 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-143">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="eca3d-144">구조체의 null 값.</span><span class="sxs-lookup"><span data-stu-id="eca3d-144">Null values in structure.</span></span>|<span data-ttu-id="eca3d-145">값 형식에 대한 참조 대신 null 참조(Visual Basic에서는 **Nothing**)를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-145">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="eca3d-146">[HandleRef 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="eca3d-146">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="eca3d-147">Structures 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-147">Structures sample</span></span>

<span data-ttu-id="eca3d-148">이 샘플에서는 두 번째 구조체를 가리키는 구조체, 포함된 구조체가 있는 구조체 및 포함된 배열이 있는 구조체를 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-148">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="eca3d-149">Structs 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-149">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="eca3d-150">PinvokeLib.dll에서 내보낸 **TestStructInStruct**.</span><span class="sxs-lookup"><span data-stu-id="eca3d-150">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="eca3d-151">PinvokeLib.dll에서 내보낸 **TestStructInStruct3**.</span><span class="sxs-lookup"><span data-stu-id="eca3d-151">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="eca3d-152">PinvokeLib.dll에서 내보낸 **TestArrayInStruct**.</span><span class="sxs-lookup"><span data-stu-id="eca3d-152">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="eca3d-153">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll)은 앞에 나열된 함수와 네 가지 구조에 대한 구현을 포함하는 관리되지 않는 사용자 지정 라이브러리입니다. **MYPERSON**, **MYPERSON2**, **MYPERSON3** 및 **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="eca3d-153">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="eca3d-154">이러한 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-154">These structures contain the following elements:</span></span>

```cpp
typedef struct _MYPERSON
{
   char* first;
   char* last;
} MYPERSON, *LP_MYPERSON;

typedef struct _MYPERSON2
{
   MYPERSON* person;
   int age;
} MYPERSON2, *LP_MYPERSON2;

typedef struct _MYPERSON3
{
   MYPERSON person;
   int age;
} MYPERSON3;

typedef struct _MYARRAYSTRUCT
{
   bool flag;
   int vals[ 3 ];
} MYARRAYSTRUCT;
```

<span data-ttu-id="eca3d-155">관리되는 `MyPerson`, `MyPerson2`, `MyPerson3` 및 `MyArrayStruct` 구조체는 다음과 같은 특성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-155">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="eca3d-156">`MyPerson`에는 문자열 멤버만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-156">`MyPerson` contains only string members.</span></span> <span data-ttu-id="eca3d-157">[CharSet](specifying-a-character-set.md) 필드는 관리되지 않는 함수에 전달되는 경우 문자열을 ANSI 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-157">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="eca3d-158">`MyPerson2`에는 `MyPerson` 구조체에 대한 **IntPtr**이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-158">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="eca3d-159">.NET Framework 애플리케이션은 코드가 **안전하지 않은** 것으로 표시된 경우가 아니면 포인터를 사용하지 않으므로 **IntPtr** 형식이 관리되지 않는 구조체에 대한 원래 포인터를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-159">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="eca3d-160">`MyPerson3`에는 `MyPerson`이 포함된 구조체로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-160">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="eca3d-161">포함된 구조체의 요소를 기본 구조에 직접 배치하여 다른 구조체 내에 포함된 구조체를 결합하거나 이 샘플과 같이 포함된 구조체로 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-161">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="eca3d-162">`MyArrayStruct`에는 정수 배열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-162">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="eca3d-163"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 배열의 요소 수를 나타내는 데 사용되는 **ByValArray**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-163">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="eca3d-164">이 샘플의 모든 구조체에는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성이 적용되어 멤버가 표시되는 순서대로 순차적으로 메모리에 정렬되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-164">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="eca3d-165">`NativeMethods` 클래스에는 `App` 클래스가 호출하는 `TestStructInStruct`, `TestStructInStruct3` 및 `TestArrayInStruct` 메서드에 대한 관리되는 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-165">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="eca3d-166">각 프로토타입은 다음과 같이 단일 매개 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-166">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="eca3d-167">`TestStructInStruct`는 `MyPerson2` 형식에 대한 참조를 해당 매개 변수로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-167">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="eca3d-168">`TestStructInStruct3`은 `MyPerson3` 형식을 해당 매개 변수로 선언하고 매개 변수를 값으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-168">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="eca3d-169">`TestArrayInStruct`는 `MyArrayStruct` 형식에 대한 참조를 해당 매개 변수로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-169">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="eca3d-170">메서드에 대한 인수로서의 구조체는 매개 변수에 **ref**(Visual Basic에서는 **ByRef**) 키워드가 포함되지 않은 경우 값으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-170">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="eca3d-171">예를 들어 `TestStructInStruct` 메서드는 `MyPerson2` 형식의 개체에 대한 참조(주소 값)를 비관리 코드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-171">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="eca3d-172">`MyPerson2`가 가리키는 구조체를 조작하기 위해 샘플에서는 지정된 크기의 버퍼를 만들고 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> 및 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 메서드를 결합하여 해당 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-172">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="eca3d-173">그런 다음 관리되는 구조체의 콘텐츠를 관리되지 않는 버퍼로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-173">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="eca3d-174">끝으로, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> 메서드를 사용하여 관리되지 않는 버퍼의 데이터를 관리되는 개체로 마샬링하고 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> 메서드를 사용하여 관리되지 않는 메모리 블록을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-174">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="eca3d-175">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="eca3d-175">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="eca3d-176">함수 호출</span><span class="sxs-lookup"><span data-stu-id="eca3d-176">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="eca3d-177">FindFile 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-177">FindFile sample</span></span>

<span data-ttu-id="eca3d-178">이 샘플에서는 포함된 두 번째 구조체를 포함하는 구조체를 관리되지 않는 함수에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-178">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="eca3d-179">또한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 구조체 내에서 고정 길이 배열을 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-179">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="eca3d-180">이 샘플에서는 포함된 구조체 요소가 부모 구조체에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-180">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="eca3d-181">결합되지 않는 포함된 구조체의 샘플은 [Structures 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca3d-181">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="eca3d-182">FindFile 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-182">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="eca3d-183">Kernel32.dll에서 내보낸 **FindFirstFile**.</span><span class="sxs-lookup"><span data-stu-id="eca3d-183">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="eca3d-184">함수에 전달된 원래 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-184">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _WIN32_FIND_DATA
{
  DWORD    dwFileAttributes;
  FILETIME ftCreationTime;
  FILETIME ftLastAccessTime;
  FILETIME ftLastWriteTime;
  DWORD    nFileSizeHigh;
  DWORD    nFileSizeLow;
  DWORD    dwReserved0;
  DWORD    dwReserved1;
  TCHAR    cFileName[ MAX_PATH ];
  TCHAR    cAlternateFileName[ 14 ];
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;
```

<span data-ttu-id="eca3d-185">이 샘플에서 `FindData` 클래스에는 원래 구조체 및 포함된 구조체의 각 요소에 해당하는 데이터 멤버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-185">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="eca3d-186">두 개의 원래 문자 버퍼 대신 이 클래스가 문자열을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-186">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="eca3d-187">**MarshalAsAttribute**는 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형을 관리되지 않는 구조체 내에 표시되는 인라인 고정 길이 문자 배열을 식별하는 데 사용되는 **ByValTStr**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-187">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="eca3d-188">`NativeMethods` 클래스에는 `FindData` 클래스를 매개 변수로 전달하는 `FindFirstFile` 메서드의 관리되는 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-188">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="eca3d-189">참조 형식인 클래스는 기본적으로 In 매개 변수로 전달되므로 <xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 통해 매개 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-189">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="eca3d-190">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="eca3d-190">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="eca3d-191">함수 호출</span><span class="sxs-lookup"><span data-stu-id="eca3d-191">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="eca3d-192">Unions 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-192">Unions sample</span></span>

<span data-ttu-id="eca3d-193">이 샘플에서는 값 형식만 포함하는 구조체 및 값 형식과 문자열을 매개 변수로 포함하는 구조체를 공용 구조체가 필요한 관리되지 않는 함수에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-193">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="eca3d-194">공용 구조체는 둘 이상의 변수가 공유할 수 있는 메모리 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-194">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="eca3d-195">Unions 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-195">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="eca3d-196">PinvokeLib.dll에서 내보낸 **TestUnion**.</span><span class="sxs-lookup"><span data-stu-id="eca3d-196">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="eca3d-197">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll)은 앞에 나열된 함수와 두 공용 구조체, **MYUNION** and **MYUNION2**에 대한 구현을 포함하는 관리되지 않는 사용자 지정 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-197">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="eca3d-198">공용 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-198">The unions contain the following elements:</span></span>

```cpp
union MYUNION
{
    int number;
    double d;
}

union MYUNION2
{
    int i;
    char str[128];
};
```

<span data-ttu-id="eca3d-199">관리 코드에서는 공용 구조체가 구조체로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-199">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="eca3d-200">`MyUnion` 구조체에는 두 개의 값 형식(정수 및 double)이 해당 멤버로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-200">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="eca3d-201"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성은 각 데이터 멤버의 정확한 위치를 제어하기 위해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-201">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="eca3d-202"><xref:System.Runtime.InteropServices.FieldOffsetAttribute> 특성은 공용 구조체의 관리되지 않는 표현 내에서 필드의 실제 위치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-202">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="eca3d-203">두 멤버는 오프셋 값이 같으므로 동일한 메모리 부분을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-203">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="eca3d-204">`MyUnion2_1` 및 `MyUnion2_2`에는 각각 값 형식(정수)과 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-204">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="eca3d-205">관리 코드에서는 값 형식과 참조 형식이 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-205">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="eca3d-206">이 샘플에서는 메서드 오버로드를 통해 호출자가 동일한 관리되지 않는 함수를 호출할 때 두 형식을 모두 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-206">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="eca3d-207">`MyUnion2_1`의 레이아웃은 명시적이며 정확한 오프셋 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-207">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="eca3d-208">반면, 명시적 레이아웃은 참조 형식에 사용할 수 없으므로 `MyUnion2_2`에는 순차적 레이아웃이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-208">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="eca3d-209"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형을 공용 구조체의 관리되지 않는 표현 내에 표시되는 인라인 고정 길이 문자 배열을 식별하는 데 사용되는 **ByValTStr**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-209">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="eca3d-210">`NativeMethods` 클래스에는 `TestUnion` 및 `TestUnion2` 메서드에 대한 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-210">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="eca3d-211">`TestUnion2`는 `MyUnion2_1` 또는 `MyUnion2_2`를 매개 변수로 선언하기 위해 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-211">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="eca3d-212">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="eca3d-212">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="eca3d-213">함수 호출</span><span class="sxs-lookup"><span data-stu-id="eca3d-213">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="eca3d-214">플랫폼 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-214">Platform sample</span></span>

<span data-ttu-id="eca3d-215">일부 시나리오에서는 `struct` 및 `union` 레이아웃이 대상 플랫폼에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-215">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="eca3d-216">예를 들어 COM 시나리오에서 정의된 경우 [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) 형식을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-216">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

```c++
#include <pshpack8.h> /* Defines the packing of the struct */
typedef struct _STRRET
    {
    UINT uType;
    /* [switch_is][switch_type] */ union
        {
        /* [case()][string] */ LPWSTR pOleStr;
        /* [case()] */ UINT uOffset;
        /* [case()] */ char cStr[ 260 ];
        }  DUMMYUNIONNAME;
    }  STRRET;
#include <poppack.h>
```

<span data-ttu-id="eca3d-217">위의 `struct`는 형식의 메모리 레이아웃에 영향을 주는 Windows 헤더를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-217">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="eca3d-218">관리형 환경에서 정의된 경우 네이티브 코드와 제대로 상호 운용하려면 해당 레이아웃 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-218">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="eca3d-219">32비트 프로세스에서 이 형식의 올바른 관리형 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-219">The correct managed definition of this type in a 32-bit process is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 264)]
public struct STRRET_32
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(4)]
    public IntPtr pOleStr;

    [FieldOffset(4)]
    public uint uOffset;

    [FieldOffset(4)]
    public IntPtr cStr;
}
```

<span data-ttu-id="eca3d-220">64비트 프로세스에서 크기 및 필드 오프셋은 다릅니다. </span><span class="sxs-lookup"><span data-stu-id="eca3d-220">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="eca3d-221">올바른 레이아웃은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-221">The correct layout is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 272)]
public struct STRRET_64
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(8)]
    public IntPtr pOleStr;

    [FieldOffset(8)]
    public uint uOffset;

    [FieldOffset(8)]
    public IntPtr cStr;
}
```

<span data-ttu-id="eca3d-222">Interop 시나리오에서 네이티브 레이아웃을 적절히 고려하지 못하면 임의 충돌이나 더 심한 경우 잘못된 계산이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-222">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="eca3d-223">기본적으로 .NET 어셈블리는 32비트 및 64비트 버전의 .NET 런타임에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-223">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="eca3d-224">앱은 런타임에 사용할 이전 정의를 결정할 때까지 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-224">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="eca3d-225">다음 코드 조각에서는 런타임에 32비트와 64비트 정의 중에서 선택하는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-225">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

```CSharp
if (IntPtr.Size == 8)
{
    // Use the STRRET_64 definition
}
else
{
    Debug.Assert(IntPtr.Size == 4);
    // Use the STRRET_32 definition
}
```

## <a name="systime-sample"></a><span data-ttu-id="eca3d-226">SysTime 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-226">SysTime sample</span></span>

<span data-ttu-id="eca3d-227">이 샘플에서는 구조체에 대한 포인터가 필요한 관리되지 않는 함수에 클래스에 대한 포인터를 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-227">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="eca3d-228">SysTime 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-228">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="eca3d-229">Kernel32.dll에서 내보낸 **GetSystemTime**.</span><span class="sxs-lookup"><span data-stu-id="eca3d-229">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="eca3d-230">함수에 전달된 원래 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-230">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="eca3d-231">이 샘플에서 `SystemTime` 클래스에는 클래스 멤버로 표현된 원래 구조체의 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-231">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="eca3d-232"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성이 설정되어 멤버가 표시되는 순서대로 순차적으로 메모리에 정렬되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-232">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="eca3d-233">`NativeMethods` 클래스에는 기본적으로 `SystemTime` 클래스를 In/Out 매개 변수로 전달하는 `GetSystemTime` 메서드의 관리되는 프로토타입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-233">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="eca3d-234">참조 형식인 클래스는 기본적으로 In 매개 변수로 전달되므로 <xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 통해 매개 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-234">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="eca3d-235">호출자가 결과를 받으려면 이러한 [방향 특성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))을 명시적으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-235">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="eca3d-236">`App` 클래스는 `SystemTime` 클래스의 새 인스턴스를 만들고 해당 데이터 필드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-236">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="eca3d-237">코드 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-237">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="eca3d-238">OutArrayOfStructs 샘플</span><span class="sxs-lookup"><span data-stu-id="eca3d-238">OutArrayOfStructs sample</span></span>

<span data-ttu-id="eca3d-239">이 샘플에서는 정수 및 문자열을 Out 매개 변수로 포함하는 구조체의 배열을 관리되지 않는 함수에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-239">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="eca3d-240"><xref:System.Runtime.InteropServices.Marshal> 클래스 및 안전하지 않은 코드를 사용하여 네이티브 함수를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-240">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="eca3d-241">이 샘플에서는 [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll)에서 정의된 래퍼 함수 및 플랫폼 호출을 사용합니다(소스 파일에도 제공됨).</span><span class="sxs-lookup"><span data-stu-id="eca3d-241">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="eca3d-242">`TestOutArrayOfStructs` 함수 및 `MYSTRSTRUCT2` 구조체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-242">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="eca3d-243">이 구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-243">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="eca3d-244">`MyStruct` 클래스에는 ANSI 문자의 문자열 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-244">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="eca3d-245"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 필드는 ANSI 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-245">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="eca3d-246">`MyUnsafeStruct`는 문자열 대신 <xref:System.IntPtr> 형식을 포함하는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-246">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="eca3d-247">`NativeMethods` 클래스에는 오버로드된 `TestOutArrayOfStructs` 프로토타입 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-247">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="eca3d-248">메서드가 포인터를 매개 변수로 선언하는 경우 클래스에 `unsafe` 키워드를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-248">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="eca3d-249">Visual Basic은 안전하지 않은 코드를 사용할 수 없으므로 오버로드된 메서드, 안전하지 않은 한정자 및 `MyUnsafeStruct` 구조체는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-249">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="eca3d-250">`App` 클래스는 배열을 전달하는 데 필요한 모든 작업을 수행하는 `UsingMarshaling` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-250">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="eca3d-251">배열에 `out`(Visual Basic에서는 `ByRef`) 키워드가 표시되어 데이터가 호출 수신자에서 호출자로 전달됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-251">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="eca3d-252">이 구현에서는 다음과 같은 <xref:System.Runtime.InteropServices.Marshal> 클래스 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-252">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="eca3d-253"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> - 관리되지 않는 버퍼의 데이터를 관리되는 개체로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-253"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="eca3d-254"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> - 구조체의 문자열에 예약된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-254"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="eca3d-255"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> - 배열에 예약된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-255"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="eca3d-256">앞서 설명한 것처럼, C#에서는 안전하지 않은 코드를 허용하고 Visual Basic에서는 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-256">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="eca3d-257">C# 샘플에서 `UsingUnsafePointer`는 <xref:System.Runtime.InteropServices.Marshal> 클래스 대신 포인터를 사용하여 `MyUnsafeStruct` 구조체가 포함된 배열을 다시 전달하는 대체 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="eca3d-257">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="eca3d-258">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="eca3d-258">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="eca3d-259">함수 호출</span><span class="sxs-lookup"><span data-stu-id="eca3d-259">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="eca3d-260">참조</span><span class="sxs-lookup"><span data-stu-id="eca3d-260">See also</span></span>

- [<span data-ttu-id="eca3d-261">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="eca3d-261">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="eca3d-262">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="eca3d-262">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="eca3d-263">여러 형식의 배열 마샬링</span><span class="sxs-lookup"><span data-stu-id="eca3d-263">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)
