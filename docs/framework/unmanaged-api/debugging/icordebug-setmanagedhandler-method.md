---
title: ICorDebug::SetManagedHandler 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f30089879f2d023c8fb04b52e75b2942da2a83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786349"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="4a264-102">ICorDebug::SetManagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="4a264-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="4a264-103">관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a264-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a264-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a264-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a264-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a264-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="4a264-106">[in] 에 대 한 포인터를 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) 개체의 이벤트 처리기 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4a264-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a264-107">설명</span><span class="sxs-lookup"><span data-stu-id="4a264-107">Remarks</span></span>  
 <span data-ttu-id="4a264-108">`SetManagedHandler` 생성 시 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a264-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="4a264-109">경우는 `ICorDebugManagedCallback` 구현에는 디버깅 중인 응용 프로그램의 디버깅 이벤트를 처리할 충분 한 인터페이스 `SetManagedHandler` HRESULT의 E_NOINTERFACE가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a264-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a264-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a264-110">Requirements</span></span>  
 <span data-ttu-id="4a264-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a264-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a264-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a264-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a264-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a264-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a264-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a264-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a264-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a264-115">See also</span></span>

- [<span data-ttu-id="4a264-116">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a264-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
