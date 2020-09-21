---
title: 개체에 대한 마샬링
description: 개체에 대한 기본 마샬링을 이해합니다. 마샬링 옵션을 검토합니다. 개체를 인터페이스 또는 변형, 개체 변형 및 ByRef 변형으로 마샬링합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
ms.openlocfilehash: 3e07ceef62d97db4206f530aa0859b101fe41a11
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555096"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="41bfa-105">개체에 대한 마샬링</span><span class="sxs-lookup"><span data-stu-id="41bfa-105">Default Marshaling for Objects</span></span>

<span data-ttu-id="41bfa-106"><xref:System.Object?displayProperty=nameWithType>로 형식화된 매개 변수와 필드는 비관리 코드에 다음 형식 하나로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-106">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>

- <span data-ttu-id="41bfa-107">개체가 매개 변수인 경우 변형.</span><span class="sxs-lookup"><span data-stu-id="41bfa-107">A variant when the object is a parameter.</span></span>

- <span data-ttu-id="41bfa-108">개체가 구조체 필드인 경우 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="41bfa-108">An interface when the object is a structure field.</span></span>

<span data-ttu-id="41bfa-109">COM interop만 개체 형식에 대한 마샬링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-109">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="41bfa-110">기본 동작은 개체를 COM 변형으로 마샬링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-110">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="41bfa-111">이러한 규칙은 **개체**에만 적용되고 **Object** 클래스에서 파생되는 강력한 형식의 개체에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-111">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>

## <a name="marshaling-options"></a><span data-ttu-id="41bfa-112">마샬링 옵션</span><span class="sxs-lookup"><span data-stu-id="41bfa-112">Marshaling Options</span></span>

<span data-ttu-id="41bfa-113">다음 표에서는 **Object** 데이터 형식에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-113">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="41bfa-114"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 개체를 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-114">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>

|<span data-ttu-id="41bfa-115">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="41bfa-115">Enumeration type</span></span>|<span data-ttu-id="41bfa-116">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="41bfa-116">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="41bfa-117">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="41bfa-117">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="41bfa-118">(매개 변수 기본값)</span><span class="sxs-lookup"><span data-stu-id="41bfa-118">(default for parameters)</span></span>|<span data-ttu-id="41bfa-119">COM 스타일 변형.</span><span class="sxs-lookup"><span data-stu-id="41bfa-119">A COM-style variant.</span></span>|
|<span data-ttu-id="41bfa-120">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="41bfa-120">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="41bfa-121">**IDispatch** 인터페이스(가능한 경우), 이외에는 **IUnknown** 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="41bfa-121">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|
|<span data-ttu-id="41bfa-122">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="41bfa-122">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="41bfa-123">(필드 기본값)</span><span class="sxs-lookup"><span data-stu-id="41bfa-123">(default for fields)</span></span>|<span data-ttu-id="41bfa-124">**IUnknown** 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="41bfa-124">An **IUnknown** interface.</span></span>|
|<span data-ttu-id="41bfa-125">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="41bfa-125">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="41bfa-126">**IDispatch** 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="41bfa-126">An **IDispatch** interface.</span></span>|

<span data-ttu-id="41bfa-127">다음 예제에서는 `MarshalObject`에 대한 관리되는 인터페이스 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-127">The following example shows the managed interface definition for `MarshalObject`.</span></span>

```vb
Interface MarshalObject
   Sub SetVariant(o As Object)
   Sub SetVariantRef(ByRef o As Object)
   Function GetVariant() As Object

   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _
      As Object)
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _
      As Object)
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object
End Interface
```

```csharp
interface MarshalObject {
   void SetVariant(Object o);
   void SetVariantRef(ref Object o);
   Object GetVariant();

   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();
}
```

<span data-ttu-id="41bfa-128">다음 코드는 `MarshalObject` 인터페이스를 형식 라이브러리에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-128">The following code exports the `MarshalObject` interface to a type library.</span></span>

```cpp
interface MarshalObject {
   HRESULT SetVariant([in] VARIANT o);
   HRESULT SetVariantRef([in,out] VARIANT *o);
   HRESULT GetVariant([out,retval] VARIANT *o)
   HRESULT SetIDispatch([in] IDispatch *o);
   HRESULT SetIDispatchRef([in,out] IDispatch **o);
   HRESULT GetIDispatch([out,retval] IDispatch **o)
   HRESULT SetIUnknown([in] IUnknown *o);
   HRESULT SetIUnknownRef([in,out] IUnknown **o);
   HRESULT GetIUnknown([out,retval] IUnknown **o)
}
```

> [!NOTE]
> <span data-ttu-id="41bfa-129">Interop 마샬러는 호출한 후 변형 내부에서 할당된 메모리를 자동으로 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-129">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>

<span data-ttu-id="41bfa-130">다음 예제에서는 서식 있는 값 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-130">The following example shows a formatted value type.</span></span>

```vb
Public Structure ObjectHolder
   Dim o1 As Object
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object
End Structure
```

```csharp
public struct ObjectHolder {
   Object o1;
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;
}
```

<span data-ttu-id="41bfa-131">다음 코드는 서식 있는 형식을 형식 라이브러리에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-131">The following code exports the formatted type to a type library.</span></span>

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a><span data-ttu-id="41bfa-132">인터페이스에 개체 마샬링</span><span class="sxs-lookup"><span data-stu-id="41bfa-132">Marshaling Object to Interface</span></span>

<span data-ttu-id="41bfa-133">개체가 COM에 인터페이스로 노출되면 해당 인터페이스는 관리되는 형식 <xref:System.Object>에 대한 클래스 인터페이스입니다( **_Object** 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="41bfa-133">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="41bfa-134">이 인터페이스는 결과 형식 라이브러리에서 **IDispatch**(<xref:System.Runtime.InteropServices.UnmanagedType>) 또는 **IUnknown**(**UnmanagedType.IUnknown**)으로 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-134">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="41bfa-135">COM 클라이언트는 **_Object** 인터페이스를 통해 관리되는 클래스 또는 파생 클래스에 의해 구현된 모든 멤버를 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-135">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="41bfa-136">클라이언트는 **QueryInterface**를 호출하여 관리되는 형식에 의해 명시적으로 구현된 다른 인터페이스를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-136">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>

## <a name="marshaling-object-to-variant"></a><span data-ttu-id="41bfa-137">변형에 개체 마샬링</span><span class="sxs-lookup"><span data-stu-id="41bfa-137">Marshaling Object to Variant</span></span>

<span data-ttu-id="41bfa-138">개체가 변형에 마샬링되면 내부 변형 형식은 런타임에 다음 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-138">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>

- <span data-ttu-id="41bfa-139">개체 참조가 null(Visual Basic의 경우 **Nothing**)이면 개체는 **VT_EMPTY** 형식 변형에 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-139">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>

- <span data-ttu-id="41bfa-140">개체가 다음 표에 나열된 형식의 인스턴스이면 결과 변형 형식은 표에 나와 있는 대로 마샬러에 기본 제공된 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-140">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>

- <span data-ttu-id="41bfa-141">마샬링 동작을 명시적으로 제어해야 하는 기타 개체는 <xref:System.IConvertible> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-141">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="41bfa-142">이 경우 변형 형식은 <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> 메서드에서 반환된 형식 코드에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-142">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="41bfa-143">이외의 경우에는 개체가 **VT_UNKNOWN** 형식 변형으로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-143">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>

### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="41bfa-144">변형에 시스템 형식 마샬링</span><span class="sxs-lookup"><span data-stu-id="41bfa-144">Marshaling System Types to Variant</span></span>

<span data-ttu-id="41bfa-145">다음 표에서는 관리 개체 형식 및 해당 COM 변형 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-145">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="41bfa-146">이러한 형식은 호출되는 메서드의 시그니처가 <xref:System.Object?displayProperty=nameWithType> 형식인 경우에만 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-146">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>

|<span data-ttu-id="41bfa-147">개체 유형</span><span class="sxs-lookup"><span data-stu-id="41bfa-147">Object type</span></span>|<span data-ttu-id="41bfa-148">COM 변형 형식</span><span class="sxs-lookup"><span data-stu-id="41bfa-148">COM variant type</span></span>|
|-----------------|----------------------|
|<span data-ttu-id="41bfa-149">Null 개체 참조(Visual Basic의 경우 **Nothing**).</span><span class="sxs-lookup"><span data-stu-id="41bfa-149">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="41bfa-150">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-150">**VT_EMPTY**</span></span>|
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="41bfa-151">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-151">**VT_NULL**</span></span>|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="41bfa-152">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="41bfa-152">**VT_ERROR**</span></span>|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="41bfa-153">**VT_ERROR**(**E_PARAMNOTFOUND** 포함)</span><span class="sxs-lookup"><span data-stu-id="41bfa-153">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="41bfa-154">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="41bfa-154">**VT_DISPATCH**</span></span>|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="41bfa-155">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="41bfa-155">**VT_UNKNOWN**</span></span>|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="41bfa-156">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-156">**VT_CY**</span></span>|
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="41bfa-157">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-157">**VT_BOOL**</span></span>|
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="41bfa-158">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="41bfa-158">**VT_I1**</span></span>|
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="41bfa-159">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="41bfa-159">**VT_UI1**</span></span>|
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="41bfa-160">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="41bfa-160">**VT_I2**</span></span>|
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="41bfa-161">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="41bfa-161">**VT_UI2**</span></span>|
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="41bfa-162">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-162">**VT_I4**</span></span>|
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="41bfa-163">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-163">**VT_UI4**</span></span>|
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="41bfa-164">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-164">**VT_I8**</span></span>|
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="41bfa-165">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-165">**VT_UI8**</span></span>|
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="41bfa-166">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-166">**VT_R4**</span></span>|
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="41bfa-167">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-167">**VT_R8**</span></span>|
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="41bfa-168">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-168">**VT_DECIMAL**</span></span>|
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="41bfa-169">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="41bfa-169">**VT_DATE**</span></span>|
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="41bfa-170">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="41bfa-170">**VT_BSTR**</span></span>|
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="41bfa-171">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-171">**VT_INT**</span></span>|
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="41bfa-172">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-172">**VT_UINT**</span></span>|
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="41bfa-173">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-173">**VT_ARRAY**</span></span>|

<span data-ttu-id="41bfa-174">다음 코드 예제에서는 이전 예제에서 정의된 `MarshalObject` 인터페이스를 사용하여 다양한 변형 형식을 COM 서버에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-174">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>

```vb
Dim mo As New MarshalObject()
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.
```

```csharp
MarshalObject mo = new MarshalObject();
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.
```

<span data-ttu-id="41bfa-175">일치하는 관리되는 형식이 없는 COM 형식은 <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, <xref:System.Runtime.InteropServices.CurrencyWrapper> 등의 래퍼 클래스를 사용하여 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-175">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="41bfa-176">다음 코드 예제에서는 이러한 래퍼를 사용하여 다양한 변형 형식을 COM 서버에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-176">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>

```vb
Imports System.Runtime.InteropServices
' Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(New UnknownWrapper(inew))
' Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(New DispatchWrapper(inew))
' Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(New ErrorWrapper(&H80054002))
' Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))
```

```csharp
using System.Runtime.InteropServices;
// Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(new UnknownWrapper(inew));
// Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(new DispatchWrapper(inew));
// Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(new ErrorWrapper(0x80054002));
// Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));
```

<span data-ttu-id="41bfa-177">래퍼 클래스는 <xref:System.Runtime.InteropServices> 네임스페이스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-177">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>

### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="41bfa-178">변형에 IConvertible 인터페이스 마샬링</span><span class="sxs-lookup"><span data-stu-id="41bfa-178">Marshaling the IConvertible Interface to Variant</span></span>

<span data-ttu-id="41bfa-179">이전 섹션에 나와 있지 않은 형식의 경우 <xref:System.IConvertible> 인터페이스를 구현하여 형식을 마샬링하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-179">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="41bfa-180">개체가 **IConvertible** 인터페이스를 구현할 경우 COM 변형 형식은 런타임에 <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> 메서드에서 반환된 <xref:System.TypeCode> 열거형 값에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-180">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="41bfa-181">다음 표에서는 **TypeCode** 열거형의 가능한 값과 각 값에 대한 일치하는 COM 변형 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-181">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>

|<span data-ttu-id="41bfa-182">TypeCode</span><span class="sxs-lookup"><span data-stu-id="41bfa-182">TypeCode</span></span>|<span data-ttu-id="41bfa-183">COM 변형 형식</span><span class="sxs-lookup"><span data-stu-id="41bfa-183">COM variant type</span></span>|
|--------------|----------------------|
|<span data-ttu-id="41bfa-184">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="41bfa-184">**TypeCode.Empty**</span></span>|<span data-ttu-id="41bfa-185">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-185">**VT_EMPTY**</span></span>|
|<span data-ttu-id="41bfa-186">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="41bfa-186">**TypeCode.Object**</span></span>|<span data-ttu-id="41bfa-187">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="41bfa-187">**VT_UNKNOWN**</span></span>|
|<span data-ttu-id="41bfa-188">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="41bfa-188">**TypeCode.DBNull**</span></span>|<span data-ttu-id="41bfa-189">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-189">**VT_NULL**</span></span>|
|<span data-ttu-id="41bfa-190">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="41bfa-190">**TypeCode.Boolean**</span></span>|<span data-ttu-id="41bfa-191">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-191">**VT_BOOL**</span></span>|
|<span data-ttu-id="41bfa-192">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="41bfa-192">**TypeCode.Char**</span></span>|<span data-ttu-id="41bfa-193">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="41bfa-193">**VT_UI2**</span></span>|
|<span data-ttu-id="41bfa-194">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="41bfa-194">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="41bfa-195">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="41bfa-195">**VT_I1**</span></span>|
|<span data-ttu-id="41bfa-196">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="41bfa-196">**TypeCode.Byte**</span></span>|<span data-ttu-id="41bfa-197">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="41bfa-197">**VT_UI1**</span></span>|
|<span data-ttu-id="41bfa-198">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="41bfa-198">**TypeCode.Int16**</span></span>|<span data-ttu-id="41bfa-199">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="41bfa-199">**VT_I2**</span></span>|
|<span data-ttu-id="41bfa-200">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="41bfa-200">**TypeCode.UInt16**</span></span>|<span data-ttu-id="41bfa-201">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="41bfa-201">**VT_UI2**</span></span>|
|<span data-ttu-id="41bfa-202">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="41bfa-202">**TypeCode.Int32**</span></span>|<span data-ttu-id="41bfa-203">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-203">**VT_I4**</span></span>|
|<span data-ttu-id="41bfa-204">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="41bfa-204">**TypeCode.UInt32**</span></span>|<span data-ttu-id="41bfa-205">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-205">**VT_UI4**</span></span>|
|<span data-ttu-id="41bfa-206">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="41bfa-206">**TypeCode.Int64**</span></span>|<span data-ttu-id="41bfa-207">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-207">**VT_I8**</span></span>|
|<span data-ttu-id="41bfa-208">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="41bfa-208">**TypeCode.UInt64**</span></span>|<span data-ttu-id="41bfa-209">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-209">**VT_UI8**</span></span>|
|<span data-ttu-id="41bfa-210">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="41bfa-210">**TypeCode.Single**</span></span>|<span data-ttu-id="41bfa-211">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-211">**VT_R4**</span></span>|
|<span data-ttu-id="41bfa-212">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="41bfa-212">**TypeCode.Double**</span></span>|<span data-ttu-id="41bfa-213">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-213">**VT_R8**</span></span>|
|<span data-ttu-id="41bfa-214">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="41bfa-214">**TypeCode.Decimal**</span></span>|<span data-ttu-id="41bfa-215">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-215">**VT_DECIMAL**</span></span>|
|<span data-ttu-id="41bfa-216">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="41bfa-216">**TypeCode.DateTime**</span></span>|<span data-ttu-id="41bfa-217">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="41bfa-217">**VT_DATE**</span></span>|
|<span data-ttu-id="41bfa-218">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="41bfa-218">**TypeCode.String**</span></span>|<span data-ttu-id="41bfa-219">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="41bfa-219">**VT_BSTR**</span></span>|
|<span data-ttu-id="41bfa-220">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-220">Not supported.</span></span>|<span data-ttu-id="41bfa-221">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-221">**VT_INT**</span></span>|
|<span data-ttu-id="41bfa-222">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-222">Not supported.</span></span>|<span data-ttu-id="41bfa-223">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-223">**VT_UINT**</span></span>|
|<span data-ttu-id="41bfa-224">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-224">Not supported.</span></span>|<span data-ttu-id="41bfa-225">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-225">**VT_ARRAY**</span></span>|
|<span data-ttu-id="41bfa-226">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-226">Not supported.</span></span>|<span data-ttu-id="41bfa-227">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="41bfa-227">**VT_RECORD**</span></span>|
|<span data-ttu-id="41bfa-228">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-228">Not supported.</span></span>|<span data-ttu-id="41bfa-229">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-229">**VT_CY**</span></span>|
|<span data-ttu-id="41bfa-230">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-230">Not supported.</span></span>|<span data-ttu-id="41bfa-231">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-231">**VT_VARIANT**</span></span>|

<span data-ttu-id="41bfa-232">COM 변형 값은 **IConvertible.To** *Type* 인터페이스를 호출하여 결정됩니다. 여기서 **To** *Type*은 **IConvertible.GetTypeCode**에서 반환된 형식에 해당하는 변환 루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-232">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="41bfa-233">예를 들어 **IConvertible.GetTypeCode**에서 **TypeCode.Double**을 반환하는 개체는 **VT_R8** 형식의 COM 변형으로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-233">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="41bfa-234">**IConvertible** 인터페이스를 캐스팅하고 <xref:System.IConvertible.ToDouble%2A> 메서드를 호출하여 COM 변형의 **dblVal** 필드에 저장된 변형 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-234">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>

## <a name="marshaling-variant-to-object"></a><span data-ttu-id="41bfa-235">개체에 변형 마샬링</span><span class="sxs-lookup"><span data-stu-id="41bfa-235">Marshaling Variant to Object</span></span>

<span data-ttu-id="41bfa-236">변형을 개체에 마샬링하면 마샬링된 변형의 형식 및 때때로 값에 따라 생성된 개체 형식이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-236">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="41bfa-237">다음 표에서는 각 변형 형식 및 변형이 COM에서 .NET Framework로 전달될 때 마샬러가 만드는 일치하는 개체 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-237">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>

|<span data-ttu-id="41bfa-238">COM 변형 형식</span><span class="sxs-lookup"><span data-stu-id="41bfa-238">COM variant type</span></span>|<span data-ttu-id="41bfa-239">개체 유형</span><span class="sxs-lookup"><span data-stu-id="41bfa-239">Object type</span></span>|
|----------------------|-----------------|
|<span data-ttu-id="41bfa-240">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-240">**VT_EMPTY**</span></span>|<span data-ttu-id="41bfa-241">Null 개체 참조(Visual Basic의 경우 **Nothing**).</span><span class="sxs-lookup"><span data-stu-id="41bfa-241">Null object reference (**Nothing** in Visual Basic).</span></span>|
|<span data-ttu-id="41bfa-242">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-242">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-243">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="41bfa-243">**VT_DISPATCH**</span></span>|<span data-ttu-id="41bfa-244">**System.__ComObject** 또는 null((pdispVal == null)인 경우)</span><span class="sxs-lookup"><span data-stu-id="41bfa-244">**System.__ComObject** or null if (pdispVal == null)</span></span>|
|<span data-ttu-id="41bfa-245">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="41bfa-245">**VT_UNKNOWN**</span></span>|<span data-ttu-id="41bfa-246">**System.__ComObject** 또는 null((punkVal == null)인 경우)</span><span class="sxs-lookup"><span data-stu-id="41bfa-246">**System.__ComObject** or null if (punkVal == null)</span></span>|
|<span data-ttu-id="41bfa-247">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="41bfa-247">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-248">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-248">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-249">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="41bfa-249">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-250">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="41bfa-250">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-251">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="41bfa-251">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-252">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="41bfa-252">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-253">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-253">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-254">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-254">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-255">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-255">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-256">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-256">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-257">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="41bfa-257">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-258">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="41bfa-258">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-259">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="41bfa-259">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-260">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="41bfa-260">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-261">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="41bfa-261">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-262">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-262">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-263">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-263">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-264">**VT_ARRAY** &#124; **VT_** \*</span><span class="sxs-lookup"><span data-stu-id="41bfa-264">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-265">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="41bfa-265">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="41bfa-266">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="41bfa-266">**VT_RECORD**</span></span>|<span data-ttu-id="41bfa-267">일치하는 boxed 값 형식.</span><span class="sxs-lookup"><span data-stu-id="41bfa-267">Corresponding boxed value type.</span></span>|
|<span data-ttu-id="41bfa-268">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="41bfa-268">**VT_VARIANT**</span></span>|<span data-ttu-id="41bfa-269">지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-269">Not supported.</span></span>|

<span data-ttu-id="41bfa-270">COM에서 관리 코드에 전달된 다음 다시 COM에 전달되는 변형 형식은 호출하는 동안 동일한 변형 형식을 유지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-270">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="41bfa-271">**VT_DISPATCH** 형식 변형이 COM에서 .NET Framework에 전달될 경우 어떤 일이 나타나는지 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-271">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="41bfa-272">마샬링하는 동안 변형은 <xref:System.Object?displayProperty=nameWithType>로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-272">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="41bfa-273">**Object**가 다시 COM에 전달되면 다시 **VT_UNKNOWN** 형식 변형에 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-273">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="41bfa-274">개체가 관리 코드에서 COM에 마샬링될 때 생성된 변형이 처음에 개체를 생성하는 데 사용되는 변형과 같은 형식이라는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-274">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>

## <a name="marshaling-byref-variants"></a><span data-ttu-id="41bfa-275">ByRef 변형 마샬링</span><span class="sxs-lookup"><span data-stu-id="41bfa-275">Marshaling ByRef Variants</span></span>

<span data-ttu-id="41bfa-276">변형 자체는 값 또는 참조로 전달될 수 있지만 **VT_BYREF** 플래그를 변형 형식과 함께 사용하여 변형의 콘텐츠가 값 대신 참조로 전달되고 있음을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-276">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="41bfa-277">참조를 통한 변형 마샬링과 **VT_BYREF** 플래그를 통한 변형 마샬링의 차이점은 혼동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-277">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="41bfa-278">다음 그림에서는 차이점을 분명히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-278">The following illustration clarifies the differences:</span></span>

<span data-ttu-id="41bfa-279">![스택에 전달된 변형을 보여 주는 다이어그램](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span><span class="sxs-lookup"><span data-stu-id="41bfa-279">![Diagram that shows variant passed on the stack.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span></span>
<span data-ttu-id="41bfa-280">값 및 참조로 전달되는 변형</span><span class="sxs-lookup"><span data-stu-id="41bfa-280">Variants passed by value and by reference</span></span>

<span data-ttu-id="41bfa-281">**값을 통한 개체 및 변형 마샬링의 기본 동작**</span><span class="sxs-lookup"><span data-stu-id="41bfa-281">**Default behavior for marshaling objects and variants by value**</span></span>

- <span data-ttu-id="41bfa-282">관리 코드에서 COM에 개체를 전달할 경우 [변형에 개체 마샬링](#marshaling-object-to-variant)에 정의된 규칙에 따라 개체의 콘텐츠가 마샬러에서 생성된 새 변형에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-282">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#marshaling-object-to-variant).</span></span> <span data-ttu-id="41bfa-283">비관리 쪽에서 변형에 적용된 변경 내용은 호출에서 반환 시 다시 원래 개체에 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-283">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>

- <span data-ttu-id="41bfa-284">COM에서 관리 코드에 변형을 전달할 경우 [개체에 변형 마샬링](#marshaling-variant-to-object)에 정의된 규칙에 따라 변형의 콘텐츠가 새로 생성된 개체에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-284">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#marshaling-variant-to-object).</span></span> <span data-ttu-id="41bfa-285">관리 쪽에서 개체에 적용된 변경 내용은 호출에서 반환 시 다시 원래 변형에 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-285">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>

<span data-ttu-id="41bfa-286">**참조를 통한 개체 및 변형 마샬링의 기본 동작**</span><span class="sxs-lookup"><span data-stu-id="41bfa-286">**Default behavior for marshaling objects and variants by reference**</span></span>

<span data-ttu-id="41bfa-287">변경 내용을 다시 호출자에게 전파하려면 매개 변수를 참조로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-287">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="41bfa-288">예를 들어 C#에서 **ref**키워드(또는 Visual Basic 관리 코드의 경우 **ByRef**)를 사용하여 매개 변수를 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-288">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="41bfa-289">COM에서 참조 매개 변수는 **변형\*** 같은 포인터를 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-289">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>

- <span data-ttu-id="41bfa-290">개체를 COM에 참조로 전달하면 마샬러는 새 변형을 만들고 호출이 수행되기 전에 개체 참조의 콘텐츠를 변형에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-290">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="41bfa-291">사용자가 변형 콘텐츠를 자유롭게 변경할 수 있는 관리되지 않는 함수에 변형이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-291">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="41bfa-292">호출에서 반환 시 비관리 쪽에서 변형에 적용된 변경 내용이 다시 원래 개체에 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-292">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="41bfa-293">변형 형식이 호출에 전달된 변형 형식과 다를 경우 변경 내용이 다른 형식의 개체에 다시 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-293">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="41bfa-294">즉, 호출에 전달된 개체 형식이 호출에서 반환된 개체 형식과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-294">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>

- <span data-ttu-id="41bfa-295">변형을 관리 코드에 참조로 전달하면 마샬러가 새 개체를 만들고 호출을 수행하기 전에 변형 콘텐츠를 개체에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-295">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="41bfa-296">사용자가 개체를 자유롭게 변경할 수 있는 관리되는 함수에 개체 참조가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-296">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="41bfa-297">호출에서 반환 시 참조된 개체의 변경 내용이 다시 원래 변형에 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-297">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="41bfa-298">개체 형식이 호출에 전달된 개체 형식과 다를 경우 원래 변형의 형식이 변경되고 값이 다시 변형에 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-298">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="41bfa-299">즉, 호출에 전달된 변형 형식이 호출에서 반환된 변형 형식과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-299">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>

 <span data-ttu-id="41bfa-300">**VT_BYREF 플래그가 설정된 변형 마샬링의 기본 동작**</span><span class="sxs-lookup"><span data-stu-id="41bfa-300">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>

- <span data-ttu-id="41bfa-301">값으로 관리 코드에 전달되는 변형에는 변형에 값 대신 참조가 포함됨을 나타내도록 **VT_BYREF** 플래그가 설정되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-301">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="41bfa-302">이 경우 변형은 값으로 전달되므로 개체에 계속 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-302">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="41bfa-303">마샬러는 변형 콘텐츠를 자동으로 역참조하고 호출을 수행하기 전에 변형을 새로 생성된 개체에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-303">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="41bfa-304">그런 다음 개체가 관리되는 함수에 전달되지만 호출에서 반환 시 개체는 다시 원래 변형으로 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-304">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="41bfa-305">관리 개체의 변경 내용이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-305">Changes made to the managed object are lost.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="41bfa-306">변형에 **VT_BYREF** 플래그가 설정된 경우에도 값으로 전달된 변형 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-306">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>

- <span data-ttu-id="41bfa-307">참조로 관리 코드에 전달되는 변형에는 변형에 또 다른 참조가 포함됨을 나타내도록 **VT_BYREF** 플래그가 설정되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-307">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="41bfa-308">이 경우 변형은 참조로 전달되므로 **ref** 개체에 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-308">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="41bfa-309">마샬러는 변형 콘텐츠를 자동으로 역참조하고 호출을 수행하기 전에 변형을 새로 생성된 개체에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-309">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="41bfa-310">호출에서 반환 시 개체의 형식이 전달된 개체와 동일한 경우에만 개체 값이 다시 원래 변형 내의 참조에 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-310">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="41bfa-311">즉, 전파를 통해 **VT_BYREF** 플래그가 설정된 변형의 형식이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-311">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="41bfa-312">호출하는 동안 개체 형식이 변경되면 호출에서 반환 시 <xref:System.InvalidCastException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-312">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>

<span data-ttu-id="41bfa-313">다음 표에서는 변형 및 개체에 대한 전파 규칙을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41bfa-313">The following table summarizes the propagation rules for variants and objects.</span></span>

|<span data-ttu-id="41bfa-314">시작</span><span class="sxs-lookup"><span data-stu-id="41bfa-314">From</span></span>|<span data-ttu-id="41bfa-315">대상</span><span class="sxs-lookup"><span data-stu-id="41bfa-315">To</span></span>|<span data-ttu-id="41bfa-316">변경 내용이 다시 전파됨</span><span class="sxs-lookup"><span data-stu-id="41bfa-316">Changes propagated back</span></span>|
|----------|--------|-----------------------------|
|<span data-ttu-id="41bfa-317">**변형** *v*</span><span class="sxs-lookup"><span data-stu-id="41bfa-317">**Variant**  *v*</span></span>|<span data-ttu-id="41bfa-318">**개체** *o*</span><span class="sxs-lookup"><span data-stu-id="41bfa-318">**Object**  *o*</span></span>|<span data-ttu-id="41bfa-319">Never</span><span class="sxs-lookup"><span data-stu-id="41bfa-319">Never</span></span>|
|<span data-ttu-id="41bfa-320">**개체** *o*</span><span class="sxs-lookup"><span data-stu-id="41bfa-320">**Object**  *o*</span></span>|<span data-ttu-id="41bfa-321">**변형** *v*</span><span class="sxs-lookup"><span data-stu-id="41bfa-321">**Variant**  *v*</span></span>|<span data-ttu-id="41bfa-322">Never</span><span class="sxs-lookup"><span data-stu-id="41bfa-322">Never</span></span>|
|<span data-ttu-id="41bfa-323">**변형** ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="41bfa-323">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="41bfa-324">**Ref 개체** *o*</span><span class="sxs-lookup"><span data-stu-id="41bfa-324">**Ref Object**  *o*</span></span>|<span data-ttu-id="41bfa-325">항상</span><span class="sxs-lookup"><span data-stu-id="41bfa-325">Always</span></span>|
|<span data-ttu-id="41bfa-326">**Ref 개체** *o*</span><span class="sxs-lookup"><span data-stu-id="41bfa-326">**Ref object**  *o*</span></span>|<span data-ttu-id="41bfa-327">**변형** ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="41bfa-327">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="41bfa-328">항상</span><span class="sxs-lookup"><span data-stu-id="41bfa-328">Always</span></span>|
|<span data-ttu-id="41bfa-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="41bfa-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="41bfa-330">**개체** *o*</span><span class="sxs-lookup"><span data-stu-id="41bfa-330">**Object**  *o*</span></span>|<span data-ttu-id="41bfa-331">Never</span><span class="sxs-lookup"><span data-stu-id="41bfa-331">Never</span></span>|
|<span data-ttu-id="41bfa-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="41bfa-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="41bfa-333">**Ref 개체** *o*</span><span class="sxs-lookup"><span data-stu-id="41bfa-333">**Ref Object**  *o*</span></span>|<span data-ttu-id="41bfa-334">형식이 변경되지 않은 경우에만.</span><span class="sxs-lookup"><span data-stu-id="41bfa-334">Only if the type has not changed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="41bfa-335">참조</span><span class="sxs-lookup"><span data-stu-id="41bfa-335">See also</span></span>

- [<span data-ttu-id="41bfa-336">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="41bfa-336">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="41bfa-337">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="41bfa-337">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="41bfa-338">[방향 특성](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="41bfa-338">[Directional Attributes](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="41bfa-339">복사 및 고정</span><span class="sxs-lookup"><span data-stu-id="41bfa-339">Copying and Pinning</span></span>](copying-and-pinning.md)
