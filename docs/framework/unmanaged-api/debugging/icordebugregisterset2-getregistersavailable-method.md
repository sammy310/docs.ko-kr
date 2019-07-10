---
title: ICorDebugRegisterSet2::GetRegistersAvailable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4ab49aaccd77fac497bd86413915e82c99ed3e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744912"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="d7633-102">ICorDebugRegisterSet2::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="d7633-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="d7633-103">사용 가능한 레지스터의 비트맵을 제공 하는 바이트 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7633-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7633-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7633-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7633-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="d7633-106">[in] `availableRegChunks` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="d7633-107">[out] 바이트 배열에는 각 비트 레지스터에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="d7633-108">레지스터 사용 가능한 경우 레지스터의 해당 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7633-109">설명</span><span class="sxs-lookup"><span data-stu-id="d7633-109">Remarks</span></span>  
 <span data-ttu-id="d7633-110">CorDebugRegister 열거형의 값을 다른 마이크로프로세서의 레지스터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="d7633-111">각 값의 상위 5 비트는 인덱스를 `availableRegChunks` 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="d7633-112">각 값의 세 가지 하위 비트는 인덱싱된 바이트에서 비트 위치를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="d7633-113">지정 된 `CorDebugRegister` 특정 레지스터를 마스크의 레지스터의 위치를 지정 하는 값은 다음과 같이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="d7633-114">정확한 바이트에 액세스 하는 데 필요한 인덱스를 추출 합니다 `availableRegChunks` 배열:</span><span class="sxs-lookup"><span data-stu-id="d7633-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="d7633-115">`CorDebugRegister` 값 >> 3</span><span class="sxs-lookup"><span data-stu-id="d7633-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="d7633-116">여기서 0 비트는 최하위 비트에서 인덱싱된 바이트 비트 위치를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7633-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="d7633-117">`CorDebugRegister` 값 및 7</span><span class="sxs-lookup"><span data-stu-id="d7633-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7633-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7633-118">Requirements</span></span>  
 <span data-ttu-id="d7633-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7633-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7633-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7633-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7633-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7633-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7633-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7633-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7633-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="d7633-123">See also</span></span>

- [<span data-ttu-id="d7633-124">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7633-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="d7633-125">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7633-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
