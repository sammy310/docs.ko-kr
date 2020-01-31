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
ms.openlocfilehash: 54a5fb50a0177fe9886582c112f16ce871ea9df4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792069"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="122d4-102">ICorDebugRegisterSet2::GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="122d4-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="122d4-103">지정 된 비트 마스크로 지정 된 각 레지스터의 값 (코드가 현재 실행 중인 플랫폼의 경우)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="122d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="122d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="122d4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="122d4-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="122d4-106">진행 `mask` 배열의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="122d4-107">진행 각 비트가 레지스터에 해당 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="122d4-108">비트가 1 이면 해당 레지스터의 값이 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="122d4-109">진행 검색할 레지스터 값의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="122d4-110">제한이 각각 레지스터의 값을 수신 하는 `CORDB_REGISTER` 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="122d4-111">주의</span><span class="sxs-lookup"><span data-stu-id="122d4-111">Remarks</span></span>  
 <span data-ttu-id="122d4-112">`GetRegisters` 메서드는 마스크로 지정 된 레지스터에서 값의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="122d4-113">배열에 해당 마스크 비트가 설정 되지 않은 레지스터의 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="122d4-114">따라서 `regBuffer` 배열의 크기는 마스크에 있는 1의 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="122d4-115">마스크가 나타내는 레지스터 수에 대해 `regCount` 값이 너무 작으면 집합에서 더 높은 숫자의 레지스터 값이 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="122d4-116">`regCount` 너무 크면 사용 하지 않는 `regBuffer` 요소가 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="122d4-117">사용할 수 없는 레지스터가 마스크로 표시 되 면 해당 레지스터에 대해 결정 되지 않은 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="122d4-118">`ICorDebugRegisterSet2::GetRegisters` 메서드는 레지스터가 64 개를 초과 하는 플랫폼에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="122d4-119">예를 들어 IA64에는 128 범용 레지스터와 128 부동 소수점 레지스터가 있으므로 비트 마스크에 64 비트 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="122d4-120">64 개 이상의 레지스터가 없는 경우 x86 등의 플랫폼에서와 같이 `GetRegisters` 메서드는 실제로 `mask` 바이트 배열의 바이트를 `ULONG64` 변환한 다음 [ICorDebugRegisterSet:: GetRegisters](icordebugregisterset-getregisters-method.md) 메서드를 호출 합니다 .이 메서드는 `ULONG64` 마스크를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="122d4-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="122d4-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="122d4-121">Requirements</span></span>  
 <span data-ttu-id="122d4-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="122d4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="122d4-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="122d4-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="122d4-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="122d4-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="122d4-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="122d4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122d4-126">참조</span><span class="sxs-lookup"><span data-stu-id="122d4-126">See also</span></span>

- [<span data-ttu-id="122d4-127">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="122d4-127">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="122d4-128">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="122d4-128">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
