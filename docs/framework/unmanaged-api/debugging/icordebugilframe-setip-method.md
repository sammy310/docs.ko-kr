---
title: ICorDebugILFrame::SetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
ms.openlocfilehash: 60273d7cf91be04c5fc3041260e4bb146ce9a45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095425"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="f9d73-102">ICorDebugILFrame::SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="f9d73-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="f9d73-103">MSIL (Microsoft 중간 언어) 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d73-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9d73-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9d73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9d73-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f9d73-106">MSIL 코드의 오프셋 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9d73-107">주의</span><span class="sxs-lookup"><span data-stu-id="f9d73-107">Remarks</span></span>  
 <span data-ttu-id="f9d73-108">`SetIP`를 호출 하면 현재 스레드에 대 한 모든 프레임과 체인이 즉시 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="f9d73-109">`SetIP`를 호출한 후 디버거에 프레임 정보가 필요한 경우 새 스택 추적을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="f9d73-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 는 스택 프레임을 유효한 상태로 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="f9d73-111">그러나 프레임이 유효한 상태 이더라도 초기화 되지 않은 지역 변수 같은 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="f9d73-112">호출자는 실행 중인 프로그램의 일관성을 보장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="f9d73-113">64 비트 플랫폼에서 명령 포인터는 `catch` 또는 `finally` 블록 밖으로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="f9d73-114">`SetIP`를 호출 하 여 64 비트 플랫폼에서 이러한 이동을 수행 하는 경우 실패를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d73-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9d73-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9d73-115">Requirements</span></span>  
 <span data-ttu-id="f9d73-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9d73-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9d73-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9d73-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9d73-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9d73-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9d73-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9d73-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
