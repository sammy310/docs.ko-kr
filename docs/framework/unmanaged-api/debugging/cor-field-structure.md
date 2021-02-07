---
description: '다음에 대 한 자세한 정보: COR_FIELD 구조체'
title: COR_FIELD 구조체
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
ms.openlocfilehash: a3e9dcc2a5c3bb2abae42dab4292c1d285df5ad7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747113"
---
# <a name="cor_field-structure"></a><span data-ttu-id="9fb18-103">COR_FIELD 구조체</span><span class="sxs-lookup"><span data-stu-id="9fb18-103">COR_FIELD Structure</span></span>

<span data-ttu-id="9fb18-104">개체의 필드에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb18-104">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fb18-105">구문</span><span class="sxs-lookup"><span data-stu-id="9fb18-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="9fb18-106">구성원</span><span class="sxs-lookup"><span data-stu-id="9fb18-106">Members</span></span>  
  
|<span data-ttu-id="9fb18-107">멤버</span><span class="sxs-lookup"><span data-stu-id="9fb18-107">Member</span></span>|<span data-ttu-id="9fb18-108">설명</span><span class="sxs-lookup"><span data-stu-id="9fb18-108">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="9fb18-109">`mdFieldDef`필드 정보를 가져오는 데 사용할 수 있는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb18-109">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="9fb18-110">개체의 필드 데이터에 대 한 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb18-110">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="9fb18-111">이 필드의 형식을 식별 하는 [COR_TYPEID](cor-typeid-structure.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb18-111">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="9fb18-112">필드의 유형을 나타내는 CorElementType 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb18-112">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fb18-113">설명</span><span class="sxs-lookup"><span data-stu-id="9fb18-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fb18-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fb18-114">Requirements</span></span>  

 <span data-ttu-id="9fb18-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb18-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fb18-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fb18-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fb18-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fb18-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fb18-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fb18-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb18-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fb18-119">See also</span></span>

- [<span data-ttu-id="9fb18-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="9fb18-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="9fb18-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="9fb18-121">Debugging</span></span>](index.md)
