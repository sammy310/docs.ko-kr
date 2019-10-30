---
title: ICorDebugRegisterSet::GetRegistersAvailable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: 9d8bd6ab13fa408fd7390aaeb76baee274742f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137698"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="d303b-102">ICorDebugRegisterSet::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="d303b-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="d303b-103">이 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 에서 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d303b-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d303b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d303b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d303b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d303b-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="d303b-106">제한이 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="d303b-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d303b-107">주의</span><span class="sxs-lookup"><span data-stu-id="d303b-107">Remarks</span></span>  
 <span data-ttu-id="d303b-108">지정 된 상황에 대해 해당 값을 확인할 수 없는 경우에는 레지스터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d303b-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="d303b-109">반환 된 마스크에는 각 레지스터의 비트 (1 < 레지스터 인덱스 <)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d303b-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="d303b-110">레지스터를 사용할 수 있으면 비트 값은 1이 고, 사용할 수 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d303b-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d303b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d303b-111">Requirements</span></span>  
 <span data-ttu-id="d303b-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d303b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d303b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d303b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d303b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d303b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d303b-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d303b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d303b-116">참조</span><span class="sxs-lookup"><span data-stu-id="d303b-116">See also</span></span>

- [<span data-ttu-id="d303b-117">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d303b-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="d303b-118">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d303b-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
