---
description: '자세히 알아보기: ICorDebug:: Terminate 메서드'
title: ICorDebug::Terminate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: c2de27a47bfd4c364a09180c75109679234f3cae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754292"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="1a63e-103">ICorDebug::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="1a63e-103">ICorDebug::Terminate Method</span></span>

<span data-ttu-id="1a63e-104">개체를 종료 `ICorDebug` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a63e-104">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a63e-105">`Terminate` 디버깅 중인 모든 프로세스에 대해 [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) 콜백이 수신 될 때까지 호출 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a63e-105">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a63e-106">구문</span><span class="sxs-lookup"><span data-stu-id="1a63e-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1a63e-107">설명</span><span class="sxs-lookup"><span data-stu-id="1a63e-107">Remarks</span></span>  

 <span data-ttu-id="1a63e-108">`Terminate``ICorDebug`개체가 더 이상 필요 하지 않을 때를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a63e-108">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a63e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a63e-109">Requirements</span></span>  

 <span data-ttu-id="1a63e-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a63e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a63e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a63e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a63e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a63e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a63e-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a63e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a63e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a63e-114">See also</span></span>

- [<span data-ttu-id="1a63e-115">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a63e-115">ICorDebug Interface</span></span>](icordebug-interface.md)
