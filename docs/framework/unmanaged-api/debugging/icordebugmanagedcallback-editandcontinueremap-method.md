---
title: ICorDebugManagedCallback::EditAndContinueRemap 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
ms.openlocfilehash: 9cb956c0262fdcdb5971d049ea7b057aa4d952c0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781899"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="e8a9c-102">ICorDebugManagedCallback::EditAndContinueRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="e8a9c-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="e8a9c-103">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8a9c-103">This method has been deprecated.</span></span> <span data-ttu-id="e8a9c-104">다시 매핑 이벤트는 IDE (통합 개발 환경)에 전송 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e8a9c-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a9c-105">구문</span><span class="sxs-lookup"><span data-stu-id="e8a9c-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e8a9c-106">주의</span><span class="sxs-lookup"><span data-stu-id="e8a9c-106">Remarks</span></span>  
 <span data-ttu-id="e8a9c-107">`EditAndContinueRemap` 메서드는 이전 버전의 업데이트 된 함수에서 코드를 실행 하려고 할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8a9c-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="e8a9c-108">공용 언어 런타임에서는 `EditAndContinueRemap` 메서드를 호출 하 여 다시 매핑 이벤트를 IDE에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8a9c-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a9c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8a9c-109">Requirements</span></span>  
 <span data-ttu-id="e8a9c-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8a9c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8a9c-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8a9c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8a9c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8a9c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8a9c-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8a9c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a9c-114">참조</span><span class="sxs-lookup"><span data-stu-id="e8a9c-114">See also</span></span>

- [<span data-ttu-id="e8a9c-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8a9c-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
