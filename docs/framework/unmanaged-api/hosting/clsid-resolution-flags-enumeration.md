---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5274e70c5bead201beb158ee2895415d7ec9e53c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779135"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="2d24a-102">CLSID_RESOLUTION_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="2d24a-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="2d24a-103">CLR (공용 언어 런타임) 확인 하는 방법을 나타내는 값을 포함 한 `CLSID`합니다.</span><span class="sxs-lookup"><span data-stu-id="2d24a-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d24a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2d24a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="2d24a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2d24a-105">Members</span></span>  
  
|<span data-ttu-id="2d24a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2d24a-106">Member</span></span>|<span data-ttu-id="2d24a-107">설명</span><span class="sxs-lookup"><span data-stu-id="2d24a-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="2d24a-108">기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d24a-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="2d24a-109">런타임 레지스트리를 검색 하 고 shim 정책 적용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d24a-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d24a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d24a-110">Requirements</span></span>  
 <span data-ttu-id="2d24a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d24a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d24a-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d24a-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d24a-113">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d24a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d24a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d24a-114">See also</span></span>

- [<span data-ttu-id="2d24a-115">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="2d24a-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
