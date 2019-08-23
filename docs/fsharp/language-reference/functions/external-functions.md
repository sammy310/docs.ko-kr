---
title: 외부 함수
description: 네이티브 코드에서 F# 함수를 호출 하는 언어 지원에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 3c8edaba25e07b6ca2c44a58c4b55dc98a13b4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968723"
---
# <a name="external-functions"></a><span data-ttu-id="2f753-103">외부 함수</span><span class="sxs-lookup"><span data-stu-id="2f753-103">External Functions</span></span>

<span data-ttu-id="2f753-104">이 항목에서는 F# 네이티브 코드에서 함수를 호출 하는 언어 지원에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f753-105">구문</span><span class="sxs-lookup"><span data-stu-id="2f753-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="2f753-106">설명</span><span class="sxs-lookup"><span data-stu-id="2f753-106">Remarks</span></span>

<span data-ttu-id="2f753-107">이전 구문에서 *인수* 는 `System.Runtime.InteropServices.DllImportAttribute` 특성에 제공 되는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="2f753-108">첫 번째 인수는이 함수가 포함 된 DLL의 이름을 나타내는 문자열이 며 .dll 확장명은 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="2f753-109">`System.Runtime.InteropServices.DllImportAttribute` 클래스의 public 속성 (예: 호출 규칙)에 대 한 추가 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="2f753-110">다음 내보낸 함수를 포함 C++ 하는 네이티브 DLL이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="2f753-111">다음 코드를 사용 하 여 F# 에서이 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="2f753-112">네이티브 코드와의 상호 운용성은 *플랫폼 호출* 이라고 하며 CLR의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="2f753-113">자세한 내용은 [비관리 코드 상호 운용](../../../framework/interop/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f753-113">For more information, see [Interoperating with Unmanaged Code](../../../framework/interop/index.md).</span></span> <span data-ttu-id="2f753-114">해당 섹션의 정보는에 F#적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f753-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f753-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f753-115">See also</span></span>

- [<span data-ttu-id="2f753-116">함수</span><span class="sxs-lookup"><span data-stu-id="2f753-116">Functions</span></span>](index.md)
