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
ms.openlocfilehash: ebdff88e9fdf499b809d56c4c29a906dbef9ec40
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008978"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="4bbbc-102">CorManifestResourceFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="4bbbc-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="4bbbc-103">어셈블리 매니페스트에 인코딩된 리소스의 표시 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4bbbc-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bbbc-104">구문</span><span class="sxs-lookup"><span data-stu-id="4bbbc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="4bbbc-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4bbbc-105">Members</span></span>  
  
|<span data-ttu-id="4bbbc-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4bbbc-106">Member</span></span>|<span data-ttu-id="4bbbc-107">설명</span><span class="sxs-lookup"><span data-stu-id="4bbbc-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="4bbbc-108">예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbbc-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="4bbbc-109">리소스는 공용입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbbc-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="4bbbc-110">전용 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbbc-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4bbbc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4bbbc-111">Requirements</span></span>  
 <span data-ttu-id="4bbbc-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbbc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bbbc-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="4bbbc-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4bbbc-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bbbc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bbbc-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4bbbc-115">See also</span></span>

- [<span data-ttu-id="4bbbc-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="4bbbc-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
