---
title: 진입점 지정
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a5449b4fa77ba99a18595077081089e80bd32df
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833612"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="53596-102">진입점 지정</span><span class="sxs-lookup"><span data-stu-id="53596-102">Specifying an Entry Point</span></span>

<span data-ttu-id="53596-103">진입점은 DLL에서 함수의 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="53596-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="53596-104">관리되는 프로젝트 내에서 대상 함수의 원래 이름이나 서수 진입점은 상호 운용 경계 간에 해당 함수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="53596-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="53596-105">또한 진입점을 다른 이름에 매핑하여 효과적으로 함수 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53596-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="53596-106">다음은 DLL 함수의 이름을 바꾸는 가능한 원인 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="53596-106">The following is a list of possible reasons to rename a DLL function:</span></span>  
  
- <span data-ttu-id="53596-107">대/소문자를 구분하는 API 함수 이름을 사용하지 않도록 하기 위해</span><span class="sxs-lookup"><span data-stu-id="53596-107">To avoid using case-sensitive API function names</span></span>  
  
- <span data-ttu-id="53596-108">기존 명명 표준을 준수하기 위해</span><span class="sxs-lookup"><span data-stu-id="53596-108">To comply with existing naming standards</span></span>  
  
- <span data-ttu-id="53596-109">동일한 DLL 함수의 여러 버전을 선언하여 다른 데이터 형식을 사용하는 함수를 수용하기 위해</span><span class="sxs-lookup"><span data-stu-id="53596-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
- <span data-ttu-id="53596-110">ANSI 및 유니코드 버전을 포함하는 API 사용을 간소화하기 위해</span><span class="sxs-lookup"><span data-stu-id="53596-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="53596-111">이 항목에는 관리 코드에서 DLL 함수 이름을 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53596-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="53596-112">Visual Basic에서 함수 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="53596-112">Renaming a Function in Visual Basic</span></span>  
 
<span data-ttu-id="53596-113">Visual Basic에서는 **Declare** 문에 **Function** 키워드를 사용하여 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> 필드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="53596-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="53596-114">다음 예제에서는 기본 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53596-114">The following example shows a basic declaration.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
<span data-ttu-id="53596-115">다음 예제와 같이 정의에 **Alias** 키워드를 포함하여 **MessageBox** 진입점을 **MsgBox**로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53596-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="53596-116">두 예제에서 모두 **Auto** 키워드를 사용하면 진입점의 문자 집합 버전을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53596-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="53596-117">문자 집합을 선택하는 방법에 대한 자세한 내용은 [문자 집합 지정](specifying-a-character-set.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53596-117">For more information about selecting a character set, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="53596-118">C# 및 C++에서 함수 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="53596-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="53596-119"><xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> 필드를 사용하여 DLL 함수를 이름 또는 서수로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53596-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="53596-120">메서드 정의의 함수 이름이 DLL의 진입점과 같으면 **EntryPoint** 필드를 사용하여 함수를 명시적으로 식별할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53596-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="53596-121">그러지 않으면 다음 특성 형식 중 하나를 사용하여 이름 또는 서수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53596-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 <span data-ttu-id="53596-122">서수 앞에 파운드 기호(#)를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53596-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="53596-123">다음 예제에서는 **EntryPoint** 필드를 사용하여 코드에서 **MessageBoxA**를 **MsgBox**로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53596-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="53596-124">참조</span><span class="sxs-lookup"><span data-stu-id="53596-124">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="53596-125">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="53596-125">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="53596-126">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="53596-126">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="53596-127">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="53596-127">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
