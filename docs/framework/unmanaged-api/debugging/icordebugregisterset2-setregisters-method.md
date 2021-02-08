---
description: '자세히 알아보기: ICorDebugRegisterSet2:: SetRegisters 메서드'
title: ICorDebugRegisterSet2::SetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
ms.openlocfilehash: d58717be34e146def2a54bb49d6cd58dde7564c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794756"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="41e2e-103">ICorDebugRegisterSet2::SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="41e2e-103">ICorDebugRegisterSet2::SetRegisters Method</span></span>

<span data-ttu-id="41e2e-104">`SetRegisters` 는 .NET Framework 버전 2.0에 구현 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41e2e-104">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="41e2e-105">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="41e2e-105">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41e2e-106">[ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) 또는 [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md)와 같은 상위 수준 작업을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41e2e-106">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e2e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="41e2e-107">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="41e2e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41e2e-108">Requirements</span></span>  

 <span data-ttu-id="41e2e-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41e2e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41e2e-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41e2e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41e2e-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41e2e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41e2e-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41e2e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e2e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41e2e-113">See also</span></span>

- [<span data-ttu-id="41e2e-114">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41e2e-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="41e2e-115">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41e2e-115">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
