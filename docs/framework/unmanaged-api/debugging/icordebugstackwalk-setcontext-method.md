---
description: '자세히 알아보기: ICorDebugStackWalk:: SetContext 메서드'
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
ms.openlocfilehash: 20e18460d237a63e4c2695b9e7cbfa766ed3908f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794717"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="9da32-103">ICorDebugStackWalk::SetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="9da32-103">ICorDebugStackWalk::SetContext Method</span></span>

<span data-ttu-id="9da32-104">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 현재 컨텍스트를 스레드의 올바른 컨텍스트로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-104">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da32-105">구문</span><span class="sxs-lookup"><span data-stu-id="9da32-105">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9da32-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9da32-106">Parameters</span></span>  

 `flag`  
 <span data-ttu-id="9da32-107">진행 컨텍스트가 스택의 활성 프레임에서 온 것인지 아니면 스택을 해제 하 여 얻은 컨텍스트를 가져왔는지 나타내는 [Cordebugsetcontextflag](cordebugsetcontextflag-enumeration.md) 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-107">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="9da32-108">진행 할당 된 `CONTEXT` 버퍼 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-108">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="9da32-109">진행 `CONTEXT` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-109">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9da32-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="9da32-110">Return Value</span></span>  

 <span data-ttu-id="9da32-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9da32-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9da32-112">HRESULT</span></span>|<span data-ttu-id="9da32-113">설명</span><span class="sxs-lookup"><span data-stu-id="9da32-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9da32-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9da32-114">S_OK</span></span>|<span data-ttu-id="9da32-115">`ICorDebugStackWalk`개체의 컨텍스트가 성공적으로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-115">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="9da32-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9da32-116">E_FAIL</span></span>|<span data-ttu-id="9da32-117">`ICorDebugStackWalk`개체의 컨텍스트가 설정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-117">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="9da32-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9da32-118">E_INVALIDARG</span></span>|<span data-ttu-id="9da32-119">컨텍스트가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="9da32-119">The context is null.</span></span>|  
|<span data-ttu-id="9da32-120">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="9da32-120">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="9da32-121">컨텍스트 버퍼가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-121">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9da32-122">예외</span><span class="sxs-lookup"><span data-stu-id="9da32-122">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9da32-123">설명</span><span class="sxs-lookup"><span data-stu-id="9da32-123">Remarks</span></span>  

 <span data-ttu-id="9da32-124">이 메서드는 스레드의 현재 컨텍스트를 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-124">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="9da32-125">현재 컨텍스트를 잘못 된 컨텍스트로 설정 하면 stack walker에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-125">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="9da32-126">[ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) 메서드를 즉시 호출 하 여이 컨텍스트의 정확한 비트 복사를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9da32-126">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da32-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9da32-127">Requirements</span></span>  

 <span data-ttu-id="9da32-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9da32-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da32-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9da32-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9da32-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9da32-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9da32-131">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9da32-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da32-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9da32-132">See also</span></span>

- [<span data-ttu-id="9da32-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9da32-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9da32-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="9da32-134">Debugging</span></span>](index.md)
