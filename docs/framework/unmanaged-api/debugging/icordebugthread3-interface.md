---
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
ms.openlocfilehash: 19bd869aec7e4d046890d2314f5142753ba0b112
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791384"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="acc82-102">ICorDebugThread3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc82-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="acc82-103">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 및 해당 인터페이스에 대 한 진입점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc82-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acc82-104">메서드</span><span class="sxs-lookup"><span data-stu-id="acc82-104">Methods</span></span>  
  
|<span data-ttu-id="acc82-105">메서드</span><span class="sxs-lookup"><span data-stu-id="acc82-105">Method</span></span>|<span data-ttu-id="acc82-106">설명</span><span class="sxs-lookup"><span data-stu-id="acc82-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acc82-107">CreateStackWalk 메서드</span><span class="sxs-lookup"><span data-stu-id="acc82-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="acc82-108">스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acc82-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="acc82-109">GetActiveInternalFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="acc82-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="acc82-110">스택에서 내부 프레임 ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체)의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc82-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acc82-111">주의</span><span class="sxs-lookup"><span data-stu-id="acc82-111">Remarks</span></span>  
 <span data-ttu-id="acc82-112">`ICorDebugThread3`는 ICorDebugThread 인터페이스에 대 한 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="acc82-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="acc82-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acc82-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc82-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acc82-114">Requirements</span></span>  
 <span data-ttu-id="acc82-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acc82-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc82-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acc82-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acc82-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acc82-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acc82-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc82-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc82-119">참조</span><span class="sxs-lookup"><span data-stu-id="acc82-119">See also</span></span>

- [<span data-ttu-id="acc82-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc82-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="acc82-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="acc82-121">Debugging</span></span>](index.md)
