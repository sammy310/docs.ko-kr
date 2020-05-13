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
ms.openlocfilehash: 43f585417ed52b92c23087c0f02fd188ee09ea7e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210217"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="16f64-102">ICorDebugILFrame2::RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="16f64-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="16f64-103">새 MSIL (Microsoft 중간 언어) 오프셋을 지정 하 여 편집 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f64-104">구문</span><span class="sxs-lookup"><span data-stu-id="16f64-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16f64-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16f64-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="16f64-106">진행 명령 포인터가 배치 되어야 하는 스택 프레임의 새 MSIL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="16f64-107">이 값은 시퀀스 위치 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="16f64-108">이 값의 유효성을 확인 하는 것은 호출자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="16f64-109">예를 들어 MSIL 오프셋은 함수 범위 밖에 있을 경우 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16f64-110">설명</span><span class="sxs-lookup"><span data-stu-id="16f64-110">Remarks</span></span>  
 <span data-ttu-id="16f64-111">프레임의 함수가 편집 된 경우 디버거는 메서드를 호출 `RemapFunction` 하 여 최신 버전의 프레임 함수를 교환 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="16f64-112">지정 된 MSIL 오프셋에서 코드 실행이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16f64-113">`RemapFunction` [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md)호출과 같이를 호출 하면 스레드의 스택 추적 생성과 관련 된 모든 디버깅 인터페이스가 즉시 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="16f64-114">이러한 인터페이스에는 [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame 및 ICorDebugNativeFrame가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="16f64-115">`RemapFunction`메서드는 현재 프레임의 컨텍스트에서만 호출할 수 있으며, 다음 중 한 가지 경우에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="16f64-116">[ICorDebugManagedCallback2:: FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) 콜백이 아직 지속 되지 않은 것을 확인 한 후</span><span class="sxs-lookup"><span data-stu-id="16f64-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="16f64-117">이 프레임에 대 한 [ICorDebugManagedCallback:: EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) 이벤트로 인해 코드 실행이 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16f64-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16f64-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16f64-118">Requirements</span></span>  
 <span data-ttu-id="16f64-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16f64-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16f64-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16f64-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16f64-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16f64-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16f64-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16f64-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
