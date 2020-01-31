---
title: ICorDebugVirtualUnwinder::GetContext 메서드
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: ff5e5bdd66ec44a0931b51212f07485718507576
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790836"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="3de29-102">ICorDebugVirtualUnwinder::GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="3de29-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>
<span data-ttu-id="3de29-103">이 해제기의 현재 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de29-104">구문</span><span class="sxs-lookup"><span data-stu-id="3de29-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3de29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3de29-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="3de29-106">[in] WinNT.h에 정의된 반환할 컨텍스트 부분을 지정하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="3de29-107">[in] `contextBuf`의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3de29-108">[out] 실제로 `contextBuf`에 기록되는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="3de29-109">[out] 이 해제기의 현재 컨텍스트를 포함하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3de29-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="3de29-110">Return Value</span></span>  
 <span data-ttu-id="3de29-111">mscordbi에 수신되는 모든 오류 HRESULT는 심각한 오류로 간주하여 ICorDebug API에서 `CORDBG_E_DATA_TARGET_ERROR`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3de29-112">주의</span><span class="sxs-lookup"><span data-stu-id="3de29-112">Remarks</span></span>  
 <span data-ttu-id="3de29-113">`contextBuf` 인수의 초기 값을 [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) 메서드를 호출 하 여 반환 되는 컨텍스트 버퍼로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3de29-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="3de29-115">해제하면 레지스터 하위 집합만(예: 비휘발성 레지스터만) 복원될 수 있으므로 컨텍스트가 실제 메서드 호출 시 레지스터 상태와 정확히 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de29-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de29-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3de29-116">Requirements</span></span>  
 <span data-ttu-id="3de29-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3de29-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de29-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3de29-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3de29-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3de29-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3de29-120">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de29-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de29-121">참조</span><span class="sxs-lookup"><span data-stu-id="3de29-121">See also</span></span>

- [<span data-ttu-id="3de29-122">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3de29-122">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="3de29-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3de29-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
