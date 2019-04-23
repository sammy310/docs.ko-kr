---
title: ICorDebugManagedCallback::Exception 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91318ea596cc7d6c8a747901fea2749a64aa2623
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168118"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="24ecb-102">ICorDebugManagedCallback::Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="24ecb-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="24ecb-103">관리 코드에서 예외가 throw 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="24ecb-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ecb-104">구문</span><span class="sxs-lookup"><span data-stu-id="24ecb-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24ecb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24ecb-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="24ecb-106">[in] 예외가 throw 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24ecb-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="24ecb-107">[in] 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24ecb-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="24ecb-108">[in] 이 값이 `false`, 예외 되지 아직이 고 그렇지 않으면 응용 프로그램에서 처리 된 예외는 처리 되지 않으며 프로세스가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24ecb-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24ecb-109">설명</span><span class="sxs-lookup"><span data-stu-id="24ecb-109">Remarks</span></span>  
 <span data-ttu-id="24ecb-110">스레드 개체에서 특정 예외를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24ecb-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ecb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24ecb-111">Requirements</span></span>  
 <span data-ttu-id="24ecb-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="24ecb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ecb-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24ecb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24ecb-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24ecb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24ecb-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ecb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ecb-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="24ecb-116">See also</span></span>

- [<span data-ttu-id="24ecb-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24ecb-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
