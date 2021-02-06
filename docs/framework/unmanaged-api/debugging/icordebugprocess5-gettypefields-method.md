---
description: '자세히 알아보기: ICorDebugProcess5:: GetTypeFields 메서드'
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
ms.openlocfilehash: bdbb0be76400262d83876b9fc37cc4f00eb34e43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649821"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="3a945-103">ICorDebugProcess5::GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="3a945-103">ICorDebugProcess5::GetTypeFields Method</span></span>

<span data-ttu-id="3a945-104">형식에 속하는 필드에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a945-104">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a945-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a945-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a945-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a945-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="3a945-107">진행 필드 정보를 검색할 형식의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a945-107">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="3a945-108">진행 필드 정보를 검색할 [COR_FIELD](cor-field-structure.md) 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a945-108">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="3a945-109">제한이 형식에 속하는 필드에 대 한 정보를 제공 하는 [COR_FIELD](cor-field-structure.md) 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3a945-109">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="3a945-110">제한이 에 포함 된 [COR_FIELD](cor-field-structure.md) 개체 수에 대 한 포인터입니다 `fields` .</span><span class="sxs-lookup"><span data-stu-id="3a945-110">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a945-111">설명</span><span class="sxs-lookup"><span data-stu-id="3a945-111">Remarks</span></span>  

 <span data-ttu-id="3a945-112">`celt`매개 변수는 메서드가 필드 정보를 채우는 데 사용 하는 필드의 수를 지정 합니다 `fields` .이 필드의 값은 필드의 값에 해당 해야 합니다 `COR_TYPE_LAYOUT::numFields` .</span><span class="sxs-lookup"><span data-stu-id="3a945-112">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a945-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a945-113">Requirements</span></span>  

 <span data-ttu-id="3a945-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a945-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a945-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a945-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a945-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a945-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a945-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a945-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a945-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a945-118">See also</span></span>

- [<span data-ttu-id="3a945-119">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a945-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="3a945-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a945-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
