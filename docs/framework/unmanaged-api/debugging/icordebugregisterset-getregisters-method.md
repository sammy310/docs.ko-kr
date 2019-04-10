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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b417685361126951470571e2440cc842ab1c94fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153909"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="daaf7-102">ICorDebugRegisterSet::GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="daaf7-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="daaf7-103">(코드는 현재 실행 중인 컴퓨터)에서 각 레지스터의 값을 가져옵니다 비트 마스크에 의해 지정 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daaf7-104">구문</span><span class="sxs-lookup"><span data-stu-id="daaf7-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daaf7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daaf7-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="daaf7-106">[in] 검색할 값은 어느 레지스터를 지정 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="daaf7-107">각 비트 레지스터에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="daaf7-108">잠시으로 설정 된 하나 레지스터의 값 검색 됩니다. 그렇지 않은 경우 레지스터의 값 검색 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="daaf7-109">[in] 레지스터 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="daaf7-110">[out] 배열을 `CORDB_REGISTER` 레지스터의 값을 받으며 각 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daaf7-111">설명</span><span class="sxs-lookup"><span data-stu-id="daaf7-111">Remarks</span></span>  
 <span data-ttu-id="daaf7-112">배열의 크기는 비트 마스크에 하나로 설정 하는 비트 수와 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="daaf7-113">`regCount` 매개 변수 레지스터 값을 받을 버퍼에서 요소 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="daaf7-114">경우는 `regCount` 값이 너무 작아서 마스크에 의해 지정 된 레지스터 수, 레지스터 집합에서 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="daaf7-115">경우는 `regCount` 값이 너무 커서를 사용 하지 않는 `regBuffer` 요소를 수정 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="daaf7-116">비트 마스크를 사용할 수 없는 레지스터를 지정 하는 경우 `GetRegisters` 해당 레지스터에 대해 비활성화 상태 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="daaf7-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daaf7-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daaf7-117">Requirements</span></span>  
 <span data-ttu-id="daaf7-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="daaf7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daaf7-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daaf7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daaf7-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daaf7-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="daaf7-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="daaf7-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="daaf7-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="daaf7-122">See also</span></span>

- [<span data-ttu-id="daaf7-123">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daaf7-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="daaf7-124">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daaf7-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
