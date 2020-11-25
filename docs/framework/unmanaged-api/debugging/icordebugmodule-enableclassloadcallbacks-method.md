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
ms.openlocfilehash: 1f6c6ae3b7cb45b049d0fb0d88bbf89121bccfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710417"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="c55f6-102">ICorDebugModule::EnableClassLoadCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="c55f6-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>

<span data-ttu-id="c55f6-103">이 모듈에 대해 [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) 및 [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) 콜백이 호출 되는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c55f6-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c55f6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c55f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c55f6-105">Parameters</span></span>  

 `bClassLoadCallbacks`  
 <span data-ttu-id="c55f6-106">진행 `true` `ICorDebugManagedCallback::LoadClass` 연결 된 이벤트가 발생할 때 CLR (공용 언어 런타임)에서 및 메서드를 호출할 수 있도록 하려면이 값을로 설정 `ICorDebugManagedCallback::UnloadClass` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c55f6-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="c55f6-107">동적이 아닌 모듈의 경우 기본값은입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="c55f6-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="c55f6-108">동적 모듈의 경우이 값은 항상 이며 `true` 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c55f6-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c55f6-109">설명</span><span class="sxs-lookup"><span data-stu-id="c55f6-109">Remarks</span></span>  

 <span data-ttu-id="c55f6-110">`ICorDebugManagedCallback::LoadClass`및 `ICorDebugManagedCallback::UnloadClass` 콜백은 동적 모듈에 대해 항상 사용할 수 있으며 비활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c55f6-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c55f6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c55f6-111">Requirements</span></span>  

 <span data-ttu-id="c55f6-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c55f6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c55f6-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c55f6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c55f6-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c55f6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c55f6-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c55f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55f6-116">참조</span><span class="sxs-lookup"><span data-stu-id="c55f6-116">See also</span></span>
