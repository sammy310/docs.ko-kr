---
description: '자세히 알아보기: ICorDebugManagedCallback:: EditAndContinueRemap 메서드'
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
ms.openlocfilehash: ad8932e41236cdb8ed213024efb4175292a5d5f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791009"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="4ebb9-103">ICorDebugManagedCallback::EditAndContinueRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="4ebb9-103">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>

<span data-ttu-id="4ebb9-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-104">This method has been deprecated.</span></span> <span data-ttu-id="4ebb9-105">다시 매핑 이벤트는 IDE (통합 개발 환경)에 전송 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-105">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ebb9-106">구문</span><span class="sxs-lookup"><span data-stu-id="4ebb9-106">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="4ebb9-107">설명</span><span class="sxs-lookup"><span data-stu-id="4ebb9-107">Remarks</span></span>  

 <span data-ttu-id="4ebb9-108">`EditAndContinueRemap`이전 버전의 업데이트 된 함수에서 코드를 실행 하려고 시도 하면 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-108">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="4ebb9-109">공용 언어 런타임에서는 메서드를 호출 하 여 다시 `EditAndContinueRemap` 매핑 이벤트를 IDE에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-109">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ebb9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ebb9-110">Requirements</span></span>  

 <span data-ttu-id="4ebb9-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ebb9-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ebb9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ebb9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ebb9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ebb9-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ebb9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebb9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ebb9-115">See also</span></span>

- [<span data-ttu-id="4ebb9-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ebb9-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
