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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7024140ed9b870b5db38dba7e9b13321dd37386a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157588"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="e145c-102">COR_NATIVE_LINK 구조체</span><span class="sxs-lookup"><span data-stu-id="e145c-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="e145c-103">네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e145c-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e145c-104">구문</span><span class="sxs-lookup"><span data-stu-id="e145c-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="e145c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e145c-105">Members</span></span>  
  
|<span data-ttu-id="e145c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e145c-106">Member</span></span>|<span data-ttu-id="e145c-107">설명</span><span class="sxs-lookup"><span data-stu-id="e145c-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="e145c-108">네이티브 코드에 연결 될 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e145c-108">The type to be linked in native code.</span></span> <span data-ttu-id="e145c-109">이 값은 중 하나는 [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e145c-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="e145c-110">네이티브 코드를 연결할 때 링커에서 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e145c-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="e145c-111">이 값은 중 하나는 [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e145c-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="e145c-112">진입점을 나타내는 MemberRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e145c-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="e145c-113">형식은 `lib:entrypoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="e145c-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e145c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e145c-114">Requirements</span></span>  
 <span data-ttu-id="e145c-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e145c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e145c-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e145c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e145c-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e145c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e145c-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e145c-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e145c-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="e145c-119">See also</span></span>

- [<span data-ttu-id="e145c-120">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="e145c-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="e145c-121">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="e145c-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="e145c-122">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="e145c-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
