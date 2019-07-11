---
title: ICorDebugManagedCallback::UnloadModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8826644ae3bdfbef76e9143de5f8f449c1555095
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761210"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="5fda6-102">ICorDebugManagedCallback::UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="5fda6-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="5fda6-103">공용 언어 런타임 모듈 (DLL)이 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5fda6-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fda6-104">구문</span><span class="sxs-lookup"><span data-stu-id="5fda6-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fda6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5fda6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5fda6-106">[in] 모듈을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="5fda6-107">[in] 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda6-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fda6-108">설명</span><span class="sxs-lookup"><span data-stu-id="5fda6-108">Remarks</span></span>  
 <span data-ttu-id="5fda6-109">모듈은이 호출 후에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda6-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fda6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5fda6-110">Requirements</span></span>  
 <span data-ttu-id="5fda6-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5fda6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fda6-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fda6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fda6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fda6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fda6-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fda6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fda6-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fda6-115">See also</span></span>

- [<span data-ttu-id="5fda6-116">LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="5fda6-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="5fda6-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fda6-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
