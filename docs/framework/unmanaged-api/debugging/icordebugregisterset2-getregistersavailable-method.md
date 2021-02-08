---
description: '자세히 알아보기: ICorDebugRegisterSet2:: GetRegistersAvailable 메서드'
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
ms.openlocfilehash: 3839647e69efd63aefd1aa154c457f292e684336
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790726"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="407fd-103">ICorDebugRegisterSet2::GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="407fd-103">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>

<span data-ttu-id="407fd-104">사용 가능한 레지스터의 비트맵을 제공 하는 바이트 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-104">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="407fd-105">구문</span><span class="sxs-lookup"><span data-stu-id="407fd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="407fd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="407fd-106">Parameters</span></span>  

 `numChunks`  
 <span data-ttu-id="407fd-107">[in] `availableRegChunks` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-107">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="407fd-108">제한이 각 비트가 레지스터에 해당 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-108">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="407fd-109">레지스터를 사용할 수 있는 경우 레지스터의 해당 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-109">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="407fd-110">설명</span><span class="sxs-lookup"><span data-stu-id="407fd-110">Remarks</span></span>  

 <span data-ttu-id="407fd-111">CorDebugRegister 열거형의 값은 다른 마이크로프로세서의 레지스터를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-111">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="407fd-112">각 값의 상위 5 비트는 `availableRegChunks` 바이트 배열에 대 한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-112">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="407fd-113">각 값의 하위 3 비트는 인덱싱된 바이트 내의 비트 위치를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-113">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="407fd-114">`CorDebugRegister`특정 레지스터를 지정 하는 값을 지정 하는 경우 마스크의 레지스터 위치는 다음과 같이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-114">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="407fd-115">배열의 올바른 바이트에 액세스 하는 데 필요한 인덱스를 추출 합니다 `availableRegChunks` .</span><span class="sxs-lookup"><span data-stu-id="407fd-115">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="407fd-116">`CorDebugRegister` 값 >> 3</span><span class="sxs-lookup"><span data-stu-id="407fd-116">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="407fd-117">인덱싱된 바이트 내에서 비트 위치를 추출 합니다. 여기서 bit 0은 최하위 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="407fd-117">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="407fd-118">`CorDebugRegister` 값 & 7</span><span class="sxs-lookup"><span data-stu-id="407fd-118">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="407fd-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="407fd-119">Requirements</span></span>  

 <span data-ttu-id="407fd-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="407fd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="407fd-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="407fd-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="407fd-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="407fd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="407fd-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="407fd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="407fd-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="407fd-124">See also</span></span>

- [<span data-ttu-id="407fd-125">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="407fd-125">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="407fd-126">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="407fd-126">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
