---
title: ICorDebugRegisterSet2::GetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2dc1064656f3493db78d858cf1e86db0cb83d6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782865"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="51f93-102">ICorDebugRegisterSet2::GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="51f93-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="51f93-103">(코드를 현재 실행 중인 플랫폼)에 대 한 각 레지스터의 값을 가져옵니다 지정 된 비트 마스크에 의해 지정 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f93-104">구문</span><span class="sxs-lookup"><span data-stu-id="51f93-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51f93-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51f93-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="51f93-106">[in] 크기 (바이트)의는 `mask` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="51f93-107">[in] 바이트 배열에는 각 비트 레지스터에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="51f93-108">이 비트가 1 인 경우 해당 레지스터의 값이 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="51f93-109">[in] 레지스터 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="51f93-110">[out] 배열을 `CORDB_REGISTER` 레지스터의 값을 받습니다. 각 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51f93-111">설명</span><span class="sxs-lookup"><span data-stu-id="51f93-111">Remarks</span></span>  
 <span data-ttu-id="51f93-112">`GetRegisters` 메서드 마스크에 의해 지정 된 레지스터에서 값의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="51f93-113">배열에 마스크 비트가 설정 되지 않은 레지스터의 값을 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="51f93-114">따라서 크기는 `regBuffer` 배열 마스크의 1의 수가 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="51f93-115">경우 변수의 `regCount` 마스크를 레지스터의 값에 의해 지정 된 레지스터 수 집합에서 잘립니다에 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="51f93-116">하는 경우 `regCount` 너무 커서를 사용 하지 않는 `regBuffer` 요소를 수정 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="51f93-117">마스크에 의해를 사용할 수 없는 레지스터를 지정 하는 경우 해당 등록에 대 한 비활성화 상태 값을 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="51f93-118">`ICorDebugRegisterSet2::GetRegisters` 메서드는 64 개 등록 하는 플랫폼에 대 한 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="51f93-119">예를 들어, IA64 있으므로 128 일반 용도 레지스터와 부동 소수점 레지스터 128 비트 마스크에 64 비트 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="51f93-120">X86와 같은 플랫폼의 경우에는 64 개 이상의 레지스터가 없는 경우는 `GetRegisters` 메서드 실제로 변환 하는 바이트를 `mask` 바이트 배열에는 `ULONG64` 를 호출 하는 [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) 를 사용 하는 메서드는 `ULONG64` 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="51f93-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f93-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51f93-121">Requirements</span></span>  
 <span data-ttu-id="51f93-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51f93-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f93-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51f93-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51f93-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51f93-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51f93-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f93-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f93-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="51f93-126">See also</span></span>

- [<span data-ttu-id="51f93-127">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51f93-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="51f93-128">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51f93-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
