---
title: ICorDebugManagedCallback::NameChange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abbfd21736d220f1cba029235c71a85bf3048ff0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761606"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="ac0e5-102">ICorDebugManagedCallback::NameChange 메서드</span><span class="sxs-lookup"><span data-stu-id="ac0e5-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="ac0e5-103">응용 프로그램 도메인 또는 스레드 이름이 변경 되었습니다 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ac0e5-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac0e5-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac0e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac0e5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ac0e5-106">[in] 응용 프로그램 도메인 또는 이름 변경 하거나 있던 나타내는 ICorDebugAppDomain 개체에 대 한 포인터 이름을 변경 하는 스레드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0e5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ac0e5-107">[in] 이름을 변경 하는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac0e5-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0e5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac0e5-108">Requirements</span></span>  
 <span data-ttu-id="ac0e5-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ac0e5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac0e5-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac0e5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac0e5-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac0e5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac0e5-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac0e5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0e5-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac0e5-113">See also</span></span>

- [<span data-ttu-id="ac0e5-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac0e5-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
