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
ms.openlocfilehash: d552b694787b5d9f0d5adc399eda6f75df93c385
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793031"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="40da7-102">ICorDebugModule::EnableClassLoadCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="40da7-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="40da7-103">이 모듈에 대해 [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) 및 [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) 콜백이 호출 되는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="40da7-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40da7-104">구문</span><span class="sxs-lookup"><span data-stu-id="40da7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40da7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40da7-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="40da7-106">진행 이 값을 `true` 설정 하 여 CLR (공용 언어 런타임)에서 `ICorDebugManagedCallback::LoadClass`를 호출 하 고 연결 된 이벤트가 발생할 때 메서드를 `ICorDebugManagedCallback::UnloadClass` 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="40da7-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="40da7-107">비동적 모듈의 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="40da7-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="40da7-108">동적 모듈의 경우 값이 항상 `true` 되며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40da7-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40da7-109">주의</span><span class="sxs-lookup"><span data-stu-id="40da7-109">Remarks</span></span>  
 <span data-ttu-id="40da7-110">`ICorDebugManagedCallback::LoadClass` 및 `ICorDebugManagedCallback::UnloadClass` 콜백은 항상 동적 모듈에 대해 사용 하도록 설정 되며 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40da7-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40da7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40da7-111">Requirements</span></span>  
 <span data-ttu-id="40da7-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40da7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40da7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40da7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40da7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40da7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40da7-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40da7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40da7-116">참조</span><span class="sxs-lookup"><span data-stu-id="40da7-116">See also</span></span>
