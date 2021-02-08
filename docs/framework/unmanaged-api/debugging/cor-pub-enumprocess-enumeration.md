---
description: '다음에 대 한 자세한 정보: 열거형 COR_PUB_ENUMPROCESS'
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
ms.openlocfilehash: 66bbd08aabb9d2c93e385ed098bae54754a85b85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801789"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="e5d50-103">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="e5d50-103">COR_PUB_ENUMPROCESS Enumeration</span></span>

<span data-ttu-id="e5d50-104">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d50-104">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d50-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5d50-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="e5d50-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e5d50-106">Members</span></span>  
  
|<span data-ttu-id="e5d50-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="e5d50-107">Member name</span></span>|<span data-ttu-id="e5d50-108">설명</span><span class="sxs-lookup"><span data-stu-id="e5d50-108">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="e5d50-109">관리 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e5d50-109">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5d50-110">설명</span><span class="sxs-lookup"><span data-stu-id="e5d50-110">Remarks</span></span>  

 <span data-ttu-id="e5d50-111">관리 되지 않는 디버깅 API의 현재 버전은 관리 되는 프로세스만 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d50-111">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d50-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5d50-112">Requirements</span></span>  

 <span data-ttu-id="e5d50-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5d50-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d50-114">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="e5d50-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e5d50-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5d50-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5d50-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d50-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d50-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5d50-117">See also</span></span>

- [<span data-ttu-id="e5d50-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="e5d50-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
