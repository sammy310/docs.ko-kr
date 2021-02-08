---
description: '다음에 대 한 자세한 정보: IDENTITY_ATTRIBUTE 구조체'
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
ms.openlocfilehash: 52610961ab202fc79351073eac1846a1a63889e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800177"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="58f65-103">IDENTITY_ATTRIBUTE 구조체</span><span class="sxs-lookup"><span data-stu-id="58f65-103">IDENTITY_ATTRIBUTE Structure</span></span>

<span data-ttu-id="58f65-104">[Idefinitionidentity](idefinitionidentity-interface.md) 인스턴스에 대 한 메타 데이터 특성 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-104">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f65-105">구문</span><span class="sxs-lookup"><span data-stu-id="58f65-105">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="58f65-106">구성원</span><span class="sxs-lookup"><span data-stu-id="58f65-106">Members</span></span>  
  
|<span data-ttu-id="58f65-107">멤버</span><span class="sxs-lookup"><span data-stu-id="58f65-107">Member</span></span>|<span data-ttu-id="58f65-108">설명</span><span class="sxs-lookup"><span data-stu-id="58f65-108">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="58f65-109">특성이 있는 네임 스페이스를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-109">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="58f65-110">특성의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-110">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="58f65-111">특성의 값을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-111">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58f65-112">설명</span><span class="sxs-lookup"><span data-stu-id="58f65-112">Remarks</span></span>  

 <span data-ttu-id="58f65-113">구조체에는 `IDENTITY_ATTRIBUTE` null로 끝나는 문자열에 대 한 세 개의 포인터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-113">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="58f65-114">이 세 문자열은 하나의 특성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-114">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="58f65-115">구조체의 인스턴스는 `IDENTITY_ATTRIBUTE` [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) 구조체의 인스턴스와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-115">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="58f65-116">구조체에는 `IDENTITY_ATTRIBUTE` 실제 문자열이 포함 되 고, 해당 `IDENTITY_ATTRIBUTE_BLOB` 구조에는 구조에 나열 된 세 개의 문자열로의 오프셋이 나열 `IDENTITY_ATTRIBUTE` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f65-116">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58f65-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58f65-117">Requirements</span></span>  

 <span data-ttu-id="58f65-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58f65-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58f65-119">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="58f65-119">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="58f65-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58f65-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f65-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58f65-121">See also</span></span>

- [<span data-ttu-id="58f65-122">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58f65-122">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="58f65-123">IDENTITY_ATTRIBUTE_BLOB 구조체</span><span class="sxs-lookup"><span data-stu-id="58f65-123">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="58f65-124">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="58f65-124">Fusion Structures</span></span>](fusion-structures.md)
