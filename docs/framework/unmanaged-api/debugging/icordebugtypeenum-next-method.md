---
title: ICorDebugTypeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: fc205e347fc39fd486d9b8a3fb256a5d29a980a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110059"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="e3926-102">ICorDebugTypeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="e3926-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="e3926-103">현재 위치에서 시작 하 여 열거형에서 `celt`로 지정 된 "ICorDebugType" 인스턴스의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3926-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3926-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3926-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3926-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3926-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e3926-106">진행 검색할 `ICorDebugType` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3926-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="e3926-107">제한이 각각 `ICorDebugType` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e3926-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e3926-108">제한이 실제로 반환 된 `ICorDebugType` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e3926-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="e3926-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3926-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3926-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3926-110">Requirements</span></span>  
 <span data-ttu-id="e3926-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3926-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3926-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3926-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3926-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3926-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3926-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3926-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3926-115">참조</span><span class="sxs-lookup"><span data-stu-id="e3926-115">See also</span></span>
