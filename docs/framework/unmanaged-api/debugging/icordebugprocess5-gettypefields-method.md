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
ms.openlocfilehash: 29006eba3d3a523fd24a461207ab12222a639782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178599"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="d455d-102">ICorDebugProcess5::GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="d455d-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="d455d-103">형식에 속하는 필드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d455d-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d455d-104">구문</span><span class="sxs-lookup"><span data-stu-id="d455d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d455d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d455d-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="d455d-106">【인】 필드 정보가 검색되는 형식의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d455d-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="d455d-107">【인】 필드 정보를 검색할 [COR_FIELD](cor-field-structure.md) 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d455d-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="d455d-108">【아웃】 형식에 속하는 필드에 대한 정보를 제공하는 [COR_FIELD](cor-field-structure.md) 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d455d-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="d455d-109">【아웃】 에 포함된 [COR_FIELD](cor-field-structure.md) 개체 수에 `fields`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d455d-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d455d-110">설명</span><span class="sxs-lookup"><span data-stu-id="d455d-110">Remarks</span></span>  
 <span data-ttu-id="d455d-111">메서드가 `celt` 채우는 `fields`데 사용하는 필드 정보가 필드의 값과 일치해야 하는 필드 수를 지정하는 매개 변수입니다. `COR_TYPE_LAYOUT::numFields`</span><span class="sxs-lookup"><span data-stu-id="d455d-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d455d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d455d-112">Requirements</span></span>  
 <span data-ttu-id="d455d-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d455d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d455d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d455d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d455d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d455d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d455d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d455d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d455d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d455d-117">See also</span></span>

- [<span data-ttu-id="d455d-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d455d-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d455d-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d455d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
