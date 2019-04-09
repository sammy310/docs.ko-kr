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
ms.openlocfilehash: 602bcd12d1fd4c5806de6db81252731baa447b7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120018"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="4e0fe-102">ICorDebugManagedCallback::EvalException 메서드</span><span class="sxs-lookup"><span data-stu-id="4e0fe-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="4e0fe-103">처리 되지 않은 예외를 사용 하 여 계산이 종료는 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4e0fe-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e0fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e0fe-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e0fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e0fe-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4e0fe-106">[in] 평가 종료 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4e0fe-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4e0fe-107">[in] 평가 종료 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4e0fe-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="4e0fe-108">[in] 평가 수행 하는 코드를 나타내는 ICorDebugEval 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4e0fe-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e0fe-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e0fe-109">Requirements</span></span>  
 <span data-ttu-id="4e0fe-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e0fe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e0fe-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e0fe-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e0fe-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e0fe-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4e0fe-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="4e0fe-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e0fe-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e0fe-114">See also</span></span>

- [<span data-ttu-id="4e0fe-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e0fe-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
