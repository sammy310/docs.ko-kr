---
title: 예외 상호 운용성
ms.date: 01/16/2020
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: db7c9943c298607aa91a4bd08ddc12bbafc872be
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830625"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="a1310-102">비관리 코드에서 Interop 예외 사용</span><span class="sxs-lookup"><span data-stu-id="a1310-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="a1310-103">비관리 코드 예외 Interop은 Windows 플랫폼에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1310-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="a1310-104">Windows 이외의 플랫폼에서는 이식성 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a1310-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="a1310-105">Unix ABI에는 예외 처리에 대한 정의가 없으므로 관리 코드는 내부적으로 예외 메커니즘이 작동하는 방식을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1310-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="a1310-106">따라서 예외가 발생하여 예기치 않은 동작과 크래시로 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1310-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="a1310-107">Setjmp/Longjmp 동작</span><span class="sxs-lookup"><span data-stu-id="a1310-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="a1310-108">`setjmp` 및 `longjmp` C 함수를 사용하는 Interop은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1310-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="a1310-109">`longjmp`를 사용하여 관리되는 프레임을 건너뛸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1310-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="a1310-110">자세한 내용은 [longjmp 설명서](/cpp/c-runtime-library/reference/longjmp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1310-110">For more information, see [longjmp documentation](/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1310-111">참조</span><span class="sxs-lookup"><span data-stu-id="a1310-111">See also</span></span>

- [<span data-ttu-id="a1310-112">예외</span><span class="sxs-lookup"><span data-stu-id="a1310-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="a1310-113">네이티브 라이브러리와의 Interop</span><span class="sxs-lookup"><span data-stu-id="a1310-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
