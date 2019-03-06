---
title: ICorDebugManagedCallback::ExitThread 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a928aed73c0287a4cad2432fa6b6ebec43ea285
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489568"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="c3b34-102">ICorDebugManagedCallback::ExitThread 메서드</span><span class="sxs-lookup"><span data-stu-id="c3b34-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="c3b34-103">관리 되는 코드를 실행 하는 스레드가 종료 된 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c3b34-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b34-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3b34-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b34-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3b34-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c3b34-106">[in] 관리 되는 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b34-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="c3b34-107">[in] 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3b34-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3b34-108">설명</span><span class="sxs-lookup"><span data-stu-id="c3b34-108">Remarks</span></span>  
 <span data-ttu-id="c3b34-109">한 번의 `ExitThread` 콜백이 발생, 스레드가 스레드 열거형에 더 이상 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3b34-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b34-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3b34-110">Requirements</span></span>  
 <span data-ttu-id="c3b34-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3b34-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b34-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3b34-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3b34-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3b34-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3b34-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3b34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b34-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3b34-115">See also</span></span>
- [<span data-ttu-id="c3b34-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3b34-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
