---
title: ICorDebugModuleDebugEvent::GetModule Method
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c0cc1305f47f03c8c9b35bab5c980cb23d1b157
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942495"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="67d00-102">ICorDebugModuleDebugEvent::GetModule Method</span><span class="sxs-lookup"><span data-stu-id="67d00-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="67d00-103">방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67d00-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67d00-104">구문</span><span class="sxs-lookup"><span data-stu-id="67d00-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67d00-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67d00-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="67d00-106">[out] 방금 로드 또는 언로드된 병합 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="67d00-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67d00-107">설명</span><span class="sxs-lookup"><span data-stu-id="67d00-107">Remarks</span></span>  
 <span data-ttu-id="67d00-108">호출할 수 있습니다 합니다 [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 모듈 로드 또는 언로드 되었는지 여부를 결정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67d00-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67d00-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d00-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67d00-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67d00-110">Requirements</span></span>  
 <span data-ttu-id="67d00-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d00-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67d00-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67d00-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67d00-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67d00-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67d00-114">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67d00-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d00-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="67d00-115">See also</span></span>

- [<span data-ttu-id="67d00-116">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67d00-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="67d00-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67d00-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
