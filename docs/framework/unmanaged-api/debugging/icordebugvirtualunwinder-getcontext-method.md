---
title: ICorDebugVirtualUnwinder::GetContext 메서드
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: a5a1afa47e52eff7c930698a3354a03d8c62259f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679457"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="2637a-102">ICorDebugVirtualUnwinder::GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="2637a-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>

<span data-ttu-id="2637a-103">이 해제기의 현재 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2637a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2637a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2637a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2637a-105">Parameters</span></span>  

 `contextFlags`  
 <span data-ttu-id="2637a-106">[in] WinNT.h에 정의된 반환할 컨텍스트 부분을 지정하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="2637a-107">[in] `contextBuf`의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="2637a-108">[out] 실제로 `contextBuf`에 기록되는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="2637a-109">[out] 이 해제기의 현재 컨텍스트를 포함하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2637a-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2637a-110">Return Value</span></span>  

 <span data-ttu-id="2637a-111">mscordbi에 수신되는 모든 오류 HRESULT는 심각한 오류로 간주하여 ICorDebug API에서 `CORDBG_E_DATA_TARGET_ERROR`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2637a-112">설명</span><span class="sxs-lookup"><span data-stu-id="2637a-112">Remarks</span></span>  

 <span data-ttu-id="2637a-113">인수의 초기 값을 `contextBuf` [ICorDebugStackWalk:: getcontext](icordebugstackwalk-getcontext-method.md) 메서드를 호출 하 여 반환 되는 컨텍스트 버퍼로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2637a-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="2637a-115">해제하면 레지스터 하위 집합만(예: 비휘발성 레지스터만) 복원될 수 있으므로 컨텍스트가 실제 메서드 호출 시 레지스터 상태와 정확히 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2637a-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2637a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2637a-116">Requirements</span></span>  

 <span data-ttu-id="2637a-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2637a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2637a-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2637a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2637a-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2637a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2637a-120">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2637a-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2637a-121">참조</span><span class="sxs-lookup"><span data-stu-id="2637a-121">See also</span></span>

- [<span data-ttu-id="2637a-122">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2637a-122">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="2637a-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2637a-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
