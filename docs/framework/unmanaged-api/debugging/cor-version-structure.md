---
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
ms.openlocfilehash: cc9a67e16635209c3bf303e97dc3e5938943a653
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099087"
---
# <a name="cor_version-structure"></a><span data-ttu-id="53456-102">COR_VERSION 구조체</span><span class="sxs-lookup"><span data-stu-id="53456-102">COR_VERSION Structure</span></span>
<span data-ttu-id="53456-103">공용 언어 런타임의 4부분으로 구성된 표준 버전 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="53456-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53456-104">구문</span><span class="sxs-lookup"><span data-stu-id="53456-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="53456-105">멤버</span><span class="sxs-lookup"><span data-stu-id="53456-105">Members</span></span>  
  
|<span data-ttu-id="53456-106">멤버</span><span class="sxs-lookup"><span data-stu-id="53456-106">Member</span></span>|<span data-ttu-id="53456-107">설명</span><span class="sxs-lookup"><span data-stu-id="53456-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="53456-108">주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="53456-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="53456-109">부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="53456-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="53456-110">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="53456-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="53456-111">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="53456-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53456-112">주의</span><span class="sxs-lookup"><span data-stu-id="53456-112">Remarks</span></span>  
 <span data-ttu-id="53456-113">버전 번호가 1.0.3705.288 인 경우 1은 주 버전 번호이 고, 0은 부 버전 번호이 고, 3705는 빌드 번호 이며, 288은 하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="53456-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53456-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53456-114">Requirements</span></span>  
 <span data-ttu-id="53456-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53456-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53456-116">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="53456-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="53456-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53456-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53456-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53456-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53456-119">참조</span><span class="sxs-lookup"><span data-stu-id="53456-119">See also</span></span>

- [<span data-ttu-id="53456-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="53456-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="53456-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="53456-121">Debugging</span></span>](index.md)
