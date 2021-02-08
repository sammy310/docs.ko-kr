---
description: '자세히 알아보기: CorManifestResourceFlags 열거형'
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
ms.openlocfilehash: a863e1248bf5274e12fc16d2edea6b28dd493963
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784407"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="f4aee-103">CorManifestResourceFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="f4aee-103">CorManifestResourceFlags Enumeration</span></span>

<span data-ttu-id="f4aee-104">어셈블리 매니페스트에 인코딩된 리소스의 표시 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4aee-104">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4aee-105">구문</span><span class="sxs-lookup"><span data-stu-id="f4aee-105">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f4aee-106">구성원</span><span class="sxs-lookup"><span data-stu-id="f4aee-106">Members</span></span>  
  
|<span data-ttu-id="f4aee-107">멤버</span><span class="sxs-lookup"><span data-stu-id="f4aee-107">Member</span></span>|<span data-ttu-id="f4aee-108">설명</span><span class="sxs-lookup"><span data-stu-id="f4aee-108">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="f4aee-109">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4aee-109">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="f4aee-110">리소스는 공용입니다.</span><span class="sxs-lookup"><span data-stu-id="f4aee-110">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="f4aee-111">전용 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="f4aee-111">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4aee-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4aee-112">Requirements</span></span>  

 <span data-ttu-id="f4aee-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4aee-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4aee-114">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="f4aee-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f4aee-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4aee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4aee-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4aee-116">See also</span></span>

- [<span data-ttu-id="f4aee-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f4aee-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
