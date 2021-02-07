---
description: '자세히 알아보기: ICorDebugRegisterSet:: SetRegisters 메서드'
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
ms.openlocfilehash: 7a83d9d01a392d7ed435292f45ee0c75765ced36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690680"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="a060a-103">ICorDebugRegisterSet::SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="a060a-103">ICorDebugRegisterSet::SetRegisters Method</span></span>

<span data-ttu-id="a060a-104">`SetRegisters` 는 .NET Framework 버전 2.0에 구현 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a060a-104">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a060a-105">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a060a-105">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a060a-106">[ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) 또는 [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md)와 같은 상위 수준 작업을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a060a-106">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a060a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a060a-107">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a060a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a060a-108">Requirements</span></span>  

 <span data-ttu-id="a060a-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a060a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a060a-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a060a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a060a-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a060a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a060a-112">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a060a-112">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a060a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a060a-113">See also</span></span>

- [<span data-ttu-id="a060a-114">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a060a-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="a060a-115">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a060a-115">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
