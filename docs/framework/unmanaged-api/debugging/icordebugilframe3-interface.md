---
description: '자세히 알아보기: ICorDebugILFrame3 인터페이스'
title: ICorDebugILFrame3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: a34a3f0941871a2d0a63fb2d9f78ccb7ff455866
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791259"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="744bc-103">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="744bc-103">ICorDebugILFrame3 Interface</span></span>

<span data-ttu-id="744bc-104">함수의 반환 값을 캡슐화하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="744bc-104">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="744bc-105">`ICorDebugILFrame3` 는 ICorDebugILFrame 및 ICorDebugILFrame2 인터페이스의 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="744bc-105">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="744bc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="744bc-106">Methods</span></span>  
  
|<span data-ttu-id="744bc-107">메서드</span><span class="sxs-lookup"><span data-stu-id="744bc-107">Method</span></span>|<span data-ttu-id="744bc-108">설명</span><span class="sxs-lookup"><span data-stu-id="744bc-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="744bc-109">GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="744bc-109">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="744bc-110">함수의 반환 값을 캡슐화 하는 ICorDebugValue 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="744bc-110">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="744bc-111">설명</span><span class="sxs-lookup"><span data-stu-id="744bc-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="744bc-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="744bc-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="744bc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="744bc-113">Requirements</span></span>  

 <span data-ttu-id="744bc-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="744bc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="744bc-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="744bc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="744bc-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="744bc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="744bc-117">**.NET Framework 버전:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="744bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="744bc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="744bc-118">See also</span></span>

- [<span data-ttu-id="744bc-119">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="744bc-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="744bc-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="744bc-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
