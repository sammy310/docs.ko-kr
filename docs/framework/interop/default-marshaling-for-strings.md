---
title: 문자열에 대한 기본 마샬링
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
ms.openlocfilehash: 49f2d871a42db484e20f0bfc35634a0e8b959c2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123554"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="35c61-102">문자열에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="35c61-102">Default Marshaling for Strings</span></span>

<span data-ttu-id="35c61-103"><xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스는 마샬링 동작이 서로 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>

<span data-ttu-id="35c61-104">문자열은 COM 스타일 `BSTR` 형식 또는 null로 끝나는 문자열(null 문자로 끝나는 문자 배열)로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="35c61-105">문자열 내의 문자는 유니코드(Windows 시스템에서 기본값) 또는 ANSI로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="35c61-106">인터페이스에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="35c61-106">Strings Used in Interfaces</span></span>

<span data-ttu-id="35c61-107">다음 표에서는 비관리 코드에 대한 메서드 인수로 마샬링하는 경우 문자열 데이터 형식에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-107">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="35c61-108"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 COM 인터페이스로 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-108">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>

|<span data-ttu-id="35c61-109">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="35c61-109">Enumeration type</span></span>|<span data-ttu-id="35c61-110">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="35c61-110">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="35c61-111">`UnmanagedType.BStr`(기본값)</span><span class="sxs-lookup"><span data-stu-id="35c61-111">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="35c61-112">고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-112">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|`UnmanagedType.LPStr`|<span data-ttu-id="35c61-113">null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-113">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="35c61-114">null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-114">A pointer to a null-terminated array of Unicode characters.</span></span>|

<span data-ttu-id="35c61-115">이 표는 <xref:System.String>에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-115">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="35c61-116"><xref:System.Text.StringBuilder>에 허용되는 옵션은 `UnmanagedType.LPStr` 및 `UnmanagedType.LPWStr`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-116">For <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>

<span data-ttu-id="35c61-117">다음 예제에서는 `IStringWorker` 인터페이스에서 선언된 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-117">The following example shows strings declared in the `IStringWorker` interface.</span></span>

```csharp
public interface IStringWorker
{
    void PassString1(string s);
    void PassString2([MarshalAs(UnmanagedType.BStr)] string s);
    void PassString3([MarshalAs(UnmanagedType.LPStr)] string s);
    void PassString4([MarshalAs(UnmanagedType.LPWStr)] string s);
    void PassStringRef1(ref string s);
    void PassStringRef2([MarshalAs(UnmanagedType.BStr)] ref string s);
    void PassStringRef3([MarshalAs(UnmanagedType.LPStr)] ref string s);
    void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)] ref string s);
}
```

```vb
Public Interface IStringWorker
    Sub PassString1(s As String)
    Sub PassString2(<MarshalAs(UnmanagedType.BStr)> s As String)
    Sub PassString3(<MarshalAs(UnmanagedType.LPStr)> s As String)
    Sub PassString4(<MarshalAs(UnmanagedType.LPWStr)> s As String)
    Sub PassStringRef1(ByRef s As String)
    Sub PassStringRef2(<MarshalAs(UnmanagedType.BStr)> ByRef s As String)
    Sub PassStringRef3(<MarshalAs(UnmanagedType.LPStr)> ByRef s As String)
    Sub PassStringRef4(<MarshalAs(UnmanagedType.LPWStr)> ByRef s As String)
End Interface
```

<span data-ttu-id="35c61-118">다음 예제에서는 형식 라이브러리에서 설명된 해당 인터페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-118">The following example shows the corresponding interface described in a type library.</span></span>

```cpp
interface IStringWorker : IDispatch
{
    HRESULT PassString1([in] BSTR s);
    HRESULT PassString2([in] BSTR s);
    HRESULT PassString3([in] LPStr s);
    HRESULT PassString4([in] LPWStr s);
    HRESULT PassStringRef1([in, out] BSTR *s);
    HRESULT PassStringRef2([in, out] BSTR *s);
    HRESULT PassStringRef3([in, out] LPStr *s);
    HRESULT PassStringRef4([in, out] LPWStr *s);
};
```

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="35c61-119">플랫폼 호출에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="35c61-119">Strings Used in Platform Invoke</span></span>

<span data-ttu-id="35c61-120">플랫폼 호출은 문자열 인수를 복사하고 .NET Framework 형식(유니코드)을 플랫폼 관리되지 않는 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-120">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="35c61-121">문자열을 변경할 수 없으며, 호출이 반환될 때 관리되지 않는 메모리에서 관리되는 메모리로 다시 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-121">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>

<span data-ttu-id="35c61-122">다음 표에서는 플랫폼 호출의 메서드 인수로 마샬링하는 경우 문자열에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-122">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="35c61-123"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-123">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>

|<span data-ttu-id="35c61-124">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="35c61-124">Enumeration type</span></span>|<span data-ttu-id="35c61-125">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="35c61-125">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="35c61-126">고정 길이 및 ANSI 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-126">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|
|`UnmanagedType.BStr`|<span data-ttu-id="35c61-127">고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-127">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="35c61-128">`UnmanagedType.LPStr`(기본값)</span><span class="sxs-lookup"><span data-stu-id="35c61-128">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="35c61-129">null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-129">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="35c61-130">null로 끝나는 플랫폼 종속 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-130">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="35c61-131">null로 끝나는 UTF-8 인코딩 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-131">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="35c61-132">null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-132">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.TBStr`|<span data-ttu-id="35c61-133">고정 길이 및 플랫폼 종속 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-133">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|
|`VBByRefStr`|<span data-ttu-id="35c61-134">Visual Basic .NET에서 비관리 코드의 문자열을 변경하고 결과를 관리 코드에 반영되도록 하는 데 사용할 수 있는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-134">A value that enables Visual Basic .NET to change a string in unmanaged code and have the results reflected in managed code.</span></span> <span data-ttu-id="35c61-135">이 값은 플랫폼 호출에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-135">This value is supported only for platform invoke.</span></span> <span data-ttu-id="35c61-136">Visual Basic에서 `ByVal` 문자열에 대한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-136">This is the default value in Visual Basic for `ByVal` strings.</span></span>|

<span data-ttu-id="35c61-137">이 표는 <xref:System.String>에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-137">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="35c61-138"><xref:System.Text.StringBuilder>에 허용되는 옵션은 `LPStr`, `LPTStr` 및 `LPWStr`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-138">For <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>

<span data-ttu-id="35c61-139">다음 형식 정의는 플랫폼 호출에 대한 `MarshalAsAttribute`의 올바른 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-139">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>

```csharp
class StringLibAPI
{
    [DllImport("StringLib.dll")]
    public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPWStr([MarshalAs(UnmanagedType.LPWStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPTStr([MarshalAs(UnmanagedType.LPTStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPUTF8Str([MarshalAs(UnmanagedType.LPUTF8Str)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)] string s);
}
```

```vb
Class StringLibAPI
    Public Declare Auto Sub PassLPStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPStr)> s As String)
    Public Declare Auto Sub PassLPWStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPWStr)> s As String)
    Public Declare Auto Sub PassLPTStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPTStr)> s As String)
    Public Declare Auto Sub PassLPUTF8Str Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPUTF8Str)> s As String)
    Public Declare Auto Sub PassBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.BStr)> s As String)
    Public Declare Auto Sub PassAnsiBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.AnsiBStr)> s As String)
    Public Declare Auto Sub PassTBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.TBStr)> s As String)
End Class
```

## <a name="strings-used-in-structures"></a><span data-ttu-id="35c61-140">구조체에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="35c61-140">Strings Used in Structures</span></span>

<span data-ttu-id="35c61-141">문자열은 구조체의 유효한 멤버지만 <xref:System.Text.StringBuilder> 버퍼는 구조체에서 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-141">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="35c61-142">다음 표에서는 형식을 필드로 마샬링하는 경우 <xref:System.String> 데이터 형식에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-142">The following table shows the marshaling options for the <xref:System.String> data type when the type is marshaled as a field.</span></span> <span data-ttu-id="35c61-143"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 필드로 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-143">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>

|<span data-ttu-id="35c61-144">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="35c61-144">Enumeration type</span></span>|<span data-ttu-id="35c61-145">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="35c61-145">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|<span data-ttu-id="35c61-146">고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-146">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="35c61-147">`UnmanagedType.LPStr`(기본값)</span><span class="sxs-lookup"><span data-stu-id="35c61-147">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="35c61-148">null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-148">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="35c61-149">null로 끝나는 플랫폼 종속 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-149">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="35c61-150">null로 끝나는 UTF-8 인코딩 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-150">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="35c61-151">null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-151">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.ByValTStr`|<span data-ttu-id="35c61-152">고정 길이 문자 배열입니다. 배열 형식은 포함하는 구조체의 문자 집합에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-152">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|

<span data-ttu-id="35c61-153">`ByValTStr` 형식은 구조체 내에 나타나는 인라인 고정 길이 문자 배열에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-153">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="35c61-154">다른 형식은 문자열에 대한 포인터를 포함하는 구조체 내에 포함된 문자열 참조에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-154">Other types apply to string references contained within structures that contain pointers to strings.</span></span>

<span data-ttu-id="35c61-155">포함하는 구조체에 적용된 <xref:System.Runtime.InteropServices.StructLayoutAttribute>의 `CharSet` 인수는 구조체에서 문자열의 문자 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-155">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="35c61-156">다음 구조체 예에서는 문자열 참조 및 인라인 문자열뿐 아니라 ANSI, 유니코드 및 플랫폼 종속 문자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-156">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span> <span data-ttu-id="35c61-157">형식 라이브러리에서 이러한 구조의 표현은 다음 C++ 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-157">The representation of these structures in a type library is shown in the following C++ code:</span></span>

```cpp
struct StringInfoA
{
    char *  f1;
    char    f2[256];
};

struct StringInfoW
{
    WCHAR * f1;
    WCHAR   f2[256];
    BSTR    f3;
};

struct StringInfoT
{
    TCHAR * f1;
    TCHAR   f2[256];
};
```

<span data-ttu-id="35c61-158">다음 예제에서는 <xref:System.Runtime.InteropServices.MarshalAsAttribute>를 사용하여 동일한 구조체를 다양한 형식으로 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-158">The following example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> to define the same structure in different formats.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
struct StringInfoA
{
    [MarshalAs(UnmanagedType.LPStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
struct StringInfoW
{
    [MarshalAs(UnmanagedType.LPWStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
    [MarshalAs(UnmanagedType.BStr)] public string f3;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Auto)]
struct StringInfoT
{
    [MarshalAs(UnmanagedType.LPTStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}
```

```vb
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _
Structure StringInfoA
    <MarshalAs(UnmanagedType.LPStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _
Structure StringInfoW
    <MarshalAs(UnmanagedType.LPWStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
<MarshalAs(UnmanagedType.BStr)> Public f3 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _
Structure StringInfoT
    <MarshalAs(UnmanagedType.LPTStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure
```

## <a name="fixed-length-string-buffers"></a><span data-ttu-id="35c61-159">고정 길이 문자열 버퍼</span><span class="sxs-lookup"><span data-stu-id="35c61-159">Fixed-Length String Buffers</span></span>

<span data-ttu-id="35c61-160">일부 환경에서는 고정 길이 문자 버퍼를 조작할 비관리 코드로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-160">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="35c61-161">호출 수신자는 전달된 버퍼의 내용을 수정할 수 없기 때문에 이 경우 단순히 문자열을 전달하면 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-161">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="35c61-162">문자열이 참조로 전달되는 경우 버퍼를 지정된 크기로 초기화할 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-162">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>

<span data-ttu-id="35c61-163">솔루션은 <xref:System.String> 대신 <xref:System.Text.StringBuilder> 버퍼를 인수로 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-163">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a <xref:System.String>.</span></span> <span data-ttu-id="35c61-164">`StringBuilder`의 용량을 초과하지 않는 한 호출 수신자가 `StringBuilder`를 역참조 및 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-164">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="35c61-165">고정 길이로 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-165">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="35c61-166">예를 들어 `StringBuilder` 버퍼를 `N` 용량으로 초기화하는 경우 마샬러가 (`N`+1)자 크기의 버퍼를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-166">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="35c61-167">+1은 `StringBuilder`에는 없는데 관리되지 않는 문자열에 null 종결자가 있다는 사실을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-167">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>

<span data-ttu-id="35c61-168">예를 들어, Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API 함수(*winuser.h*에 정의)에서는 호출자가 고정 길이 문자 버퍼를 함수가 창 텍스트를 쓰는 위치로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-168">For example, the Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API function (defined in *winuser.h*) requires that the caller pass a fixed-length character buffer to which the function writes the window's text.</span></span> <span data-ttu-id="35c61-169">`LpString`은 크기가 `nMaxCount`인 호출자 할당 버퍼를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-169">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="35c61-170">호출자는 버퍼를 할당하고 `nMaxCount` 인수를 할당된 버퍼 크기로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-170">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="35c61-171">다음 예제에서는 *winuser.h*에서 정의된 `GetWindowText` 함수 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-171">The following example shows the `GetWindowText` function declaration as defined in *winuser.h*.</span></span>

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

<span data-ttu-id="35c61-172">`StringBuilder`의 용량을 초과하지 않는 한 호출 수신자가 `StringBuilder`를 역참조 및 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-172">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="35c61-173">다음 코드 예제에서는 `StringBuilder`를 고정 길이로 초기화할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35c61-173">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;
using System.Text;

internal static class NativeMethods
{
    [DllImport("User32.dll")]
    internal static extern void GetWindowText(IntPtr hWnd, StringBuilder lpString, int nMaxCount);
}

public class Window
{
    internal IntPtr h;        // Internal handle to Window.
    public String GetText()
    {
        StringBuilder sb = new StringBuilder(256);
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1);
        return sb.ToString();
    }
}
```

```vb
Imports System.Text

Friend Class NativeMethods
    Friend Declare Auto Sub GetWindowText Lib "User32.dll" _
        (hWnd As IntPtr, lpString As StringBuilder, nMaxCount As Integer)
End Class

Public Class Window
    Friend h As IntPtr ' Friend handle to Window.
    Public Function GetText() As String
        Dim sb As New StringBuilder(256)
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1)
        Return sb.ToString()
   End Function
End Class
```

## <a name="see-also"></a><span data-ttu-id="35c61-174">참조</span><span class="sxs-lookup"><span data-stu-id="35c61-174">See also</span></span>

- [<span data-ttu-id="35c61-175">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="35c61-175">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="35c61-176">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="35c61-176">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="35c61-177">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="35c61-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="35c61-178">[방향 특성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="35c61-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="35c61-179">복사 및 고정</span><span class="sxs-lookup"><span data-stu-id="35c61-179">Copying and Pinning</span></span>](copying-and-pinning.md)
