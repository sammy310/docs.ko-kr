---
title: COR_TYPE_LAYOUT 구조체
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
ms.openlocfilehash: f33c8f5cf218979404063342d9b1cc5123839f83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726329"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="da4f7-102">COR_TYPE_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="da4f7-102">COR_TYPE_LAYOUT Structure</span></span>

<span data-ttu-id="da4f7-103">메모리 내 개체의 레이아웃에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da4f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="da4f7-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="da4f7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="da4f7-105">Members</span></span>  
  
|<span data-ttu-id="da4f7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="da4f7-106">Member</span></span>|<span data-ttu-id="da4f7-107">설명</span><span class="sxs-lookup"><span data-stu-id="da4f7-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="da4f7-108">이 형식에 대 한 부모 형식의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="da4f7-109">유형 id가에 해당 하는 경우 NULL 유형 id (token1 = 0, token2 = 0)가 됩니다 <xref:System.Object?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="da4f7-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="da4f7-110">이 형식의 개체에 대 한 기본 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-110">The base size of an object of this type.</span></span> <span data-ttu-id="da4f7-111">가변 크기가 아닌 개체의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="da4f7-112">이 형식의 개체에 포함 된 필드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="da4f7-113">이 형식이 boxed 이면 개체 필드의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="da4f7-114">이 필드는 기본 형식 및 구조체와 같은 값 형식에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="da4f7-115">이 형식이 속한 CorElementType입니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da4f7-116">설명</span><span class="sxs-lookup"><span data-stu-id="da4f7-116">Remarks</span></span>  

 <span data-ttu-id="da4f7-117">`numFields`가 0 보다 큰 경우 [ICorDebugProcess5:: gettypefields](icordebugprocess5-gettypefields-method.md) 메서드를 호출 하 여이 형식의 필드에 대 한 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="da4f7-118">`type`가 `ELEMENT_TYPE_STRING` , 또는 이면 `ELEMENT_TYPE_ARRAY` `ELEMENT_TYPE_SZARRAY` 이 형식의 개체 크기는 변수이 고 [COR_TYPEID](cor-typeid-structure.md) 구조체를 [ICorDebugProcess5:: getarraylayout](icordebugprocess5-getarraylayout-method.md) 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4f7-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da4f7-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da4f7-119">Requirements</span></span>  

 <span data-ttu-id="da4f7-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da4f7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da4f7-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da4f7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da4f7-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da4f7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da4f7-123">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da4f7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4f7-124">참조</span><span class="sxs-lookup"><span data-stu-id="da4f7-124">See also</span></span>

- [<span data-ttu-id="da4f7-125">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="da4f7-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="da4f7-126">디버깅</span><span class="sxs-lookup"><span data-stu-id="da4f7-126">Debugging</span></span>](index.md)
