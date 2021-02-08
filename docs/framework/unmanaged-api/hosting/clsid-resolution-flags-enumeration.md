---
description: '다음에 대 한 자세한 정보: 열거형 CLSID_RESOLUTION_FLAGS'
title: CLSID_RESOLUTION_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 54d334147e13217f8ce20dae1b139cdc6d11a3b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799878"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="9a74d-103">CLSID_RESOLUTION_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="9a74d-103">CLSID_RESOLUTION_FLAGS Enumeration</span></span>

<span data-ttu-id="9a74d-104">CLR (공용 언어 런타임)에서를 확인 하는 방법을 나타내는 값을 포함 합니다 `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="9a74d-104">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a74d-105">구문</span><span class="sxs-lookup"><span data-stu-id="9a74d-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9a74d-106">구성원</span><span class="sxs-lookup"><span data-stu-id="9a74d-106">Members</span></span>  
  
|<span data-ttu-id="9a74d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="9a74d-107">Member</span></span>|<span data-ttu-id="9a74d-108">설명</span><span class="sxs-lookup"><span data-stu-id="9a74d-108">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="9a74d-109">기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a74d-109">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="9a74d-110">런타임이 레지스트리를 검색 하 고 shim 정책을 적용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a74d-110">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a74d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a74d-111">Requirements</span></span>  

 <span data-ttu-id="9a74d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a74d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a74d-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9a74d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a74d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a74d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a74d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a74d-115">See also</span></span>

- [<span data-ttu-id="9a74d-116">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="9a74d-116">Hosting Enumerations</span></span>](hosting-enumerations.md)
