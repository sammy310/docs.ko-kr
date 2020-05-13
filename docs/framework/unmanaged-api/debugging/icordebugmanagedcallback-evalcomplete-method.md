---
title: ICorDebugManagedCallback::EvalComplete 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
ms.openlocfilehash: 0431b54997c9889e2b3206392e86e4dcde45ffb3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212453"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="f2ed0-102">ICorDebugManagedCallback::EvalComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="f2ed0-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="f2ed0-103">평가가 완료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f2ed0-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ed0-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2ed0-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2ed0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2ed0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f2ed0-106">진행 평가가 수행 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ed0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f2ed0-107">진행 계산이 수행 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ed0-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="f2ed0-108">진행 계산을 수행 하는 코드를 나타내는 ICorDebugEval 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ed0-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ed0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2ed0-109">Requirements</span></span>  
 <span data-ttu-id="f2ed0-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2ed0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ed0-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2ed0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2ed0-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ed0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ed0-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ed0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ed0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ed0-114">See also</span></span>

- [<span data-ttu-id="f2ed0-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2ed0-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
