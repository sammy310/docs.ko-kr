---
title: ICorDebugModuleEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa341c726ba84dc1d12b6c5628253a100d65a719
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942482"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="d46b7-102">ICorDebugModuleEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="d46b7-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="d46b7-103">지정 된 "ICorDebugModule" 인스턴스 수를 가져옵니다 `celt` 를 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d46b7-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d46b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="d46b7-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d46b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d46b7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d46b7-106">[in] 수가 `ICorDebugModule` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d46b7-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="d46b7-107">[out] 각각 가리키는 포인터 배열을 `ICorDebugModule` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d46b7-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d46b7-108">[out] 개수에 대 한 포인터 `ICorDebugModule` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d46b7-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="d46b7-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d46b7-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d46b7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d46b7-110">Requirements</span></span>  
 <span data-ttu-id="d46b7-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d46b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d46b7-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d46b7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d46b7-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d46b7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d46b7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d46b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46b7-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="d46b7-115">See also</span></span>
