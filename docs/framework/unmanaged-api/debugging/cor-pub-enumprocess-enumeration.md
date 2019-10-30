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
ms.openlocfilehash: f789105751ae2d498740ab60f326f9c0597483b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099206"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="82d3a-102">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="82d3a-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="82d3a-103">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="82d3a-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82d3a-104">구문</span><span class="sxs-lookup"><span data-stu-id="82d3a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="82d3a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="82d3a-105">Members</span></span>  
  
|<span data-ttu-id="82d3a-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="82d3a-106">Member name</span></span>|<span data-ttu-id="82d3a-107">설명</span><span class="sxs-lookup"><span data-stu-id="82d3a-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="82d3a-108">관리 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="82d3a-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82d3a-109">주의</span><span class="sxs-lookup"><span data-stu-id="82d3a-109">Remarks</span></span>  
 <span data-ttu-id="82d3a-110">관리 되지 않는 디버깅 API의 현재 버전은 관리 되는 프로세스만 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d3a-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82d3a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82d3a-111">Requirements</span></span>  
 <span data-ttu-id="82d3a-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82d3a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82d3a-113">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="82d3a-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="82d3a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82d3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82d3a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82d3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d3a-116">참조</span><span class="sxs-lookup"><span data-stu-id="82d3a-116">See also</span></span>

- [<span data-ttu-id="82d3a-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="82d3a-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
