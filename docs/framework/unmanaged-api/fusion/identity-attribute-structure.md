---
title: IDENTITY_ATTRIBUTE 구조체
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796491"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="6f241-102">IDENTITY_ATTRIBUTE 구조체</span><span class="sxs-lookup"><span data-stu-id="6f241-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="6f241-103">[Idefinitionidentity](idefinitionidentity-interface.md) 인스턴스에 대 한 메타 데이터 특성 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f241-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f241-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="6f241-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6f241-105">Members</span></span>  
  
|<span data-ttu-id="6f241-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6f241-106">Member</span></span>|<span data-ttu-id="6f241-107">설명</span><span class="sxs-lookup"><span data-stu-id="6f241-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="6f241-108">특성이 있는 네임 스페이스를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="6f241-109">특성의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="6f241-110">특성의 값을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f241-111">설명</span><span class="sxs-lookup"><span data-stu-id="6f241-111">Remarks</span></span>  
 <span data-ttu-id="6f241-112">구조체 `IDENTITY_ATTRIBUTE` 에는 null로 끝나는 문자열에 대 한 세 개의 포인터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="6f241-113">이 세 문자열은 하나의 특성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="6f241-114">`IDENTITY_ATTRIBUTE` 구조체의 인스턴스는 [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) 구조체의 인스턴스와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f241-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="6f241-115">구조체에는 실제 문자열이 포함 되 고, 해당 `IDENTITY_ATTRIBUTE_BLOB` 구조에는 `IDENTITY_ATTRIBUTE` 구조에 나열 된 세 개의 문자열로의 오프셋이 나열 됩니다. `IDENTITY_ATTRIBUTE`</span><span class="sxs-lookup"><span data-stu-id="6f241-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f241-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f241-116">Requirements</span></span>  
 <span data-ttu-id="6f241-117">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f241-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f241-118">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="6f241-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6f241-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f241-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f241-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="6f241-120">See also</span></span>

- [<span data-ttu-id="6f241-121">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f241-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="6f241-122">IDENTITY_ATTRIBUTE_BLOB 구조체</span><span class="sxs-lookup"><span data-stu-id="6f241-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="6f241-123">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="6f241-123">Fusion Structures</span></span>](fusion-structures.md)
