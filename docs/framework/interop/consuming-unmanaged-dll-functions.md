---
title: 관리되지 않는 DLL 함수 사용
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
ms.openlocfilehash: 7ec1f129dcc19300dd5a4e7c5e627d9e0edf29a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400952"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="74522-102">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="74522-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="74522-103">플랫폼 호출은 Windows API의 함수와 같이 DLL(동적 연결 라이브러리)에서 구현된 관리되지 않는 함수를 관리 코드가 호출할 수 있도록 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="74522-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="74522-104">이 서비스는 내보낸 함수를 찾아서 호출하고 필요에 따라 상호 운용 경계를 가로질러 인수(정수, 문자열, 배열, 구조체 등)를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="74522-105">이 섹션에서는 관리되지 않는 DLL 함수 사용과 관련된 작업을 소개하고 플랫폼 호출에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-105">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="74522-106">다음 작업 이외에 일반적인 고려 사항과 추가 정보 및 예제를 제공하는 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74522-106">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="74522-107">내보낸 DLL 함수를 사용하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-107">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="74522-108">[DLL에서 함수를 식별합니다](identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="74522-108">[Identify functions in DLLs](identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="74522-109">최소한 함수 이름 및 함수가 포함된 DLL 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-109">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="74522-110">[DLL 함수가 포함된 클래스를 만듭니다](creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="74522-110">[Create a class to hold DLL functions](creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="74522-111">기존 클래스를 사용하거나, 각 관리되지 않는 함수에 대한 개별 클래스를 만들거나, 관련 관리되지 않는 함수 집합을 포함하는 클래스 하나를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74522-111">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="74522-112">[관리 코드에서 프로토타입을 만듭니다](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="74522-112">[Create prototypes in managed code](creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="74522-113">[Visual Basic] **Declare** 문을 **Function** 및 **Lib** 키워드와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-113">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="74522-114">드물지만 **DllImportAttribute**를 **Shared Function** 키워드와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74522-114">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="74522-115">이러한 경우에 대해서는 이 섹션의 뒷부분에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-115">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="74522-116">[C#] **DllImportAttribute**를 사용하여 DLL 및 함수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-116">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="74522-117">**static** 및 **extern** 한정자를 사용하여 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-117">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="74522-118">[C++] **DllImportAttribute**를 사용하여 DLL 및 함수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-118">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="74522-119">**extern “C”** 를 사용하여 래퍼 메서드 또는 함수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-119">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="74522-120">[DLL 함수를 호출합니다](calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="74522-120">[Call a DLL function](calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="74522-121">다른 관리되는 메서드에서 호출하는 것처럼 관리되는 클래스에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-121">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="74522-122">[구조체 전달](passing-structures.md) 및 [콜백 함수 구현](callback-functions.md)은 특별한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="74522-122">[Passing structures](passing-structures.md) and [implementing callback functions](callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="74522-123">플랫폼 호출에서 사용되는 .NET 기반 선언을 생성하는 방법을 보여 주는 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](marshaling-data-with-platform-invoke.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74522-123">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="74522-124">플랫폼 호출 자세히 보기</span><span class="sxs-lookup"><span data-stu-id="74522-124">A closer look at platform invoke</span></span>  
 <span data-ttu-id="74522-125">플랫폼 호출은 메타데이터에 의존하여 내보낸 함수를 찾고 런타임에 해당 인수를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-125">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="74522-126">다음 그림에서 이 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74522-126">The following illustration shows this process.</span></span>  
  
 ![플랫폼 호출을 보여주는 다이어그램.](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="74522-128">플랫폼 호출이 관리되지 않는 함수를 호출할 때 다음 작업 시퀀스를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-128">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="74522-129">함수가 포함된 DLL을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="74522-129">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="74522-130">DLL을 메모리로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-130">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="74522-131">메모리에서 함수를 찾고 인수를 스택에 넣어 필요에 따라 데이터를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-131">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="74522-132">DLL을 찾아서 로드하고 메모리에서 함수의 주소를 찾는 작업은 함수에 대한 첫 번째 호출에서만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="74522-132">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="74522-133">컨트롤을 관리되지 않는 함수에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-133">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="74522-134">플랫폼 호출은 관리되지 않는 함수에서 생성된 예외를 관리되는 호출자로 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="74522-134">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="74522-135">참조</span><span class="sxs-lookup"><span data-stu-id="74522-135">See also</span></span>

- [<span data-ttu-id="74522-136">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="74522-136">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="74522-137">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="74522-137">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="74522-138">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="74522-138">Interop Marshaling</span></span>](interop-marshaling.md)
