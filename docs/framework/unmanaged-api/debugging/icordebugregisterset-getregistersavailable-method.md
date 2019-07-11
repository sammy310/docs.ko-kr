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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d600b4687b86f5872f94a60ad3422be764cf5307
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747212"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="8beb0-102">ICorDebugRegisterSet::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="8beb0-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="8beb0-103">가져옵니다가 등록을 나타내는 비트 마스크 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8beb0-104">구문</span><span class="sxs-lookup"><span data-stu-id="8beb0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8beb0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8beb0-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="8beb0-106">[out] 현재 사용할 수 있는 레지스터가 있는 여부를 나타내는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8beb0-107">설명</span><span class="sxs-lookup"><span data-stu-id="8beb0-107">Remarks</span></span>  
 <span data-ttu-id="8beb0-108">레지스터 주어진된 상황에 대 한 해당 값을 확인할 수 없는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="8beb0-109">반환 된 마스크 각 등록에 대 한 하나의 비트가 포함 (1 << 등록 인덱스).</span><span class="sxs-lookup"><span data-stu-id="8beb0-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="8beb0-110">비트 값이 1 이면 레지스터를 사용할 수 또는 사용할 수 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8beb0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8beb0-111">Requirements</span></span>  
 <span data-ttu-id="8beb0-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8beb0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8beb0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8beb0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8beb0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8beb0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8beb0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8beb0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8beb0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8beb0-116">See also</span></span>

- [<span data-ttu-id="8beb0-117">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8beb0-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="8beb0-118">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8beb0-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
