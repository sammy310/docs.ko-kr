---
title: ICorDebugProcess::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: 41c5116d23655730f3586dc656aa69c8ae817b6c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792619"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="f2f21-102">ICorDebugProcess::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="f2f21-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="f2f21-103">이 프로세스의 지정 된 스레드에 대 한 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f21-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2f21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2f21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2f21-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="f2f21-106">진행 컨텍스트를 검색할 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f2f21-107">[in] `context` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="f2f21-108">[in, out] 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="f2f21-109">컨텍스트는 스레드가 실행 되는 프로세서의 아키텍처를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2f21-110">주의</span><span class="sxs-lookup"><span data-stu-id="f2f21-110">Remarks</span></span>  
 <span data-ttu-id="f2f21-111">스레드가 실제로 해당 컨텍스트가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 `GetThreadContext` 메서드 대신이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="f2f21-112">이 메서드는 스레드가 네이티브 코드에 있는 경우에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="f2f21-113">관리 코드에서 스레드에 대해 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="f2f21-114">반환 된 데이터는 현재 플랫폼에 대 한 컨텍스트 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="f2f21-115">Win32 `GetThreadContext` 메서드와 마찬가지로 호출자는이 메서드를 호출 하기 전에 `context` 매개 변수를 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f21-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f21-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2f21-116">Requirements</span></span>  
 <span data-ttu-id="f2f21-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2f21-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2f21-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2f21-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2f21-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2f21-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2f21-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f21-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
