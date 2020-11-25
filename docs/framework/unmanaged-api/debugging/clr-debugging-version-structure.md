---
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
ms.openlocfilehash: 8a2abe847728a2bb1f1345ef73e55b58e4704001
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729813"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="df943-102">CLR_DEBUGGING_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="df943-102">CLR_DEBUGGING_VERSION Structure</span></span>

<span data-ttu-id="df943-103">디버깅용 CLR(공용 언어 런타임)의 제품 버전을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="df943-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df943-104">구문</span><span class="sxs-lookup"><span data-stu-id="df943-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="df943-105">멤버</span><span class="sxs-lookup"><span data-stu-id="df943-105">Members</span></span>  
  
|<span data-ttu-id="df943-106">멤버</span><span class="sxs-lookup"><span data-stu-id="df943-106">Member</span></span>|<span data-ttu-id="df943-107">설명</span><span class="sxs-lookup"><span data-stu-id="df943-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="df943-108">구조 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="df943-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="df943-109">주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="df943-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="df943-110">부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="df943-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="df943-111">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="df943-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="df943-112">수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="df943-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df943-113">설명</span><span class="sxs-lookup"><span data-stu-id="df943-113">Remarks</span></span>  

 <span data-ttu-id="df943-114">`CLR_DEBUGGING_VERSION`구조는 COR_VERSION 구조와 동일 하지만 구조는 `CLR_DEBUGGING_VERSION` 추가 구조 버전 필드 ()를 제공 합니다 `wStructVersion` .</span><span class="sxs-lookup"><span data-stu-id="df943-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="df943-115">현재이 필드는 0으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df943-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df943-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df943-116">Requirements</span></span>  

 <span data-ttu-id="df943-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df943-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df943-118">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="df943-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="df943-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df943-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df943-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df943-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df943-121">참조</span><span class="sxs-lookup"><span data-stu-id="df943-121">See also</span></span>

- [<span data-ttu-id="df943-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="df943-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="df943-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="df943-123">Debugging</span></span>](index.md)
