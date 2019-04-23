---
title: ICorDebugManagedCallback::Breakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8591cb7f8eec3d92100b49db553ed1b5b6533c17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131081"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="238e9-102">ICorDebugManagedCallback::Breakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="238e9-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="238e9-103">중단점에 도달할 때 디버거를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="238e9-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="238e9-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="238e9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="238e9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="238e9-106">[in] 중단점이 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="238e9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="238e9-107">[in] 중단점이 포함 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="238e9-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="238e9-108">[in] 중단점을 나타내는 ICorDebugBreakpoint 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="238e9-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238e9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="238e9-109">Requirements</span></span>  
 <span data-ttu-id="238e9-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="238e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238e9-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="238e9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="238e9-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="238e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="238e9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="238e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238e9-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="238e9-114">See also</span></span>

- [<span data-ttu-id="238e9-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="238e9-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
