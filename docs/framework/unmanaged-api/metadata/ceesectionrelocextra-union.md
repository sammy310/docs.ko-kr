---
title: CeeSectionRelocExtra 공용 구조체
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: 7becace679b62a635d8231c3d42213f247f44190
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444172"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="d79ec-102">CeeSectionRelocExtra 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d79ec-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="d79ec-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span><span class="sxs-lookup"><span data-stu-id="d79ec-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="d79ec-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="d79ec-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d79ec-105">Members</span></span>  
  
|<span data-ttu-id="d79ec-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d79ec-106">Member</span></span>|<span data-ttu-id="d79ec-107">설명</span><span class="sxs-lookup"><span data-stu-id="d79ec-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="d79ec-108">The upper address adjustment for the section.</span><span class="sxs-lookup"><span data-stu-id="d79ec-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d79ec-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d79ec-109">Requirements</span></span>  
 <span data-ttu-id="d79ec-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d79ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79ec-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d79ec-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d79ec-112">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d79ec-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d79ec-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d79ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79ec-114">참조</span><span class="sxs-lookup"><span data-stu-id="d79ec-114">See also</span></span>

- [<span data-ttu-id="d79ec-115">메타데이터 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="d79ec-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
