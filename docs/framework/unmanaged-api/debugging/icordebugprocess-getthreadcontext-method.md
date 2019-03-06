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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d54becc2d7cd4359c78415f25f579b968cb3f4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482342"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="78600-102">ICorDebugProcess::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="78600-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="78600-103">이 프로세스에서 지정 된 스레드에 대 한 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="78600-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78600-104">구문</span><span class="sxs-lookup"><span data-stu-id="78600-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78600-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78600-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="78600-106">[in] 컨텍스트를 검색 하려는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="78600-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="78600-107">[in] `context` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="78600-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="78600-108">[out에서] 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="78600-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="78600-109">컨텍스트는 스레드가 실행 중인 프로세서의 아키텍처를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78600-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78600-110">설명</span><span class="sxs-lookup"><span data-stu-id="78600-110">Remarks</span></span>  
 <span data-ttu-id="78600-111">디버거에서 Win32 대신이 메서드를 호출 해야 `GetThreadContext` 메서드는 해당 컨텍스트가 일시적으로 변경 된 "도용" 상태의 스레드가 실제로 수 있으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="78600-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="78600-112">스레드는 네이티브 코드의 경우에이 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78600-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="78600-113">사용 하 여 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 스레드에 관리 코드에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="78600-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="78600-114">반환 되는 데이터에는 현재 플랫폼에 대 한 상황에 맞는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="78600-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="78600-115">Win32의 경우와 마찬가지로 `GetThreadContext` 메서드를 호출자에 게 초기화 해야 합니다 `context` 이 메서드를 호출 하기 전에 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="78600-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78600-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78600-116">Requirements</span></span>  
 <span data-ttu-id="78600-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="78600-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78600-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78600-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78600-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78600-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78600-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78600-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
