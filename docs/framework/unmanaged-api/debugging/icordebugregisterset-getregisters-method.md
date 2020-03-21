---
title: ICorDebugRegisterSet::GetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178538"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="c996e-102">ICorDebugRegisterSet::GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="c996e-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="c996e-103">비트 마스크에 의해 지정된 각 레지스터(현재 실행 중인 컴퓨터에서)의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c996e-104">구문</span><span class="sxs-lookup"><span data-stu-id="c996e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c996e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c996e-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="c996e-106">【인】 검색할 레지스터 값을 지정하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="c996e-107">각 비트는 레지스터에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="c996e-108">비트가 1로 설정되면 레지스터의 값이 검색됩니다. 그렇지 않으면 레지스터의 값이 검색되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="c996e-109">【인】 검색할 레지스터 값의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="c996e-110">【아웃】 레지스터의 `CORDB_REGISTER` 값을 받는 각각의 개체 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c996e-111">설명</span><span class="sxs-lookup"><span data-stu-id="c996e-111">Remarks</span></span>  
 <span data-ttu-id="c996e-112">배열의 크기는 비트 마스크에서 1로 설정된 비트 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="c996e-113">매개 `regCount` 변수는 레지스터 값을 수신할 버퍼의 요소 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="c996e-114">`regCount` 값이 마스크로 표시된 레지스터 수에 너무 작으면 번호가 높은 레지스터가 집합에서 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="c996e-115">`regCount` 값이 너무 크면 사용되지 `regBuffer` 않는 요소는 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="c996e-116">비트 마스크에서 사용할 수 없는 레지스터를 `GetRegisters` 지정하면 해당 레지스터에 대한 확정되지 않은 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c996e-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c996e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c996e-117">Requirements</span></span>  
 <span data-ttu-id="c996e-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c996e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c996e-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c996e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c996e-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c996e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c996e-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c996e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c996e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c996e-122">See also</span></span>

- [<span data-ttu-id="c996e-123">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c996e-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="c996e-124">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c996e-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
