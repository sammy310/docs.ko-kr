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
ms.openlocfilehash: 6c4262c18e4efcbbca1b3e2a327fec7d4b609a31
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096922"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="95a1d-102">ICorDebugModuleEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="95a1d-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="95a1d-103">현재 위치에서 시작 하 여 열거형에서 `celt`로 지정 된 "ICorDebugModule" 인스턴스의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95a1d-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95a1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="95a1d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95a1d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95a1d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="95a1d-106">진행 검색할 `ICorDebugModule` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="95a1d-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="95a1d-107">제한이 각각 `ICorDebugModule` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="95a1d-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="95a1d-108">제한이 실제로 반환 된 `ICorDebugModule` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95a1d-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="95a1d-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95a1d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95a1d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95a1d-110">Requirements</span></span>  
 <span data-ttu-id="95a1d-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95a1d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95a1d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95a1d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95a1d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95a1d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95a1d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95a1d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95a1d-115">참조</span><span class="sxs-lookup"><span data-stu-id="95a1d-115">See also</span></span>
