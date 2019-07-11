---
title: ICorDebugModuleDebugEvent::GetModule Method
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: debf2e9dd08f6a35801932b22fbd985e7299b79f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764356"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="63d28-102">ICorDebugModuleDebugEvent::GetModule Method</span><span class="sxs-lookup"><span data-stu-id="63d28-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="63d28-103">방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="63d28-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d28-104">구문</span><span class="sxs-lookup"><span data-stu-id="63d28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d28-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63d28-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="63d28-106">[out] 방금 로드 또는 언로드된 병합 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="63d28-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d28-107">설명</span><span class="sxs-lookup"><span data-stu-id="63d28-107">Remarks</span></span>  
 <span data-ttu-id="63d28-108">호출할 수 있습니다 합니다 [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 모듈 로드 또는 언로드 되었는지 여부를 결정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="63d28-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63d28-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63d28-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d28-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63d28-110">Requirements</span></span>  
 <span data-ttu-id="63d28-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="63d28-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d28-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63d28-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63d28-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d28-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d28-114">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d28-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d28-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="63d28-115">See also</span></span>

- [<span data-ttu-id="63d28-116">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63d28-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="63d28-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63d28-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
