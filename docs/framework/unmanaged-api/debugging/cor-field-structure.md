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
ms.openlocfilehash: 78e34d9d33d34047e3ebd2effb4894bc7b709585
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132352"
---
# <a name="cor_field-structure"></a><span data-ttu-id="fcb3f-102">COR_FIELD 구조체</span><span class="sxs-lookup"><span data-stu-id="fcb3f-102">COR_FIELD Structure</span></span>
<span data-ttu-id="fcb3f-103">개체의 필드에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fcb3f-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb3f-104">구문</span><span class="sxs-lookup"><span data-stu-id="fcb3f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="fcb3f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fcb3f-105">Members</span></span>  
  
|<span data-ttu-id="fcb3f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fcb3f-106">Member</span></span>|<span data-ttu-id="fcb3f-107">설명</span><span class="sxs-lookup"><span data-stu-id="fcb3f-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="fcb3f-108">필드 정보를 가져오는 데 사용할 수 있는 `mdFieldDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb3f-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="fcb3f-109">개체의 필드 데이터에 대 한 오프셋 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb3f-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="fcb3f-110">이 필드의 유형을 식별 하는 [COR_TYPEID](cor-typeid-structure.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb3f-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="fcb3f-111">필드의 유형을 나타내는 CorElementType 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb3f-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcb3f-112">주의</span><span class="sxs-lookup"><span data-stu-id="fcb3f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcb3f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fcb3f-113">Requirements</span></span>  
 <span data-ttu-id="fcb3f-114">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcb3f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcb3f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcb3f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcb3f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcb3f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcb3f-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcb3f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb3f-118">참조</span><span class="sxs-lookup"><span data-stu-id="fcb3f-118">See also</span></span>

- [<span data-ttu-id="fcb3f-119">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="fcb3f-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="fcb3f-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="fcb3f-120">Debugging</span></span>](index.md)
