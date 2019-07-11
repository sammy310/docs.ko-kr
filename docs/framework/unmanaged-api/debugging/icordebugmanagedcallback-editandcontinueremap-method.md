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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 100688ece4ebb984d3d03823ab01bbaae7d395db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760277"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="5fa3a-102">ICorDebugManagedCallback::EditAndContinueRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="5fa3a-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="5fa3a-103">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fa3a-103">This method has been deprecated.</span></span> <span data-ttu-id="5fa3a-104">통합된 개발 환경 (IDE) 매핑 변경 이벤트를 보냈음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5fa3a-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa3a-105">구문</span><span class="sxs-lookup"><span data-stu-id="5fa3a-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="5fa3a-106">설명</span><span class="sxs-lookup"><span data-stu-id="5fa3a-106">Remarks</span></span>  
 <span data-ttu-id="5fa3a-107">`EditAndContinueRemap` 메서드 된 업데이트 된 함수의 이전 버전의 코드를 실행 하려는 경우 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fa3a-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="5fa3a-108">공용 언어 런타임 호출을 `EditAndContinueRemap` IDE에 다시 매핑 이벤트를 보내는 방법.</span><span class="sxs-lookup"><span data-stu-id="5fa3a-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa3a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5fa3a-109">Requirements</span></span>  
 <span data-ttu-id="5fa3a-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5fa3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa3a-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fa3a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fa3a-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fa3a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fa3a-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa3a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fa3a-114">See also</span></span>

- [<span data-ttu-id="5fa3a-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fa3a-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
