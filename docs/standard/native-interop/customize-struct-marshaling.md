---
title: 구조체 마샬링 사용자 지정 - .NET
description: .NET에서 구조체를 네이티브 표현으로 마샬링하는 방식을 사용자 지정하는 방법을 알아봅니다.
ms.date: 01/18/2019
dev_langs:
- csharp
- cpp
ms.openlocfilehash: 8248ca589f41967a9112ba61c09599b337814de7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003895"
---
# <a name="customizing-structure-marshaling"></a><span data-ttu-id="24e5e-103">구조체 마샬링 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="24e5e-103">Customizing structure marshaling</span></span>

<span data-ttu-id="24e5e-104">구조체의 기본 마샬링 규칙이 필요한 것과 정확히 일치하지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-104">Sometimes the default marshaling rules for structures aren't exactly what you need.</span></span> <span data-ttu-id="24e5e-105">.NET 런타임에서는 구조체 레이아웃과 필드 마샬링 방식을 사용자 지정할 수 있는 몇 가지 확장점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-105">The .NET runtimes provide a few extension points for you to customize your structure's layout and how fields are marshaled.</span></span>

## <a name="customizing-structure-layout"></a><span data-ttu-id="24e5e-106">구조체 레이아웃 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="24e5e-106">Customizing structure layout</span></span>

<span data-ttu-id="24e5e-107">.NET에서는 메모리에 필드가 배치되는 방식을 사용자 지정할 수 있도록 <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> 특성과 <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType> 열거형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-107">.NET provides the <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> attribute and the <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType> enumeration to allow you to customize how fields are placed in memory.</span></span> <span data-ttu-id="24e5e-108">다음 지침은 일반적인 문제를 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-108">The following guidance will help you avoid common issues.</span></span>

<span data-ttu-id="24e5e-109">✔️ 가능한 경우 항상 `LayoutKind.Sequential`을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-109">✔️ CONSIDER using `LayoutKind.Sequential` whenever possible.</span></span>

<span data-ttu-id="24e5e-110">✔️ 네이티브 구조체에 공용 구조체 등의 명시적인 레이아웃도 있는 경우에만 마샬링할 때 `LayoutKind.Explicit`를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="24e5e-110">✔️ DO only use `LayoutKind.Explicit` in marshaling when your native struct also has an explicit layout, such as a union.</span></span>

<span data-ttu-id="24e5e-111">❌ .NET Core 3.0보다 이전의 런타임을 대상으로 해야 하는 경우 비 Windows 플랫폼에서 구조체를 마샬링할 때 `LayoutKind.Explicit`를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="24e5e-111">❌ AVOID using `LayoutKind.Explicit` when marshaling structures on non-Windows platforms if you need to target runtimes before .NET Core 3.0.</span></span> <span data-ttu-id="24e5e-112">.NET Core 3.0보다 이전의 런타임을 통해 Intel 또는 AMD 64비트 비 Windows 시스템에서 명시적 구조체를 네이티브 함수에 값으로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-112">The .NET Core runtime before 3.0 doesn't support passing explicit structures by value to native functions on Intel or AMD 64-bit non-Windows systems.</span></span> <span data-ttu-id="24e5e-113">그러나 런타임은 모든 플랫폼에서 명시적 구조체를 참조로 전달하는 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-113">However, the runtime supports passing explicit structures by reference on all platforms.</span></span>

## <a name="customizing-boolean-field-marshaling"></a><span data-ttu-id="24e5e-114">부울 필드 마샬링 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="24e5e-114">Customizing boolean field marshaling</span></span>

<span data-ttu-id="24e5e-115">네이티브 코드에는 여러 부울 표현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-115">Native code has many different boolean representations.</span></span> <span data-ttu-id="24e5e-116">Windows만 해도 부울 값을 나타내는 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-116">On Windows alone, there are three ways to represent boolean values.</span></span> <span data-ttu-id="24e5e-117">런타임은 구조체의 네이티브 정의를 알 수 없으므로, 부울 값을 나타내는 최상의 방법은 부울 값을 마샬링하는 방식을 추측하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-117">The runtime doesn't know the native definition of your structure, so the best it can do is make a guess on how to marshal your boolean values.</span></span> <span data-ttu-id="24e5e-118">.NET 런타임에서 부울 필드를 마샬링하는 방식을 나타내는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-118">The .NET runtime provides a way to indicate how to marshal your boolean field.</span></span> <span data-ttu-id="24e5e-119">다음 예제에서는 .NET `bool`을 여러 네이티브 부울 형식으로 마샬링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-119">The following examples show how to marshal .NET `bool` to different native boolean types.</span></span>

<span data-ttu-id="24e5e-120">다음 예제와 같이 부울 값은 기본적으로 네이티브 4바이트 Win32 [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL) 값으로 마샬링되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-120">Boolean values default to marshaling as a native 4-byte Win32 [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL) value as shown in the following example:</span></span>

```csharp
public struct WinBool
{
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

<span data-ttu-id="24e5e-121">명시적으로 설정하려는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> 값을 사용하여 위와 동일한 동작을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-121">If you want to be explicit, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> value to get the same behavior as above:</span></span>

```csharp
public struct WinBool
{
    [MarshalAs(UnmanagedType.Bool)]
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

<span data-ttu-id="24e5e-122">아래의 `UnmanagedType.U1` 또는 `UnmanagedType.I1` 값을 사용하여 `b` 필드를 1바이트 네이티브 `bool` 형식으로 마샬링하도록 런타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-122">Using the `UnmanagedType.U1` or `UnmanagedType.I1` values below, you can tell the runtime to marshal the `b` field as a 1-byte native `bool` type.</span></span>

```csharp
public struct CBool
{
    [MarshalAs(UnmanagedType.U1)]
    public bool b;
}
```

```cpp
struct CBool
{
    public bool b;
};
```

<span data-ttu-id="24e5e-123">Windows에서는 <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> 값을 사용하여 부울 값을 2바이트 `VARIANT_BOOL` 값으로 마샬링하도록 런타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-123">On Windows, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> value to tell the runtime to marshal your boolean value to a 2-byte `VARIANT_BOOL` value:</span></span>

```csharp
public struct VariantBool
{
    [MarshalAs(UnmanagedType.VariantBool)]
    public bool b;
}
```

```cpp
struct VariantBool
{
    public VARIANT_BOOL b;
};
```

> [!NOTE]
> <span data-ttu-id="24e5e-124">`VARIANT_BOOL`은 `VARIANT_TRUE = -1` 및 `VARIANT_FALSE = 0`인 점에서 대부분의 bool 형식과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-124">`VARIANT_BOOL` is different than most bool types in that `VARIANT_TRUE = -1` and `VARIANT_FALSE = 0`.</span></span> <span data-ttu-id="24e5e-125">또한 `VARIANT_TRUE`와 같지 않은 모든 값은 false로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-125">Additionally, all values that aren't equal to `VARIANT_TRUE` are considered false.</span></span>

## <a name="customizing-array-field-marshaling"></a><span data-ttu-id="24e5e-126">배열 필드 마샬링 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="24e5e-126">Customizing array field marshaling</span></span>

<span data-ttu-id="24e5e-127">.NET에는 배열 마샬링을 사용자 지정하는 몇 가지 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-127">.NET also includes a few ways to customize array marshaling.</span></span>

<span data-ttu-id="24e5e-128">기본적으로 .NET에서는 배열을 인접한 요소 목록에 대한 포인터로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-128">By default, .NET marshals arrays as a pointer to a contiguous list of the elements:</span></span>

```csharp
public struct DefaultArray
{
    public int[] values;
}
```

```cpp
struct DefaultArray
{
    int* values;
};
```

<span data-ttu-id="24e5e-129">COM API와 인터페이스하는 경우 배열을 `SAFEARRAY*` 개체로 마샬링해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-129">If you're interfacing with COM APIs, you may have to marshal arrays as `SAFEARRAY*` objects.</span></span> <span data-ttu-id="24e5e-130"><xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 및 <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> 값을 사용하여 배열을 `SAFEARRAY*`로 마샬링하도록 런타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-130">You can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> and the <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> value to tell the runtime to marshal an array as a `SAFEARRAY*`:</span></span>

```csharp
public struct SafeArrayExample
{
    [MarshalAs(UnmanagedType.SafeArray)]
    public int[] values;
}
```

```cpp
struct SafeArrayExample
{
    SAFEARRAY* values;
};
```

<span data-ttu-id="24e5e-131">`SAFEARRAY`에 포함되는 요소 형식을 사용자 지정해야 하는 경우 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> 및 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> 필드를 사용하여 `SAFEARRAY`의 정확한 요소 형식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-131">If you need to customize what type of element is in the `SAFEARRAY`, then you can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> fields to customize the exact element type of the `SAFEARRAY`.</span></span>

<span data-ttu-id="24e5e-132">현재 위치에서 배열을 마샬링해야 하는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> 값을 사용하여 현재 위치에서 배열을 마샬링하도록 마샬러에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-132">If you need to marshal the array in-place, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> value to tell the marshaler to marshal the array in-place.</span></span> <span data-ttu-id="24e5e-133">이 마샬링을 사용하는 경우, 런타임에서 구조체의 공간을 올바르게 할당할 수 있도록 배열의 요소 수에 대한 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> 필드에도 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-133">When you're using this marshaling, you also must supply a value to the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> field  for the number of elements in the array so the runtime can correctly allocate space for the structure.</span></span>

```csharp
public struct InPlaceArray
{
    [MarshalAs(UnmanagedType.ByValArray, SizeConst = 4)]
    public int[] values;
}
```

```cpp
struct InPlaceArray
{
    int values[4];
};
```

> [!NOTE]
> <span data-ttu-id="24e5e-134">.NET에서는 가변 길이 배열 필드를 C99 유연한 배열 멤버로 마샬링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-134">.NET doesn't support marshaling a variable length array field as a C99 Flexible Array Member.</span></span>

## <a name="customizing-string-field-marshaling"></a><span data-ttu-id="24e5e-135">문자열 필드 마샬링 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="24e5e-135">Customizing string field marshaling</span></span>

<span data-ttu-id="24e5e-136">.NET에서는 문자열 필드를 마샬링하기 위한 다양한 사용자 지정도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-136">.NET also provides a wide variety of customizations for marshaling string fields.</span></span>

<span data-ttu-id="24e5e-137">기본적으로 .NET은 문자열을 Null 종료 문자열에 대한 포인터로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-137">By default, .NET marshals a string as a pointer to a null-terminated string.</span></span> <span data-ttu-id="24e5e-138">인코딩은 <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>의 <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> 필드 값에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-138">The encoding depends on the value of the <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> field in the <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="24e5e-139">특성을 지정하지 않으면 인코딩은 기본적으로 ANSI 인코딩으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-139">If no attribute is specified, the encoding defaults to an ANSI encoding.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char* str;
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

<span data-ttu-id="24e5e-140">다른 필드에 다른 인코딩을 사용해야 하거나 구조체 정의를 좀 더 명시적으로 설정하려는 경우 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 특성에 <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> 또는 <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-140">If you need to use different encodings for different fields or just prefer to be more explicit in your struct definition, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> values on a <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> attribute.</span></span>

```csharp
public struct AnsiString
{
    [MarshalAs(UnmanagedType.LPStr)]
    public string str;
}
```

```cpp
struct AnsiString
{
    char* str;
};
```

```csharp
public struct UnicodeString
{
    [MarshalAs(UnmanagedType.LPWStr)]
    public string str;
}
```

```cpp
struct UnicodeString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

<span data-ttu-id="24e5e-141">UTF-8 인코딩을 사용하여 문자열을 마샬링하려는 경우 <xref:System.Runtime.InteropServices.MarshalAsAttribute>의 <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-141">If you want to marshal your strings using the UTF-8 encoding, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> value in your <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>

```csharp
public struct UTF8String
{
    [MarshalAs(UnmanagedType.LPUTF8Str)]
    public string str;
}
```

```cpp
struct UTF8String
{
    char* str;
};
```

> [!NOTE]
> <span data-ttu-id="24e5e-142"><xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType>을 사용하려면 .NET Framework 4.7 이상 버전이나 .NET Core 1.1 이상 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-142">Using <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> requires either .NET Framework 4.7 (or later versions) or .NET Core 1.1 (or later versions).</span></span> <span data-ttu-id="24e5e-143">.NET Standard 2.0에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-143">It isn't available in .NET Standard 2.0.</span></span>

<span data-ttu-id="24e5e-144">COM API로 작업하는 경우 문자열을 `BSTR`로 마샬링해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-144">If you're working with COM APIs, you may need to marshal a string as a `BSTR`.</span></span> <span data-ttu-id="24e5e-145"><xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> 값을 사용하여 문자열을 `BSTR`로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-145">Using the <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> value, you can marshal a string as a `BSTR`.</span></span>

```csharp
public struct BString
{
    [MarshalAs(UnmanagedType.BStr)]
    public string str;
}
```

```cpp
struct BString
{
    BSTR str;
};
```

<span data-ttu-id="24e5e-146">WinRT 기반 API를 사용하는 경우 문자열을 `HSTRING`로 마샬링해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-146">When using a WinRT-based API, you may need to marshal a string as an `HSTRING`.</span></span>  <span data-ttu-id="24e5e-147"><xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> 값을 사용하여 문자열을 `HSTRING`로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-147">Using the <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> value, you can marshal a string as a `HSTRING`.</span></span>

```csharp
public struct HString
{
    [MarshalAs(UnmanagedType.HString)]
    public string str;
}
```

```cpp
struct BString
{
    HSTRING str;
};
```

<span data-ttu-id="24e5e-148">API에서 구조체의 현재 위치에 문자열을 전달해야 하는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType> 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-148">If your API requires you to pass the string in-place in the structure, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType> value.</span></span> <span data-ttu-id="24e5e-149">`ByValTStr`에 의해 마샬링된 문자열의 인코딩은 `CharSet` 특성으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-149">Do note that the encoding for a string marshaled by `ByValTStr` is determined from the `CharSet` attribute.</span></span> <span data-ttu-id="24e5e-150">또한 문자열 길이가 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> 필드에 의해 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-150">Additionally, it requires that a string length is passed by the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> field.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char str[4];
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t str[4]; // Could also be wchar_t[4] on Windows.
};
```

## <a name="customizing-decimal-field-marshaling"></a><span data-ttu-id="24e5e-151">10진 필드 마샬링 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="24e5e-151">Customizing decimal field marshaling</span></span>

<span data-ttu-id="24e5e-152">Windows에서 작업하는 경우 네이티브 [`CY` 또는 `CURRENCY`](/windows/win32/api/wtypes/ns-wtypes-cy~r1) 구조체를 사용하는 일부 API를 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-152">If you're working on Windows, you might encounter some APIs that use the native [`CY` or `CURRENCY`](/windows/win32/api/wtypes/ns-wtypes-cy~r1) structure.</span></span> <span data-ttu-id="24e5e-153">기본적으로 .NET `decimal` 형식은 네이티브 [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1) 구조체로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-153">By default, the .NET `decimal` type marshals to the native [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1) structure.</span></span> <span data-ttu-id="24e5e-154">그러나 <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> 값과 함께 <xref:System.Runtime.InteropServices.MarshalAsAttribute>를 사용하여 `decimal` 값을 네이티브 `CY` 값으로 변환하도록 마샬러에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-154">However, you can use a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> value to instruct the marshaler to convert a `decimal` value to a native `CY` value.</span></span>

```csharp
public struct Currency
{
    [MarshalAs(UnmanagedType.Currency)]
    public decimal dec;
}
```

```cpp
struct Currency
{
    CY dec;
};
```

## <a name="marshaling-systemobjects"></a><span data-ttu-id="24e5e-155">`System.Object` 마샬링</span><span class="sxs-lookup"><span data-stu-id="24e5e-155">Marshaling `System.Object`s</span></span>

<span data-ttu-id="24e5e-156">Windows에서 `object` 형식 필드를 네이티브 코드로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-156">On Windows, you can marshal `object`-typed fields to native code.</span></span> <span data-ttu-id="24e5e-157">이러한 필드는 다음 세 가지 형식 중 하나로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-157">You can marshal these fields to one of three types:</span></span>

- [`VARIANT`](/windows/win32/api/oaidl/ns-oaidl-variant)
- [`IUnknown*`](/windows/desktop/api/unknwn/nn-unknwn-iunknown)
- [`IDispatch*`](/windows/desktop/api/oaidl/nn-oaidl-idispatch)

<span data-ttu-id="24e5e-158">기본적으로 `object` 형식 필드는 개체를 래핑하는 `IUnknown*`으로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-158">By default, an `object`-typed field will be marshaled to an `IUnknown*` that wraps the object.</span></span>

```csharp
public struct ObjectDefault
{
    public object obj;
}
```

```cpp
struct ObjectDefault
{
    IUnknown* obj;
};
```

<span data-ttu-id="24e5e-159">개체 필드를 `IDispatch*`로 마샬링하려는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType> 값과 함께 <xref:System.Runtime.InteropServices.MarshalAsAttribute>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-159">If you want to marshal an object field to an `IDispatch*`, add a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType> value.</span></span>

```csharp
public struct ObjectDispatch
{
    [MarshalAs(UnmanagedType.IDispatch)]
    public object obj;
}
```

```cpp
struct ObjectDispatch
{
    IDispatch* obj;
};
```

<span data-ttu-id="24e5e-160">`VARIANT`로 마샬링하려는 경우 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> 값과 함께 <xref:System.Runtime.InteropServices.MarshalAsAttribute>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-160">If you want to marshal it as a `VARIANT`, add a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> value.</span></span>

```csharp
public struct ObjectVariant
{
    [MarshalAs(UnmanagedType.Struct)]
    public object obj;
}
```

```cpp
struct ObjectVariant
{
    VARIANT obj;
};
```

<span data-ttu-id="24e5e-161">다음 표에서는 `obj` 필드의 여러 런타임 형식이 `VARIANT`에 저장된 다양한 형식에 매핑되는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24e5e-161">The following table describes how different runtime types of the `obj` field map to the various types stored in a `VARIANT`:</span></span>

| <span data-ttu-id="24e5e-162">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="24e5e-162">.NET Type</span></span> | <span data-ttu-id="24e5e-163">VARIANT 형식</span><span class="sxs-lookup"><span data-stu-id="24e5e-163">VARIANT Type</span></span> | | <span data-ttu-id="24e5e-164">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="24e5e-164">.NET Type</span></span> | <span data-ttu-id="24e5e-165">VARIANT 형식</span><span class="sxs-lookup"><span data-stu-id="24e5e-165">VARIANT Type</span></span> |
|------------|--------------|-|----------|--------------|
|  `byte`  | `VT_UI1` |     | `System.Runtime.InteropServices.BStrWrapper` | `VT_BSTR` |
| `sbyte`  | `VT_I1`  |     | `object`  | `VT_DISPATCH` |
| `short`  | `VT_I2`  |     | `System.Runtime.InteropServices.UnknownWrapper` | `VT_UNKNOWN` |
| `ushort` | `VT_UI2` |     | `System.Runtime.InteropServices.DispatchWrapper` | `VT_DISPATCH` |
| `int`    | `VT_I4`  |     | `System.Reflection.Missing` | `VT_ERROR` |
| `uint`   | `VT_UI4` |     | `(object)null` | `VT_EMPTY` |
| `long`   | `VT_I8`  |     | `bool` | `VT_BOOL` |
| `ulong`  | `VT_UI8` |     | `System.DateTime` | `VT_DATE` |
| `float`  | `VT_R4`  |     | `decimal` | `VT_DECIMAL` |
| `double` | `VT_R8`  |     | `System.Runtime.InteropServices.CurrencyWrapper` | `VT_CURRENCY` |
| `char`   | `VT_UI2` |     | `System.DBNull` | `VT_NULL` |
| `string` | `VT_BSTR`|
