---
title: 외부 함수
description: 알아봅니다는 F# 네이티브 코드의 함수를 호출 하는 것에 대 한 언어 지원 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 73e38d8942bfc8ddb3c51d126d7678e84903326b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642058"
---
# <a name="external-functions"></a><span data-ttu-id="7969e-103">외부 함수</span><span class="sxs-lookup"><span data-stu-id="7969e-103">External Functions</span></span>

<span data-ttu-id="7969e-104">설명 F# 네이티브 코드의 함수를 호출 하는 것에 대 한 언어 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="7969e-105">구문</span><span class="sxs-lookup"><span data-stu-id="7969e-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="7969e-106">설명</span><span class="sxs-lookup"><span data-stu-id="7969e-106">Remarks</span></span>

<span data-ttu-id="7969e-107">이전 구문에서 *인수* 에 제공 되는 인수를 나타내는 `System.Runtime.InteropServices.DllImportAttribute` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="7969e-108">첫 번째 인수는.dll 확장명 없이이 함수를 포함 하는 DLL의 이름을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="7969e-109">공용 속성에 대 한 추가 인수를 제공할 수 있습니다는 `System.Runtime.InteropServices.DllImportAttribute` 호출 규칙 같은 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="7969e-110">것을 전제로 네이티브 C++ 다음 내보낸된 함수를 포함 하는 DLL입니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="7969e-111">이 함수를 호출할 수 있습니다 F# 다음 코드를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="7969e-112">네이티브 코드와의 상호 운용성 이라고 *플랫폼 호출* 이며 CLR의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="7969e-113">자세한 내용은 [비관리 코드 상호 운용](../../../../docs/framework/interop/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7969e-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="7969e-114">이 섹션의 정보에 적용 됩니다 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="7969e-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="7969e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="7969e-115">See also</span></span>

- [<span data-ttu-id="7969e-116">함수</span><span class="sxs-lookup"><span data-stu-id="7969e-116">Functions</span></span>](index.md)
