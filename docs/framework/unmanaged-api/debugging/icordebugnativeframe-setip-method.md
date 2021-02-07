---
description: '자세히 알아보기: ICorDebugNativeFrame:: SetIP 메서드'
title: ICorDebugNativeFrame::SetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: cb55b35eb4bd107a7273fd80ba83baac96610fb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729174"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="410ac-103">ICorDebugNativeFrame::SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="410ac-103">ICorDebugNativeFrame::SetIP Method</span></span>

<span data-ttu-id="410ac-104">네이티브 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-104">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410ac-105">구문</span><span class="sxs-lookup"><span data-stu-id="410ac-105">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="410ac-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="410ac-106">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="410ac-107">진행 네이티브 코드의 오프셋 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-107">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="410ac-108">설명</span><span class="sxs-lookup"><span data-stu-id="410ac-108">Remarks</span></span>  

 <span data-ttu-id="410ac-109">를 호출 `SetIP` 하면 현재 스레드에 대 한 모든 프레임과 체인이 즉시 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-109">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="410ac-110">를 호출한 후 디버거에 프레임 정보가 필요한 경우 `SetIP` 새 스택 추적을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-110">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="410ac-111">[ICorDebug](icordebug-interface.md) 는 스택 프레임을 유효한 상태로 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-111">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="410ac-112">그러나 런타임이 중요 한 것 처럼 프레임이 유효한 상태에 있더라도 지역 변수를 초기화 하지 않는 등의 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-112">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="410ac-113">호출자는 실행 중인 프로그램의 일관성을 지 게 할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-113">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="410ac-114">64 비트 플랫폼에서 명령 포인터는 또는 블록 밖으로 이동할 수 없습니다 `catch` `finally` .</span><span class="sxs-lookup"><span data-stu-id="410ac-114">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="410ac-115">을 `SetIP` 호출 하 여 64 비트 플랫폼에서 이러한 이동을 수행 하는 경우 실패를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="410ac-115">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="410ac-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="410ac-116">Requirements</span></span>  

 <span data-ttu-id="410ac-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="410ac-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="410ac-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="410ac-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="410ac-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="410ac-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="410ac-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="410ac-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410ac-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="410ac-121">See also</span></span>
