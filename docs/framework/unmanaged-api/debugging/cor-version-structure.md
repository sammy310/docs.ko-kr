---
description: '다음에 대 한 자세한 정보: COR_VERSION 구조체'
title: COR_VERSION 구조체
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
ms.openlocfilehash: abdbe2a62d89db9dd673a429d81209fc42c34b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801776"
---
# <a name="cor_version-structure"></a><span data-ttu-id="5a628-103">COR_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="5a628-103">COR_VERSION Structure</span></span>

<span data-ttu-id="5a628-104">공용 언어 런타임의 4부분으로 구성된 표준 버전 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5a628-104">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a628-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a628-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="5a628-106">구성원</span><span class="sxs-lookup"><span data-stu-id="5a628-106">Members</span></span>  
  
|<span data-ttu-id="5a628-107">멤버</span><span class="sxs-lookup"><span data-stu-id="5a628-107">Member</span></span>|<span data-ttu-id="5a628-108">설명</span><span class="sxs-lookup"><span data-stu-id="5a628-108">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="5a628-109">주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5a628-109">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="5a628-110">부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5a628-110">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="5a628-111">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5a628-111">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="5a628-112">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5a628-112">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a628-113">설명</span><span class="sxs-lookup"><span data-stu-id="5a628-113">Remarks</span></span>  

 <span data-ttu-id="5a628-114">버전 번호가 1.0.3705.288 인 경우 1은 주 버전 번호이 고, 0은 부 버전 번호이 고, 3705는 빌드 번호 이며, 288은 하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5a628-114">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a628-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a628-115">Requirements</span></span>  

 <span data-ttu-id="5a628-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a628-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a628-117">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="5a628-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="5a628-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a628-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a628-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a628-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a628-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a628-120">See also</span></span>

- [<span data-ttu-id="5a628-121">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="5a628-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="5a628-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="5a628-122">Debugging</span></span>](index.md)
