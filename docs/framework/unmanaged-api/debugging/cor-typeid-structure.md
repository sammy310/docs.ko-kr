---
title: COR_TYPEID 구조체
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 426420175a7d05f39859b9e217a888a8c01b6d63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740517"
---
# <a name="cortypeid-structure"></a><span data-ttu-id="1056a-102">COR_TYPEID 구조체</span><span class="sxs-lookup"><span data-stu-id="1056a-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="1056a-103">유형 식별자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1056a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1056a-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="1056a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1056a-105">Members</span></span>  
  
|<span data-ttu-id="1056a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1056a-106">Member</span></span>|<span data-ttu-id="1056a-107">Description</span><span class="sxs-lookup"><span data-stu-id="1056a-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="1056a-108">첫 번째 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="1056a-109">두 번째 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1056a-110">설명</span><span class="sxs-lookup"><span data-stu-id="1056a-110">Remarks</span></span>  
 <span data-ttu-id="1056a-111">`COR_TYPEID` 다양 한 개체를 가비지 수집에 대 한 정보를 제공 하는 방법 디버깅에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="1056a-112">그 다음 전달할 수 있습니다 인수로 서 해당 항목에 대 한 추가 정보를 제공 하는 다른 디버깅 방법.</span><span class="sxs-lookup"><span data-stu-id="1056a-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="1056a-113">예를 들어, 열거 하 여는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 개체를 개별 검색할 수 있습니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개별 관리 되는 힙의 개체를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="1056a-114">전달할 수 있습니다는 `COR_TYPEID` 에서 값을 `COR_HEAPOBJECT.type` 필드를 합니다 [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 개체에 대 한 형식 정보를 제공 하는 ICorDebugType 개체를 검색 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="1056a-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="1056a-115">`COR_TYPEID` 불투명 개체는 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="1056a-116">개별 필드를 액세스 하거나 조작할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="1056a-117">유일한 용도으로 제공 되는 식별자로는 `out` 수 있는 메서드 호출에 매개 변수를 전달할 수 다른 방법 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1056a-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1056a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1056a-118">Requirements</span></span>  
 <span data-ttu-id="1056a-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1056a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1056a-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1056a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1056a-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1056a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1056a-122">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1056a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1056a-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="1056a-123">See also</span></span>

- [<span data-ttu-id="1056a-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="1056a-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="1056a-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="1056a-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
