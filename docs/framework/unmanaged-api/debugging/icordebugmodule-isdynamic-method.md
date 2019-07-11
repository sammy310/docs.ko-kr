---
title: ICorDebugModule::IsDynamic 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db5d07d2b9a295a5cd21b4d4af954503b8bd7a8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763666"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="2c25e-102">ICorDebugModule::IsDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="2c25e-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="2c25e-103">이 모듈 동적 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c25e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c25e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c25e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c25e-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="2c25e-106">[out] `true` 경우이 모듈은 고, 그렇지 않으면 동적 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c25e-107">설명</span><span class="sxs-lookup"><span data-stu-id="2c25e-107">Remarks</span></span>  
 <span data-ttu-id="2c25e-108">동적 모듈을 새 클래스를 추가 하 고 모듈이 로드 된 후에 기존 클래스를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c25e-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="2c25e-109">합니다 [icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 하 고 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 클래스 추가 되거나 삭제 된 경우 콜백을 디버거에 알리기 위해.</span><span class="sxs-lookup"><span data-stu-id="2c25e-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c25e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c25e-110">Requirements</span></span>  
 <span data-ttu-id="2c25e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c25e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c25e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c25e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c25e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c25e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c25e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c25e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
