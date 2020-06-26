---
title: JIT 연결 디버깅 설정
description: 오류가 발생할 때 디버거를 프로세스에 연결 하려면 JIT (just-in-time) 연결 디버깅을 사용 하도록 설정 합니다. 특정 메서드나 함수에 의해 트리거될 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
ms.openlocfilehash: d1190c51a9cc6b5322ec832e0d35bc01dc855b12
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416046"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="2fc76-104">JIT 연결 디버깅 설정</span><span class="sxs-lookup"><span data-stu-id="2fc76-104">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="2fc76-105">오류가 발생한 경우 JIT 연결 디버깅은 디버거를 프로세스에 연결하는 방법을 설명하는 데 사용되는 구문이고, 오류가 발생하지 않은 경우 특정 메서드 또는 함수에 의해 트리거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-105">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="2fc76-106">JIT 연결 디버깅은 다음 오류 조건에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-106">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="2fc76-107">처리되지 않은 예외(네이티브 및 관리 코드에서 둘 다).</span><span class="sxs-lookup"><span data-stu-id="2fc76-107">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="2fc76-108"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> 메서드 또는 [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) 함수(Windows 7 제품군).</span><span class="sxs-lookup"><span data-stu-id="2fc76-108"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="2fc76-109">런타임 오류.</span><span class="sxs-lookup"><span data-stu-id="2fc76-109">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="2fc76-110">JIT 연결 디버깅은 다음 메서드 및 함수에 대한 호출에 의해서도 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-110">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="2fc76-111"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-111"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="2fc76-112"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-112"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="2fc76-113">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) 함수(Win32).</span><span class="sxs-lookup"><span data-stu-id="2fc76-113">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) function (Win32).</span></span>  
  
 <span data-ttu-id="2fc76-114">.NET Framework 4 이전에는 .NET Framework 네이티브 및 관리 되는 디버거의 동작을 제어 하기 위해 별도의 레지스트리 키를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-114">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="2fc76-115">.NET Framework 4부터 컨트롤은 단일 레지스트리 키 (HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.에 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-115">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="2fc76-116">해당 키에 대해 설정할 수 있는 값에 따라 디버거 호출 여부가 결정되고 디버거가 호출되는 경우 사용자 조작이 필요한 대화 상자와 함께 호출되는지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc76-116">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="2fc76-117">이 레지스트리 키를 설정 하는 방법에 대 한 자세한 내용은 [자동 디버깅 구성](/windows/win32/debug/configuring-automatic-debugging)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fc76-117">For information about setting this registry key, see [Configuring Automatic Debugging](/windows/win32/debug/configuring-automatic-debugging).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc76-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2fc76-118">See also</span></span>

- [<span data-ttu-id="2fc76-119">디버깅, 추적 및 프로파일링</span><span class="sxs-lookup"><span data-stu-id="2fc76-119">Debugging, Tracing, and Profiling</span></span>](index.md)
- [<span data-ttu-id="2fc76-120">쉽게 디버깅할 수 있도록 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="2fc76-120">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)
