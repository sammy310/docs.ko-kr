---
description: '다음에 대 한 자세한 정보: CLR_DEBUGGING_VERSION 구조체'
title: CLR_DEBUGGING_VERSION 구조체
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 2d274a91948b98dc309cd5670c3dd3bf6cd01e2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772785"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="89252-103">CLR_DEBUGGING_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="89252-103">CLR_DEBUGGING_VERSION Structure</span></span>

<span data-ttu-id="89252-104">디버깅용 CLR(공용 언어 런타임)의 제품 버전을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="89252-104">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89252-105">구문</span><span class="sxs-lookup"><span data-stu-id="89252-105">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="89252-106">구성원</span><span class="sxs-lookup"><span data-stu-id="89252-106">Members</span></span>  
  
|<span data-ttu-id="89252-107">멤버</span><span class="sxs-lookup"><span data-stu-id="89252-107">Member</span></span>|<span data-ttu-id="89252-108">설명</span><span class="sxs-lookup"><span data-stu-id="89252-108">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="89252-109">구조 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="89252-109">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="89252-110">주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="89252-110">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="89252-111">부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="89252-111">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="89252-112">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="89252-112">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="89252-113">수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="89252-113">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89252-114">설명</span><span class="sxs-lookup"><span data-stu-id="89252-114">Remarks</span></span>  

 <span data-ttu-id="89252-115">`CLR_DEBUGGING_VERSION`구조는 COR_VERSION 구조와 동일 하지만 구조는 `CLR_DEBUGGING_VERSION` 추가 구조 버전 필드 ()를 제공 합니다 `wStructVersion` .</span><span class="sxs-lookup"><span data-stu-id="89252-115">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="89252-116">현재이 필드는 0으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89252-116">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89252-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89252-117">Requirements</span></span>  

 <span data-ttu-id="89252-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89252-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89252-119">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="89252-119">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="89252-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89252-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89252-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89252-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89252-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89252-122">See also</span></span>

- [<span data-ttu-id="89252-123">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="89252-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="89252-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="89252-124">Debugging</span></span>](index.md)
