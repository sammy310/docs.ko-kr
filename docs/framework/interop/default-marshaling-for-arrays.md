---
title: 배열에 대한 기본 마샬링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: f0094ac572834b2cf0d74fb53c94877da55669e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181459"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="e0c78-102">배열에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="e0c78-102">Default Marshaling for Arrays</span></span>
<span data-ttu-id="e0c78-103">전체적으로 관리 코드로 구성된 애플리케이션에서는 공용 언어 런타임이 배열 형식을 In/Out 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-103">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="e0c78-104">반면 interop 마샬러는 기본적으로 배열을 In 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-104">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="e0c78-105">[고정 최적화](copying-and-pinning.md)를 통해 blittable 배열은 같은 아파트의 개체와 상호 작용할 때 In/Out 매개 변수로 사용되는 것으로 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-105">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="e0c78-106">그러나 나중에 컴퓨터 간 프록시를 생성하는 데 사용되는 형식 라이브러리에 코드를 내보내고 해당 라이브러리를 사용하여 아파트 간에 호출을 마샬링할 경우 호출은 실제 In 매개 변수 동작으로 되돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-106">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="e0c78-107">배열은 본질적으로 복잡하고 관리되는 배열과 관리되지 않는 배열을 구별하면 다른 비 blittable 형식보다 더 많은 정보를 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-107">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span>  
  
## <a name="managed-arrays"></a><span data-ttu-id="e0c78-108">관리되는 배열</span><span class="sxs-lookup"><span data-stu-id="e0c78-108">Managed Arrays</span></span>  
 <span data-ttu-id="e0c78-109">관리되는 배열 형식은 달라질 수 있지만 <xref:System.Array?displayProperty=nameWithType> 클래스는 모든 배열 형식의 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-109">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="e0c78-110">**System.Array** 클래스에는 배열의 순위, 길이 및 하한/상한을 결정하기 위한 속성과 배열을 액세스, 정렬, 검색, 복사, 생성하기 위한 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-110">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="e0c78-111">이러한 배열 형식의 경우 동적이고 기본 클래스 라이브러리에서 정의된 해당 정적 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-111">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="e0c78-112">각 요소 형식 및 순위의 조합을 개별 배열 형식으로 생각하면 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-112">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="e0c78-113">따라서 정수의 1차원 배열은 double 형식의 1차원 배열과 형식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-113">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="e0c78-114">마찬가지로 정수의 2차원 배열은 정수의 1차원 배열과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-114">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="e0c78-115">형식을 비교할 경우 배열의 경계를 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-115">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="e0c78-116">다음 표와 같이 관리되는 배열의 인스턴스에는 특수 요소 형식, 순위 및 하한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-116">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="e0c78-117">관리되는 배열 형식</span><span class="sxs-lookup"><span data-stu-id="e0c78-117">Managed array type</span></span>|<span data-ttu-id="e0c78-118">요소 형식</span><span class="sxs-lookup"><span data-stu-id="e0c78-118">Element type</span></span>|<span data-ttu-id="e0c78-119">Rank</span><span class="sxs-lookup"><span data-stu-id="e0c78-119">Rank</span></span>|<span data-ttu-id="e0c78-120">하한</span><span class="sxs-lookup"><span data-stu-id="e0c78-120">Lower bound</span></span>|<span data-ttu-id="e0c78-121">시그니처 표기법</span><span class="sxs-lookup"><span data-stu-id="e0c78-121">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="e0c78-122">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="e0c78-122">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="e0c78-123">형식으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-123">Specified by type.</span></span>|<span data-ttu-id="e0c78-124">순위로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-124">Specified by rank.</span></span>|<span data-ttu-id="e0c78-125">필요한 경우 경계로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-125">Optionally specified by bounds.</span></span>|<span data-ttu-id="e0c78-126">*유형* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="e0c78-126">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="e0c78-127">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="e0c78-127">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="e0c78-128">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="e0c78-128">Unknown</span></span>|<span data-ttu-id="e0c78-129">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="e0c78-129">Unknown</span></span>|<span data-ttu-id="e0c78-130">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="e0c78-130">Unknown</span></span>|<span data-ttu-id="e0c78-131">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="e0c78-131">**System.Array**</span></span>|  
|<span data-ttu-id="e0c78-132">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="e0c78-132">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="e0c78-133">형식으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-133">Specified by type.</span></span>|<span data-ttu-id="e0c78-134">1</span><span class="sxs-lookup"><span data-stu-id="e0c78-134">1</span></span>|<span data-ttu-id="e0c78-135">0</span><span class="sxs-lookup"><span data-stu-id="e0c78-135">0</span></span>|<span data-ttu-id="e0c78-136">*유형* **[** *n]* **]**</span><span class="sxs-lookup"><span data-stu-id="e0c78-136">*type* **[** *n* **]**</span></span>|  
  
## <a name="unmanaged-arrays"></a><span data-ttu-id="e0c78-137">관리되지 않는 배열</span><span class="sxs-lookup"><span data-stu-id="e0c78-137">Unmanaged Arrays</span></span>  
 <span data-ttu-id="e0c78-138">관리되지 않는 배열은 고정 또는 가변 길이가 포함된 COM 스타일 안전 배열 또는 C 스타일 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-138">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="e0c78-139">안전 배열은 연결된 배열 데이터의 형식, 순위 및 경계를 제공하는 자체 설명 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-139">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="e0c78-140">C 스타일 배열은 고정 하한이 0인 1차원 형식 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-140">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="e0c78-141">마샬링 서비스는 두 가지 배열 형식에 대한 지원을 모두 제한했습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-141">The marshaling service has limited support for both types of arrays.</span></span>  
  
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="e0c78-142">.NET 코드에 배열 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="e0c78-142">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="e0c78-143">C 스타일 배열 및 안전 배열은 둘 다 비관리 코드에서 안전 배열 또는 C 스타일 배열로 .NET 코드에 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-143">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="e0c78-144">다음 표에서는 관리되지 않는 형식 값과 가져온 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-144">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="e0c78-145">관리되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="e0c78-145">Unmanaged type</span></span>|<span data-ttu-id="e0c78-146">가져온 형식</span><span class="sxs-lookup"><span data-stu-id="e0c78-146">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="e0c78-147">**세이프어레이(타입)** *Type* **)**</span><span class="sxs-lookup"><span data-stu-id="e0c78-147">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="e0c78-148">**ELEMENT_TYPE_SZARRAY** **\<** *변환된 유형\*\*\*>*\*</span><span class="sxs-lookup"><span data-stu-id="e0c78-148">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="e0c78-149">순위 = 1, 하한 = 0.</span><span class="sxs-lookup"><span data-stu-id="e0c78-149">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="e0c78-150">관리되는 시그니처에서 제공된 경우에만 크기가 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-150">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="e0c78-151">순위 = 1 또는 하한 = 0이 아닌 안전 배열은 **SZARRAY**로 마샬링될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-151">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="e0c78-152">*유형*  **[]**</span><span class="sxs-lookup"><span data-stu-id="e0c78-152">*Type*  **[]**</span></span>|<span data-ttu-id="e0c78-153">**ELEMENT_TYPE_SZARRAY** **\<** *변환된 유형\*\*\*>*\*</span><span class="sxs-lookup"><span data-stu-id="e0c78-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="e0c78-154">순위 = 1, 하한 = 0.</span><span class="sxs-lookup"><span data-stu-id="e0c78-154">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="e0c78-155">관리되는 시그니처에서 제공된 경우에만 크기가 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-155">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="e0c78-156">안전 배열</span><span class="sxs-lookup"><span data-stu-id="e0c78-156">Safe Arrays</span></span>  
 <span data-ttu-id="e0c78-157">안전 배열을 형식 라이브러리에서 .NET 어셈블리로 가져온 경우 배열은 알려진 형식(예: **int**)의 1차원 배열로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-157">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="e0c78-158">매개 변수에 적용되는 같은 형식 변환 규칙이 배열 요소에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-158">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="e0c78-159">예를 들어 **BSTR** 형식의 안전 배열은 문자열의 관리되는 배열이 되고 변형의 안전 배열은 개체의 관리되는 배열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-159">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="e0c78-160">**SAFEARRAY** 요소 형식은 형식 라이브러리에서 캡처되고 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형의 **SAFEARRAY** 값에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-160">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="e0c78-161">형식 라이브러리에서 안전 배열의 순위와 범위를 확인할 수 없으므로 순위는 1로, 하한은 0으로 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-161">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="e0c78-162">[형식 라이브러리 가져오기(Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md)에서 생성하는 관리되는 시그니처에 순위와 범위를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-162">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="e0c78-163">런타임에 메서드에 전달되는 순위가 다른 경우 <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-163">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="e0c78-164">런타임에 전달되는 배열 형식이 다른 경우 <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-164">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="e0c78-165">다음 예제에서는 관리 및 비관리 코드의 안전 배열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-165">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="e0c78-166">**관리되지 않는 서명**</span><span class="sxs-lookup"><span data-stu-id="e0c78-166">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="e0c78-167">**관리되는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="e0c78-167">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]
   ref String[] ar);  
```  
  
 <span data-ttu-id="e0c78-168">Tlbimp.exe에서 생성된 메서드 시그니처가 **ELEMENT_TYPE_SZARRAY** 대신 **ELEMENT_TYPE_ARRAY**의 요소 형식을 나타내도록 수정될 경우 다차원 또는 0이 아닌 경계 안전 배열은 관리 코드로 마샬링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-168">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="e0c78-169">또는 Tlbimp.exe에서 **/sysarray** 스위치를 사용하여 모든 배열을 <xref:System.Array?displayProperty=nameWithType> 개체로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-169">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="e0c78-170">전달되는 배열이 다차원으로 알려진 경우에는 Tlbimp.exe에서 생성된 MSIL(Microsoft Intermediate Language) 코드를 편집하고 다시 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-170">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="e0c78-171">MSIL 코드를 수정하는 방법에 대한 자세한 내용은 [런타임 호출 가능 래퍼 사용자 지정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0c78-171">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="e0c78-172">C 스타일 배열</span><span class="sxs-lookup"><span data-stu-id="e0c78-172">C-Style Arrays</span></span>  
 <span data-ttu-id="e0c78-173">C 스타일 배열을 형식 라이브러리에서 .NET 어셈블리로 가져온 경우 배열은 **ELEMENT_TYPE_SZARRAY**로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-173">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="e0c78-174">배열 요소 형식은 형식 라이브러리에서 결정되고 가져오는 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-174">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="e0c78-175">매개 변수에 적용되는 같은 변환 규칙이 배열 요소에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-175">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="e0c78-176">예를 들어 **LPStr** 형식 배열은 **String** 형식 배열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-176">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="e0c78-177">Tlbimp.exe는 배열 형식을 캡처하고 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 매개 변수에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-177">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="e0c78-178">배열 순위는 1과 같은 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-178">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="e0c78-179">순위가 1보다 크면 배열은 열 중심 순서에서 1차원 배열로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-179">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="e0c78-180">하한은 항상 0과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-180">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="e0c78-181">형식 라이브러리에는 고정 또는 가변 길이의 배열이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-181">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="e0c78-182">형식 라이브러리에는 가변 길이 배열을 마샬링하는 데 필요한 정보가 없으므로 Tlbimp.exe는 형식 라이브러리에서 고정 길이 배열만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-182">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="e0c78-183">고정 길이 배열에서 크기는 형식 라이브러리에서 가져오고 매개 변수에 적용되는 **MarshalAsAttribute**에서 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-183">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="e0c78-184">다음 예제와 같이 가변 길이 배열이 포함된 형식 라이브러리를 수동으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-184">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="e0c78-185">**관리되지 않는 서명**</span><span class="sxs-lookup"><span data-stu-id="e0c78-185">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="e0c78-186">**관리되는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="e0c78-186">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 <span data-ttu-id="e0c78-187">IDL(Interface Definition Language) 소스의 배열에 **size_is** 또는 **length_is** 특성을 적용하여 클라이언트에 크기를 전달할 수 있지만 MIDL(Microsoft 인터페이스 정의 언어) 컴파일러는 해당 정보를 형식 라이브러리에 전파하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-187">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="e0c78-188">크기를 모르면 interop 마샬링 서비스가 배열 요소를 마샬링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-188">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="e0c78-189">따라서 가변 길이 배열은 참조 인수로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-189">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="e0c78-190">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-190">For example:</span></span>  
  
 <span data-ttu-id="e0c78-191">**관리되지 않는 서명**</span><span class="sxs-lookup"><span data-stu-id="e0c78-191">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="e0c78-192">**관리되는 시그니처**</span><span class="sxs-lookup"><span data-stu-id="e0c78-192">**Managed signature**</span></span>  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);
void New2(ref double ar);
void New3(ref String ar);
```  
  
 <span data-ttu-id="e0c78-193">Tlbimp.exe에서 생성된 MSIL(Microsoft Intermediate Language) 코드를 편집하고 다시 컴파일하여 마샬러에 배열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-193">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="e0c78-194">MSIL 코드를 수정하는 방법에 대한 자세한 내용은 [런타임 호출 가능 래퍼 사용자 지정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0c78-194">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span> <span data-ttu-id="e0c78-195">배열의 요소 수를 지정하려면 다음 방법 중 하나로 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 형식을 관리되는 메서드 정의의 배열 매개 변수에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-195">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
- <span data-ttu-id="e0c78-196">배열의 요소 수가 포함된 또 다른 매개 변수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-196">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="e0c78-197">매개 변수는 위치로 식별되고 첫 번째 매개 변수는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-197">The parameters are identified by position, starting with the first parameter as number 0.</span></span>
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
- <span data-ttu-id="e0c78-198">배열 크기를 상수로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-198">Define the size of the array as a constant.</span></span> <span data-ttu-id="e0c78-199">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-199">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="e0c78-200">비관리 코드에서 관리 코드로 배열을 마샬링할 경우 마샬러는 매개 변수와 연결된 **MarshalAsAttribute**를 확인하여 배열 크기를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-200">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="e0c78-201">배열 크기를 지정하지 않으면 하나의 요소만 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-201">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0c78-202">**MarshalAsAttribute**는 관리 배열을 비관리 코드에 마샬링하는 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-202">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="e0c78-203">해당 방향의 배열 크기는 검사에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-203">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="e0c78-204">관리되는 배열의 하위 집합을 마샬링할 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-204">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="e0c78-205">interop 마샬러는 **CoTaskMemAlloc** 및 **CoTaskMemFree** 메서드를 사용하여 메모리를 할당 및 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-205">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="e0c78-206">비관리 코드에서 수행되는 메모리 할당에는 이러한 메서드도 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-206">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
## <a name="passing-arrays-to-com"></a><span data-ttu-id="e0c78-207">COM에 배열 전달</span><span class="sxs-lookup"><span data-stu-id="e0c78-207">Passing Arrays to COM</span></span>  
 <span data-ttu-id="e0c78-208">모든 관리되는 배열 형식은 관리 코드에서 비관리 코드로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-208">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="e0c78-209">다음 표와 같이 관리되는 형식과 이 형식에 적용되는 특성에 따라 배열에는 안전 배열 또는 C 스타일 배열로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-209">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="e0c78-210">관리되는 배열 형식</span><span class="sxs-lookup"><span data-stu-id="e0c78-210">Managed array type</span></span>|<span data-ttu-id="e0c78-211">내보내기 형식</span><span class="sxs-lookup"><span data-stu-id="e0c78-211">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="e0c78-212">**ELEMENT_TYPE_SZARRAY** **\<** *타입\*\*\*>*\*</span><span class="sxs-lookup"><span data-stu-id="e0c78-212">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="e0c78-213"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="e0c78-213"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="e0c78-214">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="e0c78-214">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="e0c78-215">형식은 시그니처로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-215">Type is provided in the signature.</span></span> <span data-ttu-id="e0c78-216">순위는 항상 1이고 하한은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-216">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="e0c78-217">크기는 항상 런타임에 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-217">Size is always known at run time.</span></span>|  
|<span data-ttu-id="e0c78-218">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** 타입**\<** *랭크* **>** *[경계]* **>**</span><span class="sxs-lookup"><span data-stu-id="e0c78-218">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="e0c78-219">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="e0c78-219">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="e0c78-220">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="e0c78-220">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="e0c78-221">형식, 순위, 경계는 시그니처로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-221">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="e0c78-222">크기는 항상 런타임에 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-222">Size is always known at run time.</span></span>|  
|<span data-ttu-id="e0c78-223">**ELEMENT_TYPE_CLASS\*\*\*\*\<**<xref:System.Array?displayProperty=nameWithType>**>**</span><span class="sxs-lookup"><span data-stu-id="e0c78-223">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span></span>|<span data-ttu-id="e0c78-224">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="e0c78-224">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="e0c78-225">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="e0c78-225">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="e0c78-226">형식, 순위, 경계 및 크기는 항상 런타임에 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-226">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="e0c78-227">LPSTR 또는 LPWSTR이 포함된 구조체 배열에 관련된 OLE 자동화에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-227">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="e0c78-228">따라서 **String** 필드는 **UnmanagedType.BSTR**로 마샬링되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-228">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="e0c78-229">그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-229">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="element_type_szarray"></a><span data-ttu-id="e0c78-230">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="e0c78-230">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="e0c78-231">**ELEMENT_TYPE_SZARRAY** 매개 변수(1차원 배열)가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보내면 배열 매개 변수가 지정된 형식의 **SAFEARRAY**로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-231">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="e0c78-232">같은 변환 규칙이 배열 요소 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-232">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="e0c78-233">관리되는 배열의 콘텐츠는 관리되는 메모리에서 **SAFEARRAY**로 자동으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-233">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="e0c78-234">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-234">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="e0c78-235">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="e0c78-235">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="e0c78-236">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="e0c78-236">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="e0c78-237">안전 배열의 순위는 항상 1이고 하한은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-237">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="e0c78-238">크기는 런타임에 전달 중인 관리되는 배열 크기에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-238">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="e0c78-239"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 배열을 C 스타일 배열로 마샬링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-239">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="e0c78-240">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-240">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="e0c78-241">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="e0c78-241">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=
   UnmanagedType.LPStr, SizeParamIndex=1)]
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="e0c78-242">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="e0c78-242">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="e0c78-243">마샬러에는 배열을 마샬링하는 데 필요한 길이 정보가 있지만 배열 길이는 대개 호출 수신자에게 길이를 전달하기 위한 개별 인수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-243">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="element_type_array"></a><span data-ttu-id="e0c78-244">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="e0c78-244">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="e0c78-245">**ELEMENT_TYPE_ARRAY** 매개 변수가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보내면 배열 매개 변수가 지정된 형식의 **SAFEARRAY**로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-245">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="e0c78-246">관리되는 배열의 콘텐츠는 관리되는 메모리에서 **SAFEARRAY**로 자동으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-246">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="e0c78-247">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-247">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="e0c78-248">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="e0c78-248">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="e0c78-249">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="e0c78-249">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="e0c78-250">안전 배열의 순위, 크기 및 경계는 런타임에 관리되는 배열의 특징에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-250">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="e0c78-251"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 적용하여 배열을 C 스타일 배열로 마샬링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-251">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="e0c78-252">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-252">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="e0c78-253">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="e0c78-253">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="e0c78-254">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="e0c78-254">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="e0c78-255">중첩 배열은 마샬링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-255">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="e0c78-256">예를 들어 다음 시그니처는 [형식 라이브러리 내보내기(Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md)를 통해 내보낼 경우 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-256">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="e0c78-257">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="e0c78-257">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a><span data-ttu-id="e0c78-258">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="e0c78-258">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="e0c78-259"><xref:System.Array?displayProperty=nameWithType> 매개 변수가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보내면 배열 매개 변수가 **_Array** 인터페이스로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-259">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="e0c78-260">관리되는 배열의 콘텐츠는 **_Array** 인터페이스의 메서드 및 속성을 통해서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-260">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="e0c78-261"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 **System.Array**를 **SAFEARRAY**로 마샬링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-261">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="e0c78-262">안전 배열로 마샬링될 경우 배열 요소는 변형으로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-262">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="e0c78-263">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-263">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="e0c78-264">관리되는 시그니처</span><span class="sxs-lookup"><span data-stu-id="e0c78-264">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="e0c78-265">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="e0c78-265">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="e0c78-266">구조체가 있는 배열</span><span class="sxs-lookup"><span data-stu-id="e0c78-266">Arrays within Structures</span></span>  
 <span data-ttu-id="e0c78-267">관리되지 않는 구조체에는 포함된 배열이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-267">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="e0c78-268">기본적으로 이러한 포함된 배열 필드는 SAFEARRAY로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-268">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="e0c78-269">다음 예제에서 `s1`은 구조체 자체 내에서 직접 할당되는 포함된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-269">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="e0c78-270">관리되지 않는 표현</span><span class="sxs-lookup"><span data-stu-id="e0c78-270">Unmanaged representation</span></span>  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="e0c78-271">배열은 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 필드를 설정해야 하는 <xref:System.Runtime.InteropServices.UnmanagedType>으로 마샬링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-271">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="e0c78-272">크기는 상수로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-272">The size can be set only as a constant.</span></span> <span data-ttu-id="e0c78-273">다음 코드에서는 `MyStruct`의 해당 관리되는 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0c78-273">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0c78-274">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0c78-274">See also</span></span>

- [<span data-ttu-id="e0c78-275">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="e0c78-275">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="e0c78-276">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="e0c78-276">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="e0c78-277">[방향 특성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e0c78-277">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="e0c78-278">복사 및 고정</span><span class="sxs-lookup"><span data-stu-id="e0c78-278">Copying and Pinning</span></span>](copying-and-pinning.md)
