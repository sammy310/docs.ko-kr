---
title: 문자 집합 지정
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
ms.openlocfilehash: 0db1cd8d75b45f6d718168793c873e5867028269
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125168"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="245f6-102">문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="245f6-102">Specifying a Character Set</span></span>
<span data-ttu-id="245f6-103"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 문자열 마샬링을 제어하고 플랫폼 호출이 DLL에서 함수 이름을 찾는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="245f6-104">이 항목에서는 두 동작에 대해 모두 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="245f6-105">일부 API는 문자열 인수를 사용하는 함수의 두 가지 버전인 narrow(ANSI) 및 wide(Unicode)를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="245f6-106">예를 들어 Windows API에는 **MessageBox** 함수에 대한 다음 진입점 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-106">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
- <span data-ttu-id="245f6-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="245f6-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="245f6-108">진입점 이름에 “A”를 추가하여 구분되는 1바이트 문자 ANSI 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="245f6-109">**MessageBoxA** 호출은 항상 문자열을 ANSI 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-109">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
- <span data-ttu-id="245f6-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="245f6-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="245f6-111">진입점 이름에 “W”를 추가하여 구분되는 2바이트 문자 유니코드 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="245f6-112">**MessageBoxW** 호출은 항상 문자열을 유니코드 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-112">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="245f6-113">문자열 마샬링 및 이름 일치</span><span class="sxs-lookup"><span data-stu-id="245f6-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="245f6-114">`CharSet` 필드는 다음 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-114">The `CharSet` field accepts the following values:</span></span>  
  
 <span data-ttu-id="245f6-115"><xref:System.Runtime.InteropServices.CharSet.Ansi>(기본값)</span><span class="sxs-lookup"><span data-stu-id="245f6-115"><xref:System.Runtime.InteropServices.CharSet.Ansi> (default value)</span></span>  
  
- <span data-ttu-id="245f6-116">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="245f6-116">String marshaling</span></span>  
  
     <span data-ttu-id="245f6-117">플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 ANSI 형식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
- <span data-ttu-id="245f6-118">이름 일치</span><span class="sxs-lookup"><span data-stu-id="245f6-118">Name matching</span></span>  
  
     <span data-ttu-id="245f6-119"><xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> 필드가 Visual Basic의 기본값인 `true`이면 플랫폼 호출이 지정한 이름만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="245f6-120">예를 들어 **MessageBox**를 지정하는 경우 플랫폼 호출은 **MessageBox**를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="245f6-121">`ExactSpelling` 필드가 C++ 및 C#의 기본값인 `false`이면 플랫폼 호출은 올바른 별칭(**MessageBox**)을 먼저 검색한 다음, 올바른 별칭을 찾을 수 없는 경우 잘못된 이름(**MessageBoxA**)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-121">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="245f6-122">ANSI 이름 일치 동작은 유니코드 이름 일치 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- <span data-ttu-id="245f6-123">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="245f6-123">String marshaling</span></span>  
  
     <span data-ttu-id="245f6-124">플랫폼 호출은 관리되는 형식(유니코드)의 문자열을 유니코드 형식으로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-124">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
- <span data-ttu-id="245f6-125">이름 일치</span><span class="sxs-lookup"><span data-stu-id="245f6-125">Name matching</span></span>  
  
     <span data-ttu-id="245f6-126">`ExactSpelling` 필드가 Visual Basic의 기본값인 `true`이면 플랫폼 호출이 지정한 이름만 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-126">When the `ExactSpelling` field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="245f6-127">예를 들어 **MessageBox**를 지정하는 경우 플랫폼 호출은 **MessageBox**를 검색하고, 정확한 철자를 찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-127">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="245f6-128">`ExactSpelling` 필드가 C++ 및 C#의 기본값인 `false`이면 플랫폼 호출은 잘못된 이름(**MessageBoxW**)을 먼저 검색한 다음, 잘못된 이름을 찾을 수 없는 경우 올바른 별칭(**MessageBox**)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-128">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="245f6-129">유니코드 이름 일치 동작은 ANSI 이름 일치 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-129">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- <span data-ttu-id="245f6-130">플랫폼 호출이 대상 플랫폼에 따라 런타임에 ANSI와 유니코드 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-130">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="245f6-131">Visual Basic에서 문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="245f6-131">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="245f6-132">다음 예제에서는 매번 서로 다른 문자 집합 동작을 사용하여 **MessageBox** 함수를 세 번 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-132">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="245f6-133">**Ansi**, **유니코드** 또는 **자동** 키워드를 선언문에 추가하여 Visual Basic에서 문자 집합 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-133">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="245f6-134">첫 번째 선언문과 같이 문자 집합 키워드를 생략하면 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본적으로 ANSI 문자 집합으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-134">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="245f6-135">예제에서 두 번째 문과 세 번째 문은 키워드를 사용해서 명시적으로 문자 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-135">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
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
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="245f6-136">C# 및 C++에서 문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="245f6-136">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="245f6-137"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드는 기본 문자 집합을 ANSI 또는 유니코드로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-137">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="245f6-138">문자 집합은 메서드에 대한 문자열 인수를 마샬링하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-138">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="245f6-139">다음 형식 중 하나를 사용하여 문자 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-139">Use one of the following forms to indicate the character set:</span></span>  
  
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
  
 <span data-ttu-id="245f6-140">다음 예제에서는 문자 집합을 지정하는 **MessageBox** 함수의 세 가지 관리되는 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-140">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="245f6-141">첫 번째 정의에서는 생략에 의해 `CharSet` 필드가 기본값인 ANSI 문자 집합으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="245f6-141">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="245f6-142">참조</span><span class="sxs-lookup"><span data-stu-id="245f6-142">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="245f6-143">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="245f6-143">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="245f6-144">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="245f6-144">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="245f6-145">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="245f6-145">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
