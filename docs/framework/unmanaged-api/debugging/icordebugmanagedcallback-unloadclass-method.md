---
title: ICorDebugManagedCallback::UnloadClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 020774778b21cf0f6029a666e0022fe83845c4ed
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472449"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="77d7e-102">ICorDebugManagedCallback::UnloadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="77d7e-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="77d7e-103">클래스를 언로드되고 있음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="77d7e-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77d7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="77d7e-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77d7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77d7e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="77d7e-106">[in] 클래스를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77d7e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="77d7e-107">[in] 클래스를 나타내는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77d7e-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77d7e-108">설명</span><span class="sxs-lookup"><span data-stu-id="77d7e-108">Remarks</span></span>  
 <span data-ttu-id="77d7e-109">이 호출 후에 클래스를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77d7e-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77d7e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77d7e-110">Requirements</span></span>  
 <span data-ttu-id="77d7e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="77d7e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77d7e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77d7e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77d7e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77d7e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77d7e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77d7e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d7e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="77d7e-115">See also</span></span>
- [<span data-ttu-id="77d7e-116">LoadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="77d7e-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="77d7e-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77d7e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
