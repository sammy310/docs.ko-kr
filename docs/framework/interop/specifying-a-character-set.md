---
title: 문자 집합 지정
description: 좁은 인코딩(ANSI) 또는 와이드 인코딩(유니코드)을 사용하는 문자 집합을 지정하는 방법을 알아봅니다. 또는 자동 런타임 선택 영역을 지정할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
ms.openlocfilehash: 8cc4198d6c13d4705ffc5ce5229cce7a205aec8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278182"
---
# <a name="specify-a-character-set"></a><span data-ttu-id="cc084-104">문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="cc084-104">Specify a character set</span></span>

<span data-ttu-id="cc084-105"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 문자열 마샬링을 제어하고 플랫폼 호출이 DLL에서 함수 이름을 찾는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-105">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="cc084-106">이 항목에서는 두 동작에 대해 모두 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-106">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="cc084-107">일부 API는 문자열 인수를 사용하는 함수의 두 가지 버전인 narrow(ANSI) 및 wide(Unicode)를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-107">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="cc084-108">예를 들어 Windows API에는 **MessageBox** 함수에 대한 다음 진입점 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-108">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
- <span data-ttu-id="cc084-109">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="cc084-109">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="cc084-110">진입점 이름에 “A”를 추가하여 구분되는 1바이트 문자 ANSI 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-110">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="cc084-111">**MessageBoxA** 호출은 항상 문자열을 ANSI 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-111">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
- <span data-ttu-id="cc084-112">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="cc084-112">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="cc084-113">진입점 이름에 “W”를 추가하여 구분되는 2바이트 문자 유니코드 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-113">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="cc084-114">**MessageBoxW** 호출은 항상 문자열을 유니코드 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-114">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="cc084-115">문자열 마샬링 및 이름 일치</span><span class="sxs-lookup"><span data-stu-id="cc084-115">String Marshaling and Name Matching</span></span>  

 <span data-ttu-id="cc084-116">`CharSet` 필드는 다음 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-116">The `CharSet` field accepts the following values:</span></span>  
  
 <span data-ttu-id="cc084-117"><xref:System.Runtime.InteropServices.CharSet.Ansi>(기본값)</span><span class="sxs-lookup"><span data-stu-id="cc084-117"><xref:System.Runtime.InteropServices.CharSet.Ansi> (default value)</span></span>  
  
- <span data-ttu-id="cc084-118">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="cc084-118">String marshaling</span></span>  
  
     <span data-ttu-id="cc084-119">플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 ANSI 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-119">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
- <span data-ttu-id="cc084-120">이름 일치</span><span class="sxs-lookup"><span data-stu-id="cc084-120">Name matching</span></span>  
  
     <span data-ttu-id="cc084-121"><xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> 필드가 Visual Basic의 기본값인 `true`이면 플랫폼 호출이 지정한 이름만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-121">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="cc084-122">예를 들어 **MessageBox** 를 지정하는 경우 플랫폼 호출은 **MessageBox** 를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-122">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="cc084-123">`ExactSpelling` 필드가 C++ 및 C#의 기본값인 `false`이면 플랫폼 호출은 올바른 별칭(**MessageBox**)을 먼저 검색한 다음, 올바른 별칭을 찾을 수 없는 경우 잘못된 이름(**MessageBoxA**)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-123">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="cc084-124">ANSI 이름 일치 동작은 유니코드 이름 일치 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-124">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- <span data-ttu-id="cc084-125">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="cc084-125">String marshaling</span></span>  
  
     <span data-ttu-id="cc084-126">플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 유니코드 형식으로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-126">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
- <span data-ttu-id="cc084-127">이름 일치</span><span class="sxs-lookup"><span data-stu-id="cc084-127">Name matching</span></span>  
  
     <span data-ttu-id="cc084-128">`ExactSpelling` 필드가 Visual Basic의 기본값인 `true`이면 플랫폼 호출이 지정한 이름만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-128">When the `ExactSpelling` field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="cc084-129">예를 들어 **MessageBox** 를 지정하는 경우 플랫폼 호출은 **MessageBox** 를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-129">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="cc084-130">`ExactSpelling` 필드가 C++ 및 C#의 기본값인 `false`이면 플랫폼 호출은 잘못된 이름(**MessageBoxW**)을 먼저 검색한 다음, 잘못된 이름을 찾을 수 없는 경우 올바른 별칭(**MessageBox**)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-130">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="cc084-131">유니코드 이름 일치 동작은 ANSI 이름 일치 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-131">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- <span data-ttu-id="cc084-132">플랫폼 호출이 대상 플랫폼에 따라 런타임에 ANSI와 유니코드 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-132">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specify-a-character-set-in-visual-basic"></a><span data-ttu-id="cc084-133">Visual Basic에서 문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="cc084-133">Specify a character set in Visual Basic</span></span>

<span data-ttu-id="cc084-134">`Ansi`, `Unicode` 또는 `Auto` 키워드를 선언문에 추가하여 Visual Basic에서 문자 집합 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-134">You can specify character-set behavior in Visual Basic by adding the `Ansi`, `Unicode`, or `Auto` keyword to the declaration statement.</span></span> <span data-ttu-id="cc084-135">문자 집합 키워드를 생략하면 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본적으로 ANSI 문자 집합으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-135">If you omit the character-set keyword, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span>

<span data-ttu-id="cc084-136">다음 예제에서는 매번 서로 다른 문자 집합 동작을 사용하여 **MessageBox** 함수를 세 번 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-136">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="cc084-137">첫 번째 문은 문자 집합 키워드를 생략하므로 문자 집합이 기본적으로 ANSI로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-137">The first statement omits the character-set keyword, so the character set defaults to ANSI.</span></span> <span data-ttu-id="cc084-138">두 번째 문과 세 번째 문은 키워드를 사용해서 명시적으로 문자 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-138">The second and third statements explicitly specify a character set with a keyword.</span></span>

```vb
Friend Class NativeMethods
    Friend Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specify-a-character-set-in-c-and-c"></a><span data-ttu-id="cc084-139">C# 및 C++에서 문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="cc084-139">Specify a character set in C# and C++</span></span>

<span data-ttu-id="cc084-140"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본 문자 집합을 ANSI 또는 유니코드로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-140">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="cc084-141">문자 집합은 메서드에 대한 문자열 인수를 마샬링하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-141">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="cc084-142">다음 형식 중 하나를 사용하여 문자 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-142">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp
[DllImport("DllName", CharSet = CharSet.Ansi)]
[DllImport("DllName", CharSet = CharSet.Unicode)]
[DllImport("DllName", CharSet = CharSet.Auto)]
```
  
```cpp
[DllImport("DllName", CharSet = CharSet::Ansi)]
[DllImport("DllName", CharSet = CharSet::Unicode)]
[DllImport("DllName", CharSet = CharSet::Auto)]
```
  
 <span data-ttu-id="cc084-143">다음 예제에서는 문자 집합을 지정하는 **MessageBox** 함수의 세 가지 관리되는 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-143">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="cc084-144">첫 번째 정의에서는 생략에 의해 `CharSet` 필드가 기본값인 ANSI 문자 집합으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc084-144">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll")]
    internal static extern int MessageBoxA(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    internal static extern int MessageBoxW(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Auto)]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```  
  
```cpp
typedef void* HWND;

// Can use MessageBox or MessageBoxA.
[DllImport("user32")]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Can use MessageBox or MessageBoxW.
[DllImport("user32", CharSet = CharSet::Unicode)]
extern "C" int MessageBoxW(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Must use MessageBox.
[DllImport("user32", CharSet = CharSet::Auto)]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="cc084-145">참조</span><span class="sxs-lookup"><span data-stu-id="cc084-145">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="cc084-146">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="cc084-146">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="cc084-147">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="cc084-147">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="cc084-148">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="cc084-148">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
