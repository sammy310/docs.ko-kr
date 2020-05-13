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
ms.openlocfilehash: 40de06d47654337542d2c80dc325f8201335312a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379147"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="03e8f-102">ICorDebugRegisterSet::GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="03e8f-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="03e8f-103">비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03e8f-104">구문</span><span class="sxs-lookup"><span data-stu-id="03e8f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03e8f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03e8f-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="03e8f-106">진행 검색할 레지스터 값을 지정 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="03e8f-107">각 비트는 레지스터에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="03e8f-108">비트가 1로 설정 된 경우 레지스터의 값이 검색 됩니다. 그렇지 않으면 레지스터의 값이 검색 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="03e8f-109">진행 검색할 레지스터 값의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="03e8f-110">제한이 `CORDB_REGISTER`각각 레지스터의 값을 받는 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03e8f-111">설명</span><span class="sxs-lookup"><span data-stu-id="03e8f-111">Remarks</span></span>  
 <span data-ttu-id="03e8f-112">배열의 크기는 비트 마스크에서 1로 설정 된 비트 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="03e8f-113">`regCount`매개 변수는 레지스터 값을 받는 버퍼의 요소 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="03e8f-114">`regCount`마스크가 나타내는 레지스터 수에 비해 값이 너무 작으면 집합에서 더 높은 번호의 레지스터가 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="03e8f-115">`regCount`값이 너무 크면 사용 하지 않는 `regBuffer` 요소가 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="03e8f-116">비트 마스크에서 사용할 수 없는 레지스터를 지정 하는 경우 `GetRegisters` 는 해당 레지스터에 대해 확정 되지 않은 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e8f-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03e8f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03e8f-117">Requirements</span></span>  
 <span data-ttu-id="03e8f-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e8f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03e8f-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03e8f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03e8f-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03e8f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03e8f-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03e8f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e8f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03e8f-122">See also</span></span>

- [<span data-ttu-id="03e8f-123">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03e8f-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="03e8f-124">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03e8f-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
