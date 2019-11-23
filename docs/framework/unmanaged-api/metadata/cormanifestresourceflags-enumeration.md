---
title: CorManifestResourceFlags 열거형
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
ms.openlocfilehash: 35966e25d02bd6f1a9bdd21ad4e9cc44b7bb480e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450250"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="ec63d-102">CorManifestResourceFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="ec63d-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="ec63d-103">Indicates the visibility of resources encoded in an assembly manifest.</span><span class="sxs-lookup"><span data-stu-id="ec63d-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec63d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec63d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ec63d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ec63d-105">Members</span></span>  
  
|<span data-ttu-id="ec63d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ec63d-106">Member</span></span>|<span data-ttu-id="ec63d-107">설명</span><span class="sxs-lookup"><span data-stu-id="ec63d-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="ec63d-108">예약됨.</span><span class="sxs-lookup"><span data-stu-id="ec63d-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="ec63d-109">The resources are public.</span><span class="sxs-lookup"><span data-stu-id="ec63d-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="ec63d-110">The resources are private.</span><span class="sxs-lookup"><span data-stu-id="ec63d-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec63d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec63d-111">Requirements</span></span>  
 <span data-ttu-id="ec63d-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec63d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec63d-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ec63d-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ec63d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec63d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec63d-115">참조</span><span class="sxs-lookup"><span data-stu-id="ec63d-115">See also</span></span>

- [<span data-ttu-id="ec63d-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ec63d-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
