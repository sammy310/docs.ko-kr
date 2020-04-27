---
title: 매개 변수 마샬링 사용자 지정 - .NET
description: .NET에서 매개 변수를 네이티브 표현으로 마샬링하는 방식을 사용자 지정하는 방법을 알아봅니다.
ms.date: 01/18/2019
ms.openlocfilehash: ff646ad942cf051ce90cd75b24c8562e536182d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401162"
---
# <a name="customizing-parameter-marshaling"></a><span data-ttu-id="b5e18-103">매개 변수 마샬링 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b5e18-103">Customizing parameter marshaling</span></span>

<span data-ttu-id="b5e18-104">.NET 런타임의 기본 매개 변수 마샬링 동작이 원하는 대로 작동하지 않을 경우, <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 특성을 사용하여 매개 변수가 마샬링되는 방식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-104">When the .NET runtime's default parameter marshaling behavior doesn't do what you want, use can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> attribute to customize how your parameters are marshaled.</span></span>

## <a name="customizing-string-parameters"></a><span data-ttu-id="b5e18-105">문자열 매개 변수 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b5e18-105">Customizing string parameters</span></span>

<span data-ttu-id="b5e18-106">.NET에는 문자열을 마샬링하기 위한 다양한 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-106">.NET has a variety of formats for marshaling strings.</span></span> <span data-ttu-id="b5e18-107">이러한 메서드는 C 스타일 문자열 및 Windows 중심 문자열 형식에 대한 개별 섹션으로 나누어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-107">These methods are split into distinct sections on C-style strings and Windows-centric string formats.</span></span>

### <a name="c-style-strings"></a><span data-ttu-id="b5e18-108">C 스타일 문자열</span><span class="sxs-lookup"><span data-stu-id="b5e18-108">C-Style strings</span></span>

<span data-ttu-id="b5e18-109">이러한 형식은 각각 Null 종료 문자열을 네이티브 코드에 전달하며,</span><span class="sxs-lookup"><span data-stu-id="b5e18-109">Each of these formats passes a null-terminated string to native code.</span></span> <span data-ttu-id="b5e18-110">네이티브 문자열의 인코딩에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-110">They differ by the encoding of the native string.</span></span>

| <span data-ttu-id="b5e18-111">`System.Runtime.InteropServices.UnmanagedType` 값</span><span class="sxs-lookup"><span data-stu-id="b5e18-111">`System.Runtime.InteropServices.UnmanagedType` value</span></span> | <span data-ttu-id="b5e18-112">인코딩</span><span class="sxs-lookup"><span data-stu-id="b5e18-112">Encoding</span></span> |
|------------------------------------------------------|----------|
| <span data-ttu-id="b5e18-113">LPStr</span><span class="sxs-lookup"><span data-stu-id="b5e18-113">LPStr</span></span> | <span data-ttu-id="b5e18-114">ANSI</span><span class="sxs-lookup"><span data-stu-id="b5e18-114">ANSI</span></span> |
| <span data-ttu-id="b5e18-115">LPUTF8Str</span><span class="sxs-lookup"><span data-stu-id="b5e18-115">LPUTF8Str</span></span> | <span data-ttu-id="b5e18-116">UTF-8</span><span class="sxs-lookup"><span data-stu-id="b5e18-116">UTF-8</span></span> |
| <span data-ttu-id="b5e18-117">LPWStr</span><span class="sxs-lookup"><span data-stu-id="b5e18-117">LPWStr</span></span> | <span data-ttu-id="b5e18-118">UTF-16</span><span class="sxs-lookup"><span data-stu-id="b5e18-118">UTF-16</span></span> |
| <span data-ttu-id="b5e18-119">LPTStr</span><span class="sxs-lookup"><span data-stu-id="b5e18-119">LPTStr</span></span> | <span data-ttu-id="b5e18-120">UTF-16</span><span class="sxs-lookup"><span data-stu-id="b5e18-120">UTF-16</span></span> |

<span data-ttu-id="b5e18-121"><xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> 형식은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-121">The <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> format is slightly different.</span></span> <span data-ttu-id="b5e18-122">`LPWStr`과 마찬가지로, 이 형식은 문자열을 UTF-16으로 인코드된 네이티브 C 스타일 문자열로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-122">Like `LPWStr`, it marshals the string to a native C-style string encoded in UTF-16.</span></span> <span data-ttu-id="b5e18-123">그러나 관리형 시그니처는 문자열을 참조로 전달하게 하고, 일치하는 네이티브 시그니처는 문자열을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-123">However, the managed signature has you pass in the string by reference and the matching native signature takes the string by value.</span></span> <span data-ttu-id="b5e18-124">이러한 차이를 통해 `StringBuilder`를 사용하지 않고도 문자열을 값으로 사용하고 현재 위치에서 수정하는 네이티브 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-124">This distinction allows you to use a native API that takes a string by value and modifies it in-place without having to use a `StringBuilder`.</span></span> <span data-ttu-id="b5e18-125">네이티브 시그니처와 관리형 시그니처의 불일치와 혼동되는 경향이 있으므로 이 형식을 수동으로 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-125">We recommend against manually using this format since it's prone to cause confusion with the mismatching native and managed signatures.</span></span>

### <a name="windows-centric-string-formats"></a><span data-ttu-id="b5e18-126">Windows 중심 문자열 형식</span><span class="sxs-lookup"><span data-stu-id="b5e18-126">Windows-centric string formats</span></span>

<span data-ttu-id="b5e18-127">COM 또는 OLE 인터페이스를 조작하는 경우 네이티브 함수가 문자열을 `BSTR` 인수로 사용하는 것을 보게 될 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-127">When interacting with COM or OLE interfaces, you'll likely find that the native functions take strings as `BSTR` arguments.</span></span> <span data-ttu-id="b5e18-128"><xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> 비관리형 형식을 사용하여 문자열을 `BSTR`로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-128">You can use the <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> unmanaged type to marshal a string as a `BSTR`.</span></span>

<span data-ttu-id="b5e18-129">WinRT API를 조작하는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> 형식을 사용하여 문자열을 `HSTRING`로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-129">If you're interacting with WinRT APIs, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> format to marshal a string as an `HSTRING`.</span></span>

## <a name="customizing-array-parameters"></a><span data-ttu-id="b5e18-130">배열 매개 변수 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b5e18-130">Customizing array parameters</span></span>

<span data-ttu-id="b5e18-131">.NET에서는 배열 매개 변수를 마샬링하는 몇 가지 방법도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-131">.NET also provides you multiple ways to marshal array parameters.</span></span> <span data-ttu-id="b5e18-132">C 스타일 배열을 사용하는 API를 호출하는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType> 비관리형 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-132">If you're calling an API that takes a C-style array, use the <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType> unmanaged type.</span></span> <span data-ttu-id="b5e18-133">배열의 값에 사용자 지정 마샬링이 필요한 경우 해당 배열의 `[MarshalAs]` 특성에 있는 <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-133">If the values in the array need customized marshaling, you can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> field on the `[MarshalAs]` attribute for that.</span></span>

<span data-ttu-id="b5e18-134">COM API를 사용하는 경우 배열 매개 변수를 `SAFEARRAY*`로 마샬링해야 할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-134">If you're using COM APIs, you'll likely have to marshal your array parameters as `SAFEARRAY*`s.</span></span> <span data-ttu-id="b5e18-135">이렇게 하려면 <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> 비관리형 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-135">To do so, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> unmanaged type.</span></span> <span data-ttu-id="b5e18-136">`SAFEARRAY` 요소의 기본 형식은 [`object` 필드 사용자 지정](./customize-struct-marshaling.md#marshaling-systemobjects)에 대한 표에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-136">The default type of the elements of the `SAFEARRAY` can be seen in the table on [customizing `object` fields](./customize-struct-marshaling.md#marshaling-systemobjects).</span></span> <span data-ttu-id="b5e18-137"><xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> 및 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> 필드를 사용하여 `SAFEARRAY`의 정확한 요소 형식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-137">You can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> fields to customize the exact element type of the `SAFEARRAY`.</span></span>

## <a name="customizing-boolean-or-decimal-parameters"></a><span data-ttu-id="b5e18-138">부울 또는 10진 매개 변수 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b5e18-138">Customizing boolean or decimal parameters</span></span>

<span data-ttu-id="b5e18-139">부울 또는 10진 매개 변수 마샬링에 대한 자세한 내용은 [구조체 마샬링 사용자 지정](customize-struct-marshaling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5e18-139">For information on marshaling boolean or decimal parameters, see [Customizing structure marshaling](customize-struct-marshaling.md).</span></span>

## <a name="customizing-object-parameters-windows-only"></a><span data-ttu-id="b5e18-140">개체 매개 변수 사용자 지정(Windows에만 해당)</span><span class="sxs-lookup"><span data-stu-id="b5e18-140">Customizing object parameters (Windows-only)</span></span>

<span data-ttu-id="b5e18-141">Windows에서 .NET 런타임은 개체 매개 변수를 네이티브 코드로 마샬링하는 몇 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-141">On Windows, the .NET runtime provides a number of different ways to marshal object parameters to native code.</span></span>

### <a name="marshaling-as-specific-com-interfaces"></a><span data-ttu-id="b5e18-142">특정 COM 인터페이스로 마샬링</span><span class="sxs-lookup"><span data-stu-id="b5e18-142">Marshaling as specific COM interfaces</span></span>

<span data-ttu-id="b5e18-143">API에서 COM 개체에 대한 포인터를 사용하는 경우 `object` 형식 매개 변수에 다음과 같은 `UnmanagedType` 형식 중 하나를 사용하여 이러한 특정 인터페이스로 마샬링하도록 .NET에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-143">If your API takes a pointer to a COM object, you can use any of the following `UnmanagedType` formats on an `object`-typed parameter to tell .NET to marshal as these specific interfaces:</span></span>

- `IUnknown`
- `IDispatch`
- `IInspectable`

<span data-ttu-id="b5e18-144">또한 형식이 `[ComVisible(true)]`로 표시되거나 `object` 형식을 마샬링하는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> 형식을 사용하여 해당 형식의 COM 보기에 대한 COM 호출 가능 래퍼로 개체를 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-144">Additionally, if your type is marked `[ComVisible(true)]` or you're marshaling the `object` type, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> format to marshal your object as a COM callable wrapper for the COM view of your type.</span></span>

### <a name="marshaling-to-a-variant"></a><span data-ttu-id="b5e18-145">`VARIANT`로 마샬링</span><span class="sxs-lookup"><span data-stu-id="b5e18-145">Marshaling to a `VARIANT`</span></span>

<span data-ttu-id="b5e18-146">네이티브 API에서 Win32 `VARIANT`를 사용하는 경우 `object` 매개 변수의 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> 형식을 사용하여 개체를 `VARIANT`로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-146">If your native API takes a Win32 `VARIANT`, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> format on your `object` parameter to marshal your objects as `VARIANT`s.</span></span> <span data-ttu-id="b5e18-147">.NET 형식과 `VARIANT` 형식 간의 매핑에 대해서는 [`object` 필드 사용자 지정](customize-struct-marshaling.md#marshaling-systemobjects) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5e18-147">See the documentation on [customizing `object` fields](customize-struct-marshaling.md#marshaling-systemobjects) for a mapping between .NET types and `VARIANT` types.</span></span>

### <a name="custom-marshalers"></a><span data-ttu-id="b5e18-148">사용자 설정 마샬러</span><span class="sxs-lookup"><span data-stu-id="b5e18-148">Custom marshalers</span></span>

<span data-ttu-id="b5e18-149">네이티브 COM 인터페이스를 다른 관리형 형식으로 프로젝트하려는 경우 `UnmanagedType.CustomMarshaler` 형식과 <xref:System.Runtime.InteropServices.ICustomMarshaler> 구현을 사용하여 사용자 고유의 사용자 지정 마샬링 코드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e18-149">If you want to project a native COM interface into a different managed type, you can use the `UnmanagedType.CustomMarshaler` format and an implementation of <xref:System.Runtime.InteropServices.ICustomMarshaler> to provide your own custom marshaling code.</span></span>
