---
title: ICorDebugILFrame2::RemapFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92885d2a6514839a864d6a345dd8af8b07b90c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489815"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="7cc25-102">ICorDebugILFrame2::RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="7cc25-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="7cc25-103">새 Microsoft MSIL (intermediate language) 오프셋을 지정 하 여 편집된 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc25-104">구문</span><span class="sxs-lookup"><span data-stu-id="7cc25-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cc25-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7cc25-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="7cc25-106">[in] 스택 프레임의 새 MSIL 오프셋 명령 포인터를 배치할입니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="7cc25-107">이 값에 시퀀스 포인트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="7cc25-108">이 값의 유효성을 확인 해야 하는 호출자의 경우</span><span class="sxs-lookup"><span data-stu-id="7cc25-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="7cc25-109">예를 들어, MSIL 오프셋 함수의 범위를 벗어난 경우에 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cc25-110">설명</span><span class="sxs-lookup"><span data-stu-id="7cc25-110">Remarks</span></span>  
 <span data-ttu-id="7cc25-111">디버거에서 호출 프레임의 함수를 편집한 후에 `RemapFunction` 실행할 수 있도록 최신 버전의 프레임의 함수에서 교환 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="7cc25-112">코드 실행의 지정 된 MSIL 오프셋에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cc25-113">호출 `RemapFunction`같은 호출 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), 스레드의 스택 추적을 생성 하려면 관련 된 모든 디버깅 인터페이스를 즉시 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="7cc25-114">이러한 인터페이스를 포함 [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, 및 ICorDebugNativeFrame 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="7cc25-115">`RemapFunction` 현재 프레임의 컨텍스트에서만에서 및 다음 경우 중 하나에 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
-   <span data-ttu-id="7cc25-116">수신 후는 [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) 계속 하지 아직 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
-   <span data-ttu-id="7cc25-117">때문에 코드 실행이 중지 된 동안는 [icordebugmanagedcallback:: Editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) 이 프레임에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7cc25-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cc25-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7cc25-118">Requirements</span></span>  
 <span data-ttu-id="7cc25-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7cc25-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cc25-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cc25-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cc25-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cc25-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cc25-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc25-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
