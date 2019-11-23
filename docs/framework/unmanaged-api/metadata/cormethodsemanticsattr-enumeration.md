---
title: CorMethodSemanticsAttr 열거형
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: bab215a8221696a0e43e228278085fcef52a40e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442816"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="14799-102">CorMethodSemanticsAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="14799-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="14799-103">메서드와 관련 속성 또는 이벤트 간의 관계를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="14799-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14799-104">구문</span><span class="sxs-lookup"><span data-stu-id="14799-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="14799-105">멤버</span><span class="sxs-lookup"><span data-stu-id="14799-105">Members</span></span>  
  
|<span data-ttu-id="14799-106">멤버</span><span class="sxs-lookup"><span data-stu-id="14799-106">Member</span></span>|<span data-ttu-id="14799-107">설명</span><span class="sxs-lookup"><span data-stu-id="14799-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="14799-108">Specifies that the method is a `set` accessor for a property.</span><span class="sxs-lookup"><span data-stu-id="14799-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="14799-109">Specifies that the method is a `get` accessor for a property.</span><span class="sxs-lookup"><span data-stu-id="14799-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="14799-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span><span class="sxs-lookup"><span data-stu-id="14799-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="14799-111">Specifies that the method adds handler methods for an event.</span><span class="sxs-lookup"><span data-stu-id="14799-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="14799-112">Specifies that the method removes handler methods for an event.</span><span class="sxs-lookup"><span data-stu-id="14799-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="14799-113">Specifies that the method raises an event.</span><span class="sxs-lookup"><span data-stu-id="14799-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14799-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14799-114">Requirements</span></span>  
 <span data-ttu-id="14799-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14799-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14799-116">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="14799-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="14799-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14799-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14799-118">참조</span><span class="sxs-lookup"><span data-stu-id="14799-118">See also</span></span>

- [<span data-ttu-id="14799-119">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="14799-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
