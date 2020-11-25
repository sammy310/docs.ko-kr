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
ms.openlocfilehash: 1d8aa2cca9dbbeaa9e03813b177ca59125770803
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721285"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="311e8-102">ICorDebugManagedCallback::EditAndContinueRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="311e8-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>

<span data-ttu-id="311e8-103">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="311e8-103">This method has been deprecated.</span></span> <span data-ttu-id="311e8-104">다시 매핑 이벤트는 IDE (통합 개발 환경)에 전송 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="311e8-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311e8-105">구문</span><span class="sxs-lookup"><span data-stu-id="311e8-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="311e8-106">설명</span><span class="sxs-lookup"><span data-stu-id="311e8-106">Remarks</span></span>  

 <span data-ttu-id="311e8-107">`EditAndContinueRemap`이전 버전의 업데이트 된 함수에서 코드를 실행 하려고 시도 하면 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="311e8-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="311e8-108">공용 언어 런타임에서는 메서드를 호출 하 여 다시 `EditAndContinueRemap` 매핑 이벤트를 IDE에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="311e8-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="311e8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="311e8-109">Requirements</span></span>  

 <span data-ttu-id="311e8-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="311e8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="311e8-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="311e8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="311e8-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="311e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="311e8-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="311e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311e8-114">참조</span><span class="sxs-lookup"><span data-stu-id="311e8-114">See also</span></span>

- [<span data-ttu-id="311e8-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="311e8-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
