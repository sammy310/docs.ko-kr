---
title: ICorDebugProcess6::ProcessStateChanged 메서드
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f25e25f94dae1a959cbb813a44a7f4f09eaa69c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474594"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="acb4e-102">ICorDebugProcess6::ProcessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="acb4e-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="acb4e-103">알립니다 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 프로세스가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb4e-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb4e-104">구문</span><span class="sxs-lookup"><span data-stu-id="acb4e-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acb4e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="acb4e-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="acb4e-106">[in] 멤버는 [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) 열거형</span><span class="sxs-lookup"><span data-stu-id="acb4e-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acb4e-107">설명</span><span class="sxs-lookup"><span data-stu-id="acb4e-107">Remarks</span></span>  
 <span data-ttu-id="acb4e-108">에 알리기 위해이 메서드를 호출 하는 디버거 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 프로세스가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acb4e-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acb4e-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acb4e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb4e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acb4e-110">Requirements</span></span>  
 <span data-ttu-id="acb4e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acb4e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb4e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acb4e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acb4e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acb4e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acb4e-114">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acb4e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb4e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="acb4e-115">See also</span></span>
- [<span data-ttu-id="acb4e-116">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acb4e-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="acb4e-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acb4e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
