---
description: '자세히 알아보기: ICorDebugStackWalk 인터페이스'
title: ICorDebugStackWalk 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: 27dcdfc90829a3a28d81ad28dce0cd4d1d674948
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738093"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="2592a-103">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2592a-103">ICorDebugStackWalk Interface</span></span>

<span data-ttu-id="2592a-104">스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2592a-104">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2592a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2592a-105">Methods</span></span>  
  
|<span data-ttu-id="2592a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2592a-106">Method</span></span>|<span data-ttu-id="2592a-107">설명</span><span class="sxs-lookup"><span data-stu-id="2592a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2592a-108">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="2592a-108">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="2592a-109">개체의 현재 프레임에 대 한 컨텍스트를 반환 합니다 `ICorDebugStackWalk` .</span><span class="sxs-lookup"><span data-stu-id="2592a-109">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="2592a-110">SetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="2592a-110">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="2592a-111">`ICorDebugStackWalk`개체의 현재 컨텍스트를 스레드의 유효한 컨텍스트로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2592a-111">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="2592a-112">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="2592a-112">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="2592a-113">개체를 `ICorDebugStackWalk` 다음 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2592a-113">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="2592a-114">GetFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="2592a-114">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="2592a-115">개체의 현재 프레임을 가져옵니다 `ICorDebugStackWalk` .</span><span class="sxs-lookup"><span data-stu-id="2592a-115">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2592a-116">설명</span><span class="sxs-lookup"><span data-stu-id="2592a-116">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2592a-117">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2592a-117">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2592a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2592a-118">Requirements</span></span>  

 <span data-ttu-id="2592a-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2592a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2592a-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2592a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2592a-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2592a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2592a-122">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2592a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2592a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2592a-123">See also</span></span>

- [<span data-ttu-id="2592a-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2592a-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2592a-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="2592a-125">Debugging</span></span>](index.md)
