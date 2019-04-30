---
title: ICorDebugManagedCallback::ExitAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aed6ccd938761385aafd21802829bd741847b4ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988210"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="fcf65-102">ICorDebugManagedCallback::ExitAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="fcf65-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="fcf65-103">응용 프로그램 도메인 종료 되었습니다. 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fcf65-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf65-104">구문</span><span class="sxs-lookup"><span data-stu-id="fcf65-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf65-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fcf65-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="fcf65-106">[in] 지정 된 응용 프로그램 도메인을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf65-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="fcf65-107">[in] 종료 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf65-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf65-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fcf65-108">Requirements</span></span>  
 <span data-ttu-id="fcf65-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fcf65-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf65-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcf65-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcf65-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcf65-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcf65-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf65-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf65-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="fcf65-113">See also</span></span>

- [<span data-ttu-id="fcf65-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fcf65-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
