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
ms.openlocfilehash: b137b956e06a2b2954918e4024860f9b234e7583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792102"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="057d7-102">ICorDebugRegisterSet::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="057d7-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="057d7-103">이 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 에서 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="057d7-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="057d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="057d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="057d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="057d7-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="057d7-106">제한이 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="057d7-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="057d7-107">주의</span><span class="sxs-lookup"><span data-stu-id="057d7-107">Remarks</span></span>  
 <span data-ttu-id="057d7-108">지정 된 상황에 대해 해당 값을 확인할 수 없는 경우에는 레지스터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="057d7-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="057d7-109">반환 된 마스크에는 각 레지스터의 비트 (1 < 레지스터 인덱스 <)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="057d7-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="057d7-110">레지스터를 사용할 수 있으면 비트 값은 1이 고, 사용할 수 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="057d7-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="057d7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="057d7-111">Requirements</span></span>  
 <span data-ttu-id="057d7-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="057d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="057d7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="057d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="057d7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="057d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="057d7-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="057d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="057d7-116">참조</span><span class="sxs-lookup"><span data-stu-id="057d7-116">See also</span></span>

- [<span data-ttu-id="057d7-117">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="057d7-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="057d7-118">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="057d7-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
