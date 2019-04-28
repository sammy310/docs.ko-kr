---
title: ICorDebugModule::EnableClassLoadCallbacks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22a838748414f9d89cdc7ff469f7f5cc5e11b9d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796892"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="a7250-102">ICorDebugModule::EnableClassLoadCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="a7250-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="a7250-103">컨트롤 여부는 [icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 이 모듈에 대 한 콜백을 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7250-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7250-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7250-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7250-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7250-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="a7250-106">[in] 이 값을 설정 `true` 는 CLR (공용 언어 런타임) 호출을 사용 하도록 설정 합니다 `ICorDebugManagedCallback::LoadClass` 및 `ICorDebugManagedCallback::UnloadClass` 관련된 이벤트가 발생할 때 메서드.</span><span class="sxs-lookup"><span data-stu-id="a7250-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="a7250-107">기본값은 `false` 동적이 지 않은 모듈에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7250-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="a7250-108">값은 항상 `true` 동적 모듈에 대 한 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7250-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7250-109">설명</span><span class="sxs-lookup"><span data-stu-id="a7250-109">Remarks</span></span>  
 <span data-ttu-id="a7250-110">합니다 `ICorDebugManagedCallback::LoadClass` 고 `ICorDebugManagedCallback::UnloadClass` 콜백을 동적 모듈에 대해 항상 설정 되 고 비활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7250-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7250-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7250-111">Requirements</span></span>  
 <span data-ttu-id="a7250-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7250-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7250-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7250-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7250-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7250-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7250-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7250-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7250-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7250-116">See also</span></span>
