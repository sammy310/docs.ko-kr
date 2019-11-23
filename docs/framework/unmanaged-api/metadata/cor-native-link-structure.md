---
title: COR_NATIVE_LINK 구조체
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: d03c22c455f0e44ce32d4593d9eee50ceef94a22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443951"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="69625-102">COR_NATIVE_LINK 구조체</span><span class="sxs-lookup"><span data-stu-id="69625-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="69625-103">네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="69625-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69625-104">구문</span><span class="sxs-lookup"><span data-stu-id="69625-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="69625-105">멤버</span><span class="sxs-lookup"><span data-stu-id="69625-105">Members</span></span>  
  
|<span data-ttu-id="69625-106">멤버</span><span class="sxs-lookup"><span data-stu-id="69625-106">Member</span></span>|<span data-ttu-id="69625-107">설명</span><span class="sxs-lookup"><span data-stu-id="69625-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="69625-108">The type to be linked in native code.</span><span class="sxs-lookup"><span data-stu-id="69625-108">The type to be linked in native code.</span></span> <span data-ttu-id="69625-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="69625-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="69625-110">Flags used by the linker when linking native code.</span><span class="sxs-lookup"><span data-stu-id="69625-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="69625-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="69625-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="69625-112">The MemberRef metadata token that represents the entry point.</span><span class="sxs-lookup"><span data-stu-id="69625-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="69625-113">형식은 `lib:entrypoint`입니다.</span><span class="sxs-lookup"><span data-stu-id="69625-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69625-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69625-114">Requirements</span></span>  
 <span data-ttu-id="69625-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69625-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69625-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69625-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69625-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69625-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69625-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69625-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69625-119">참조</span><span class="sxs-lookup"><span data-stu-id="69625-119">See also</span></span>

- [<span data-ttu-id="69625-120">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="69625-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="69625-121">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="69625-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="69625-122">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="69625-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
