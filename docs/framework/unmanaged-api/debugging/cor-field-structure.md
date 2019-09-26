---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f857f773f02da25fe6650000be777b8290f5af91
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274053"
---
# <a name="cor_field-structure"></a><span data-ttu-id="cd7d6-102">COR_FIELD 구조체</span><span class="sxs-lookup"><span data-stu-id="cd7d6-102">COR_FIELD Structure</span></span>
<span data-ttu-id="cd7d6-103">개체의 필드에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cd7d6-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd7d6-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="cd7d6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cd7d6-105">Members</span></span>  
  
|<span data-ttu-id="cd7d6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cd7d6-106">Member</span></span>|<span data-ttu-id="cd7d6-107">설명</span><span class="sxs-lookup"><span data-stu-id="cd7d6-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="cd7d6-108">필드 정보를 가져오는 데 사용할 수 있는 토큰입니다.`mdFieldDef`</span><span class="sxs-lookup"><span data-stu-id="cd7d6-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="cd7d6-109">개체의 필드 데이터에 대 한 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="cd7d6-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="cd7d6-110">이 필드의 유형을 식별 하는 [COR_TYPEID](cor-typeid-structure.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cd7d6-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="cd7d6-111">필드의 유형을 나타내는 CorElementType 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cd7d6-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd7d6-112">설명</span><span class="sxs-lookup"><span data-stu-id="cd7d6-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd7d6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd7d6-113">Requirements</span></span>  
 <span data-ttu-id="cd7d6-114">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd7d6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd7d6-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd7d6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd7d6-116">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd7d6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd7d6-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd7d6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7d6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd7d6-118">See also</span></span>

- [<span data-ttu-id="cd7d6-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="cd7d6-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="cd7d6-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="cd7d6-120">Debugging</span></span>](index.md)
