---
title: ICorDebugRegisterSet::SetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: 7af3109c822dfe945a60c16d4bd3b764f7550492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131336"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="fef72-102">ICorDebugRegisterSet::SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="fef72-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="fef72-103">`SetRegisters`는 .NET Framework 버전 2.0에 구현 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fef72-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="fef72-104">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="fef72-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fef72-105">[ICorDebugILFrame:: setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) 또는 [ICorDebugNativeFrame:: setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)와 같은 상위 수준 작업을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef72-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef72-106">구문</span><span class="sxs-lookup"><span data-stu-id="fef72-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="fef72-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fef72-107">Requirements</span></span>  
 <span data-ttu-id="fef72-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fef72-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fef72-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fef72-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fef72-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fef72-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fef72-111">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="fef72-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef72-112">참조</span><span class="sxs-lookup"><span data-stu-id="fef72-112">See also</span></span>

- [<span data-ttu-id="fef72-113">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fef72-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="fef72-114">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fef72-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
