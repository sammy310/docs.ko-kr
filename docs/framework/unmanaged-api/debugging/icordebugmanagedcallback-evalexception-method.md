---
title: ICorDebugManagedCallback::EvalException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e3ab185f1ca5571656ed9b4aa4352a007da4151
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484539"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="59122-102">ICorDebugManagedCallback::EvalException 메서드</span><span class="sxs-lookup"><span data-stu-id="59122-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="59122-103">처리 되지 않은 예외를 사용 하 여 계산이 종료는 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="59122-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59122-104">구문</span><span class="sxs-lookup"><span data-stu-id="59122-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59122-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59122-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="59122-106">[in] 평가 종료 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59122-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="59122-107">[in] 평가 종료 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59122-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="59122-108">[in] 평가 수행 하는 코드를 나타내는 ICorDebugEval 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59122-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59122-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59122-109">Requirements</span></span>  
 <span data-ttu-id="59122-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59122-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59122-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59122-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59122-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59122-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59122-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59122-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59122-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="59122-114">See also</span></span>
- [<span data-ttu-id="59122-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59122-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
