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
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007977"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="b6d09-102">COR_NATIVE_LINK 구조체</span><span class="sxs-lookup"><span data-stu-id="b6d09-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="b6d09-103">네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d09-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6d09-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="b6d09-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b6d09-105">Members</span></span>  
  
|<span data-ttu-id="b6d09-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b6d09-106">Member</span></span>|<span data-ttu-id="b6d09-107">설명</span><span class="sxs-lookup"><span data-stu-id="b6d09-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="b6d09-108">네이티브 코드에 연결 될 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-108">The type to be linked in native code.</span></span> <span data-ttu-id="b6d09-109">이 값은 [CorNativeLinkType](cornativelinktype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="b6d09-110">네이티브 코드를 연결할 때 링커에서 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="b6d09-111">이 값은 [CorNativeLinkFlags](cornativelinkflags-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="b6d09-112">진입점을 나타내는 MemberRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="b6d09-113">형식은 `lib:entrypoint`입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6d09-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6d09-114">Requirements</span></span>  
 <span data-ttu-id="b6d09-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6d09-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d09-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b6d09-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6d09-117">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6d09-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6d09-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d09-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d09-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6d09-119">See also</span></span>

- [<span data-ttu-id="b6d09-120">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="b6d09-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="b6d09-121">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="b6d09-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="b6d09-122">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="b6d09-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
