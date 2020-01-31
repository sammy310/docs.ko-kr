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
ms.openlocfilehash: 737993ac80b26d490915af3e97fd6a9552246aee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792116"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="9e5ec-102">ICorDebugRegisterSet::GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="9e5ec-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="9e5ec-103">비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e5ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e5ec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e5ec-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="9e5ec-106">진행 검색할 레지스터 값을 지정 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="9e5ec-107">각 비트는 레지스터에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="9e5ec-108">비트가 1로 설정 된 경우 레지스터의 값이 검색 됩니다. 그렇지 않으면 레지스터의 값이 검색 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="9e5ec-109">진행 검색할 레지스터 값의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="9e5ec-110">제한이 각각 레지스터의 값을 수신 하는 `CORDB_REGISTER` 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e5ec-111">주의</span><span class="sxs-lookup"><span data-stu-id="9e5ec-111">Remarks</span></span>  
 <span data-ttu-id="9e5ec-112">배열의 크기는 비트 마스크에서 1로 설정 된 비트 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="9e5ec-113">`regCount` 매개 변수는 레지스터 값을 받을 버퍼의 요소 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="9e5ec-114">마스크가 나타내는 레지스터 수에 대해 `regCount` 값이 너무 작으면 집합에서 더 높은 번호의 레지스터가 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="9e5ec-115">`regCount` 값이 너무 크면 사용 하지 않는 `regBuffer` 요소가 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="9e5ec-116">비트 마스크에서 사용할 수 없는 레지스터를 지정 하는 경우 `GetRegisters`은 해당 레지스터에 대해 결정 되지 않은 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e5ec-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e5ec-117">Requirements</span></span>  
 <span data-ttu-id="9e5ec-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e5ec-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e5ec-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e5ec-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e5ec-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e5ec-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e5ec-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e5ec-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5ec-122">참조</span><span class="sxs-lookup"><span data-stu-id="9e5ec-122">See also</span></span>

- [<span data-ttu-id="9e5ec-123">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e5ec-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="9e5ec-124">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e5ec-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
