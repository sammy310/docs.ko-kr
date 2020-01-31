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
ms.openlocfilehash: 3ae93081bd201f745fa47bc01a9c6fcbf6e9f63c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781867"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="495dd-102">ICorDebugManagedCallback::EvalException 메서드</span><span class="sxs-lookup"><span data-stu-id="495dd-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="495dd-103">처리 되지 않은 예외를 사용 하 여 평가가 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="495dd-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="495dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="495dd-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="495dd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="495dd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="495dd-106">진행 평가가 종료 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="495dd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="495dd-107">진행 평가가 종료 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="495dd-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="495dd-108">진행 계산을 수행 하는 코드를 나타내는 ICorDebugEval 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="495dd-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="495dd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="495dd-109">Requirements</span></span>  
 <span data-ttu-id="495dd-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="495dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="495dd-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="495dd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="495dd-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="495dd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="495dd-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="495dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="495dd-114">참조</span><span class="sxs-lookup"><span data-stu-id="495dd-114">See also</span></span>

- [<span data-ttu-id="495dd-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="495dd-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
