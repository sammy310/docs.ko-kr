---
title: ICorDebugStackWalk::GetContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 700e0af05828b9fe0a50c1aac114e840adc276b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131843"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="1d528-102">ICorDebugStackWalk::GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="1d528-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="1d528-103">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 개체의 현재 프레임에 대 한 컨텍스트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d528-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d528-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d528-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d528-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="1d528-106">진행 WinNT에 정의 된 컨텍스트 버퍼의 요청 된 콘텐츠를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="1d528-107">진행 할당 된 컨텍스트 버퍼 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="1d528-108">제한이 컨텍스트의 실제 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-108">[out] The actual size of the context.</span></span> <span data-ttu-id="1d528-109">이 값은 컨텍스트 버퍼의 크기 보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="1d528-110">제한이 컨텍스트 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d528-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="1d528-111">Return Value</span></span>  
 <span data-ttu-id="1d528-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1d528-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d528-113">HRESULT</span></span>|<span data-ttu-id="1d528-114">설명</span><span class="sxs-lookup"><span data-stu-id="1d528-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d528-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d528-115">S_OK</span></span>|<span data-ttu-id="1d528-116">현재 프레임에 대 한 컨텍스트가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="1d528-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d528-117">E_FAIL</span></span>|<span data-ttu-id="1d528-118">컨텍스트를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="1d528-119">HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="1d528-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="1d528-120">컨텍스트 버퍼가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="1d528-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="1d528-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="1d528-122">프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="1d528-123">예외</span><span class="sxs-lookup"><span data-stu-id="1d528-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d528-124">주의</span><span class="sxs-lookup"><span data-stu-id="1d528-124">Remarks</span></span>  
 <span data-ttu-id="1d528-125">해제 하면 비휘발성 레지스터와 같이 레지스터의 하위 집합만 복원 되므로 컨텍스트는 호출 시 등록 상태와 정확 하 게 일치 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d528-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d528-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d528-126">Requirements</span></span>  
 <span data-ttu-id="1d528-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d528-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d528-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d528-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d528-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d528-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d528-130">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d528-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d528-131">참조</span><span class="sxs-lookup"><span data-stu-id="1d528-131">See also</span></span>

- [<span data-ttu-id="1d528-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d528-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1d528-133">디버깅</span><span class="sxs-lookup"><span data-stu-id="1d528-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
