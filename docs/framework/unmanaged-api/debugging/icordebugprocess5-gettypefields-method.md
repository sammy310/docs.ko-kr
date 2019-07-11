---
title: ICorDebugProcess5::GetTypeFields 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d413b17da0b6f241f9078bfeb3bd035d4d07a81
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767634"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="7b03c-102">ICorDebugProcess5::GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="7b03c-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="7b03c-103">형식에 속하는 필드에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b03c-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b03c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b03c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b03c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b03c-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="7b03c-106">[in] 식별자 인 필드 정보를 검색할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7b03c-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="7b03c-107">[in] 수가 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 필드 정보를 검색할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7b03c-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="7b03c-108">[out] 배열을 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 형식에 속하는 필드에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7b03c-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="7b03c-109">[out] 개수에 대 한 포인터 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 에 포함 된 개체 `fields`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b03c-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b03c-110">설명</span><span class="sxs-lookup"><span data-stu-id="7b03c-110">Remarks</span></span>  
 <span data-ttu-id="7b03c-111">`celt` 필드를 채우는 메서드를 사용 하 여 필드 정보를 가져올 수를 지정 하는 매개 변수 `fields`의 값과 일치 해야 합니다 `COR_TYPE_LAYOUT::numFields` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="7b03c-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b03c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b03c-112">Requirements</span></span>  
 <span data-ttu-id="7b03c-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b03c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b03c-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b03c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b03c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b03c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b03c-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b03c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b03c-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b03c-117">See also</span></span>

- [<span data-ttu-id="7b03c-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b03c-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="7b03c-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b03c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
