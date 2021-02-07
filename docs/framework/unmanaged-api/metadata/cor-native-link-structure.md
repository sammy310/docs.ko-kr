---
description: '다음에 대 한 자세한 정보: COR_NATIVE_LINK 구조체'
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
ms.openlocfilehash: 09c715af698a0614fd4a9a17679df6908a1497a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678577"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="e9b4f-103">COR_NATIVE_LINK 구조체</span><span class="sxs-lookup"><span data-stu-id="e9b4f-103">COR_NATIVE_LINK Structure</span></span>

<span data-ttu-id="e9b4f-104">네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-104">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b4f-105">구문</span><span class="sxs-lookup"><span data-stu-id="e9b4f-105">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="e9b4f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e9b4f-106">Members</span></span>  
  
|<span data-ttu-id="e9b4f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e9b4f-107">Member</span></span>|<span data-ttu-id="e9b4f-108">설명</span><span class="sxs-lookup"><span data-stu-id="e9b4f-108">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="e9b4f-109">네이티브 코드에 연결 될 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-109">The type to be linked in native code.</span></span> <span data-ttu-id="e9b4f-110">이 값은 [CorNativeLinkType](cornativelinktype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-110">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="e9b4f-111">네이티브 코드를 연결할 때 링커에서 사용 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-111">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="e9b4f-112">이 값은 [CorNativeLinkFlags](cornativelinkflags-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-112">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="e9b4f-113">진입점을 나타내는 MemberRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-113">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="e9b4f-114">형식은 `lib:entrypoint`입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-114">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9b4f-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9b4f-115">Requirements</span></span>  

 <span data-ttu-id="e9b4f-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b4f-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e9b4f-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9b4f-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9b4f-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9b4f-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b4f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b4f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9b4f-120">See also</span></span>

- [<span data-ttu-id="e9b4f-121">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="e9b4f-121">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="e9b4f-122">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="e9b4f-122">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="e9b4f-123">CorNativeLinkFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="e9b4f-123">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
