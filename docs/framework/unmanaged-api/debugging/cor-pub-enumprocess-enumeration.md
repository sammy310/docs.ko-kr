---
title: COR_PUB_ENUMPROCESS 열거형
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ff60852a85d003deb68cae96a184ac8d61c65f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089414"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="d5d22-102">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="d5d22-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="d5d22-103">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d22-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d22-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5d22-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="d5d22-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d5d22-105">Members</span></span>  
  
|<span data-ttu-id="d5d22-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="d5d22-106">Member name</span></span>|<span data-ttu-id="d5d22-107">설명</span><span class="sxs-lookup"><span data-stu-id="d5d22-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="d5d22-108">관리 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d22-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5d22-109">설명</span><span class="sxs-lookup"><span data-stu-id="d5d22-109">Remarks</span></span>  
 <span data-ttu-id="d5d22-110">관리 되지 않는 디버깅 API의 현재 버전 관리 프로세스에만 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d22-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5d22-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5d22-111">Requirements</span></span>  
 <span data-ttu-id="d5d22-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5d22-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d22-113">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d5d22-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d5d22-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5d22-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d5d22-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d5d22-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5d22-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5d22-116">See also</span></span>

- [<span data-ttu-id="d5d22-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="d5d22-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
