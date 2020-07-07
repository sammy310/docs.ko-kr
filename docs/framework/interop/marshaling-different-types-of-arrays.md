---
title: 여러 형식의 배열 마샬링
description: 값별 또는 참조별 정수, 값별 2차원 정수, 값별 문자열, 정수 또는 문자열을 포함하는 구조체 등 다양한 배열 형식을 마샬링합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: f1473c7917189f0b36c96b2adcf20005c5fd6b48
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621498"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="05083-103">여러 형식의 배열 마샬링</span><span class="sxs-lookup"><span data-stu-id="05083-103">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="05083-104">배열은 동일한 형식의 요소를 하나 이상 포함하는 관리 코드의 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05083-104">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="05083-105">배열은 참조 형식이지만 관리되지 않는 함수에 In 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="05083-105">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="05083-106">이 동작은 관리되는 배열이 관리되는 개체에 전달되는 방식(In/Out 매개 변수로)과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05083-106">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="05083-107">자세한 내용은 [복사 및 고정](copying-and-pinning.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05083-107">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="05083-108">다음 표에서는 배열에 대한 마샬링 옵션을 나열하고 사용법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-108">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="05083-109">배열</span><span class="sxs-lookup"><span data-stu-id="05083-109">Array</span></span>|<span data-ttu-id="05083-110">설명</span><span class="sxs-lookup"><span data-stu-id="05083-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="05083-111">값 형식 정수.</span><span class="sxs-lookup"><span data-stu-id="05083-111">Of integers by value.</span></span>|<span data-ttu-id="05083-112">정수 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-112">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="05083-113">참조 형식 정수.</span><span class="sxs-lookup"><span data-stu-id="05083-113">Of integers by reference.</span></span>|<span data-ttu-id="05083-114">정수 배열을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-114">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="05083-115">값 형식 정수(2차원).</span><span class="sxs-lookup"><span data-stu-id="05083-115">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="05083-116">정수 행렬을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-116">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="05083-117">값 형식 문자열.</span><span class="sxs-lookup"><span data-stu-id="05083-117">Of strings by value.</span></span>|<span data-ttu-id="05083-118">문자열 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-118">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="05083-119">정수를 포함하는 구조체.</span><span class="sxs-lookup"><span data-stu-id="05083-119">Of structures with integers.</span></span>|<span data-ttu-id="05083-120">정수를 포함하는 구조체 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-120">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="05083-121">문자열을 포함하는 구조체.</span><span class="sxs-lookup"><span data-stu-id="05083-121">Of structures with strings.</span></span>|<span data-ttu-id="05083-122">문자열만 포함하는 구조체 배열을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-122">Passes an array of structures that contain only strings as an In/Out parameter.</span></span> <span data-ttu-id="05083-123">배열의 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05083-123">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="05083-124">예제</span><span class="sxs-lookup"><span data-stu-id="05083-124">Example</span></span>  
 <span data-ttu-id="05083-125">이 샘플에서는 다음 형식의 배열을 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05083-125">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
- <span data-ttu-id="05083-126">값 형식 정수 배열</span><span class="sxs-lookup"><span data-stu-id="05083-126">Array of integers by value.</span></span>  
  
- <span data-ttu-id="05083-127">크기를 조정할 수 있는 참조 형식 정수 배열</span><span class="sxs-lookup"><span data-stu-id="05083-127">Array of integers by reference, which can be resized.</span></span>  
  
- <span data-ttu-id="05083-128">값 형식 정수의 다차원 배열(행렬)</span><span class="sxs-lookup"><span data-stu-id="05083-128">Multidimensional array (matrix) of integers by value.</span></span>  
  
- <span data-ttu-id="05083-129">값 형식 문자열 배열</span><span class="sxs-lookup"><span data-stu-id="05083-129">Array of strings by value.</span></span>  
  
- <span data-ttu-id="05083-130">정수를 포함하는 구조체 배열</span><span class="sxs-lookup"><span data-stu-id="05083-130">Array of structures with integers.</span></span>  
  
- <span data-ttu-id="05083-131">문자열을 포함하는 구조체 배열</span><span class="sxs-lookup"><span data-stu-id="05083-131">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="05083-132">배열이 참조에 의해 명시적으로 마샬링되지 않은 한 기본 동작은 배열을 In 매개 변수로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-132">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="05083-133"><xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 명시적으로 적용하면 이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05083-133">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="05083-134">Arrays 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-134">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="05083-135">PinvokeLib.dll에서 내보낸**TestArrayOfInts**</span><span class="sxs-lookup"><span data-stu-id="05083-135">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- <span data-ttu-id="05083-136">PinvokeLib.dll에서 내보낸**TestRefArrayOfInts**</span><span class="sxs-lookup"><span data-stu-id="05083-136">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- <span data-ttu-id="05083-137">PinvokeLib.dll에서 내보낸**TestMatrixOfInts**</span><span class="sxs-lookup"><span data-stu-id="05083-137">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- <span data-ttu-id="05083-138">PinvokeLib.dll에서 내보낸**TestArrayOfStrings**</span><span class="sxs-lookup"><span data-stu-id="05083-138">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- <span data-ttu-id="05083-139">PinvokeLib.dll에서 내보낸**TestArrayOfStructs**</span><span class="sxs-lookup"><span data-stu-id="05083-139">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- <span data-ttu-id="05083-140">PinvokeLib.dll에서 내보낸**TestArrayOfStructs2**</span><span class="sxs-lookup"><span data-stu-id="05083-140">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="05083-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) 은 앞에 나열된 함수 및 2개의 구조체 변수 **MYPOINT** 및 **MYPERSON**에 대한 구현을 포함하는 관리되지 않는 사용자 지정 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="05083-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="05083-142">구조체에는 다음과 같은 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="05083-142">The structures contain the following elements:</span></span>  
  
```cpp
typedef struct _MYPOINT  
{  
   int x;
   int y;
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;
   char* last;
} MYPERSON;  
```  
  
 <span data-ttu-id="05083-143">이 샘플에서 `MyPoint` 및 `MyPerson` 구조체에는 포함된 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05083-143">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="05083-144"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성이 설정되어 멤버가 표시되는 순서대로 순차적으로 메모리에 정렬되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-144">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="05083-145">`NativeMethods` 클래스에는 `App` 클래스가 호출하는 메서드 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="05083-145">The `NativeMethods` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="05083-146">배열을 전달하는 방법에 대한 자세한 내용은 다음 샘플의 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05083-146">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="05083-147">참조 형식인 배열은 기본적으로 In 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="05083-147">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="05083-148">호출자가 결과를 받으려면 배열을 포함하는 인수에 **InAttribute** 및 **OutAttribute** 를 명시적으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05083-148">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="05083-149">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="05083-149">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="05083-150">함수 호출</span><span class="sxs-lookup"><span data-stu-id="05083-150">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="05083-151">참조</span><span class="sxs-lookup"><span data-stu-id="05083-151">See also</span></span>

- [<span data-ttu-id="05083-152">플랫폼 호출 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="05083-152">Platform invoke data types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="05083-153">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="05083-153">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
