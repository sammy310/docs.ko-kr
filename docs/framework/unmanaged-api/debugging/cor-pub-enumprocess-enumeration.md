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
ms.openlocfilehash: eab5fc13b74d8af4f0baaa3953c5c73ea255bfe6
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274017"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="a55f2-102">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="a55f2-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="a55f2-103">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a55f2-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a55f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="a55f2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="a55f2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a55f2-105">Members</span></span>  
  
|<span data-ttu-id="a55f2-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="a55f2-106">Member name</span></span>|<span data-ttu-id="a55f2-107">설명</span><span class="sxs-lookup"><span data-stu-id="a55f2-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="a55f2-108">관리 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="a55f2-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a55f2-109">설명</span><span class="sxs-lookup"><span data-stu-id="a55f2-109">Remarks</span></span>  
 <span data-ttu-id="a55f2-110">관리 되지 않는 디버깅 API의 현재 버전은 관리 되는 프로세스만 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a55f2-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a55f2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a55f2-111">Requirements</span></span>  
 <span data-ttu-id="a55f2-112">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a55f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a55f2-113">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="a55f2-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a55f2-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a55f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a55f2-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a55f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55f2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a55f2-116">See also</span></span>

- [<span data-ttu-id="a55f2-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="a55f2-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
