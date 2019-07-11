---
title: ICorDebugStackWalk::SetContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6eb97fc70fec25f4b225c3fd5bad1e780091f7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771042"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="60202-102">ICorDebugStackWalk::SetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="60202-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="60202-103">집합의 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 스레드에 대 한 올바른 컨텍스트 개체의 현재 컨텍스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60202-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60202-104">구문</span><span class="sxs-lookup"><span data-stu-id="60202-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60202-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60202-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="60202-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) 컨텍스트가 스택의 활성 프레임에서 또는 컨텍스트 스택을 해제 하 여 얻은 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="60202-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="60202-107">[in] 할당 된 크기는 `CONTEXT` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="60202-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="60202-108">[in] `CONTEXT` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="60202-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60202-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="60202-109">Return Value</span></span>  
 <span data-ttu-id="60202-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60202-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="60202-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60202-111">HRESULT</span></span>|<span data-ttu-id="60202-112">설명</span><span class="sxs-lookup"><span data-stu-id="60202-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60202-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="60202-113">S_OK</span></span>|<span data-ttu-id="60202-114">`ICorDebugStackWalk` 개체의 컨텍스트를 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="60202-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="60202-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60202-115">E_FAIL</span></span>|<span data-ttu-id="60202-116">`ICorDebugStackWalk` 개체의 컨텍스트가 설정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="60202-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="60202-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="60202-117">E_INVALIDARG</span></span>|<span data-ttu-id="60202-118">컨텍스트가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="60202-118">The context is null.</span></span>|  
|<span data-ttu-id="60202-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="60202-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="60202-120">상황에 맞는 버퍼가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="60202-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="60202-121">예외</span><span class="sxs-lookup"><span data-stu-id="60202-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60202-122">설명</span><span class="sxs-lookup"><span data-stu-id="60202-122">Remarks</span></span>  
 <span data-ttu-id="60202-123">이 메서드는 스레드의 현재 컨텍스트를 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60202-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="60202-124">잘못 된 컨텍스트에 현재 컨텍스트를 설정 합니다. 스택 워크에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60202-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="60202-125">이 컨텍스트에서의 정확한 비트 복사본을 즉시 호출 하 여 검색할 수 있습니다 합니다 [icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="60202-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60202-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60202-126">Requirements</span></span>  
 <span data-ttu-id="60202-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="60202-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60202-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60202-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60202-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60202-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60202-130">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60202-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60202-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="60202-131">See also</span></span>

- [<span data-ttu-id="60202-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60202-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="60202-133">디버깅</span><span class="sxs-lookup"><span data-stu-id="60202-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
