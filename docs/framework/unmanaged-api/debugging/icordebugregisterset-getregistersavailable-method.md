---
description: '자세히 알아보기: ICorDebugRegisterSet:: GetRegistersAvailable 메서드'
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
ms.openlocfilehash: a1727c594733fe6529fe1e78f341723623b68be2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690823"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="b01c6-103">ICorDebugRegisterSet::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="b01c6-103">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>

<span data-ttu-id="b01c6-104">이 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 에서 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b01c6-104">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b01c6-105">구문</span><span class="sxs-lookup"><span data-stu-id="b01c6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b01c6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b01c6-106">Parameters</span></span>  

 `pAvailable`  
 <span data-ttu-id="b01c6-107">제한이 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="b01c6-107">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b01c6-108">설명</span><span class="sxs-lookup"><span data-stu-id="b01c6-108">Remarks</span></span>  

 <span data-ttu-id="b01c6-109">지정 된 상황에 대해 해당 값을 확인할 수 없는 경우에는 레지스터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b01c6-109">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="b01c6-110">반환 된 마스크에는 각 레지스터의 비트 (1 << 레지스터 인덱스)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01c6-110">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="b01c6-111">레지스터를 사용할 수 있으면 비트 값은 1이 고, 사용할 수 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="b01c6-111">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b01c6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b01c6-112">Requirements</span></span>  

 <span data-ttu-id="b01c6-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b01c6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b01c6-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b01c6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b01c6-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b01c6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b01c6-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b01c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b01c6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b01c6-117">See also</span></span>

- [<span data-ttu-id="b01c6-118">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b01c6-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="b01c6-119">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b01c6-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
