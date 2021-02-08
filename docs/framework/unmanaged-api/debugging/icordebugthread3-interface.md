---
description: '자세히 알아보기: ICorDebugThread3 인터페이스'
title: ICorDebugThread3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 88c668f1e08d0843f26d231937c85d80e03bee6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800970"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="9b413-103">ICorDebugThread3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b413-103">ICorDebugThread3 Interface</span></span>

<span data-ttu-id="9b413-104">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 및 해당 인터페이스에 대 한 진입점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b413-104">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b413-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9b413-105">Methods</span></span>  
  
|<span data-ttu-id="9b413-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9b413-106">Method</span></span>|<span data-ttu-id="9b413-107">설명</span><span class="sxs-lookup"><span data-stu-id="9b413-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b413-108">CreateStackWalk 메서드</span><span class="sxs-lookup"><span data-stu-id="9b413-108">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="9b413-109">스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b413-109">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="9b413-110">GetActiveInternalFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="9b413-110">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="9b413-111">스택에서 내부 프레임 ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체)의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b413-111">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b413-112">설명</span><span class="sxs-lookup"><span data-stu-id="9b413-112">Remarks</span></span>  

 <span data-ttu-id="9b413-113">`ICorDebugThread3` 는 ICorDebugThread 인터페이스에 대 한 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="9b413-113">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b413-114">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b413-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b413-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b413-115">Requirements</span></span>  

 <span data-ttu-id="9b413-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b413-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b413-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b413-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b413-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b413-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b413-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b413-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b413-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b413-120">See also</span></span>

- [<span data-ttu-id="9b413-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b413-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9b413-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="9b413-122">Debugging</span></span>](index.md)
