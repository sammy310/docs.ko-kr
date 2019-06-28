---
title: ICorDebugProcessEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9f32b554de191ff84e7c319e2a00e3cd0610a9f
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422193"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="cae24-102">ICorDebugProcessEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="cae24-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="cae24-103">ICorDebugProcess 인스턴스 수가 지정 된 현재 위치부터 시작 하는 열거형에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cae24-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae24-104">구문</span><span class="sxs-lookup"><span data-stu-id="cae24-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cae24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cae24-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cae24-106">[in] 수가 `ICorDebugProcess` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cae24-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="cae24-107">[out] 각각 가리키는 포인터 배열을 `ICorDebugProcess` 프로세스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cae24-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cae24-108">[out] 개수에 대 한 포인터 `ICorDebugProcess` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="cae24-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="cae24-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="cae24-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae24-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cae24-110">Requirements</span></span>  
 <span data-ttu-id="cae24-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cae24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cae24-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cae24-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cae24-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cae24-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cae24-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cae24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
