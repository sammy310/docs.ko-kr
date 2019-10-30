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
ms.openlocfilehash: 0666becb5a34688d3f4cf5bddd1e2fa71785b38a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139794"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="0131c-102">ICorDebugProcessEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="0131c-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="0131c-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugProcess 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0131c-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0131c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0131c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0131c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0131c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0131c-106">진행 검색할 `ICorDebugProcess` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0131c-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="0131c-107">제한이 각각 프로세스를 나타내는 `ICorDebugProcess` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0131c-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0131c-108">제한이 실제로 반환 된 `ICorDebugProcess` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0131c-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="0131c-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0131c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0131c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0131c-110">Requirements</span></span>  
 <span data-ttu-id="0131c-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0131c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0131c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0131c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0131c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0131c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0131c-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0131c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
