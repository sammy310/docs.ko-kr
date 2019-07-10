---
title: DacpModuleData 구조체
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 2e27082ba4c35bc10eb65139b2af6c81c10d79a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739127"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="7fd31-102">DacpModuleData 구조체</span><span class="sxs-lookup"><span data-stu-id="7fd31-102">DacpModuleData Structure</span></span>

<span data-ttu-id="7fd31-103">모듈의 런타임 정보에 대 한 전송 버퍼를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd31-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7fd31-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fd31-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="7fd31-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7fd31-105">Members</span></span>

| <span data-ttu-id="7fd31-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7fd31-106">Member</span></span>    | <span data-ttu-id="7fd31-107">설명</span><span class="sxs-lookup"><span data-stu-id="7fd31-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="7fd31-108">모듈 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd31-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="7fd31-109">Pe (이식 가능) 파일에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd31-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="7fd31-110">로드 된 이미지의 주소의 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd31-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="7fd31-111">런타임에서 사용 되는 추가 모듈 정보에 대 한 페이로드 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd31-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7fd31-112">설명</span><span class="sxs-lookup"><span data-stu-id="7fd31-112">Remarks</span></span>

<span data-ttu-id="7fd31-113">이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd31-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7fd31-114">를 사용 하려면 위에서 지정한 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd31-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="7fd31-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fd31-115">Requirements</span></span>
<span data-ttu-id="7fd31-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fd31-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7fd31-117">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="7fd31-117">**Header:** None</span></span>  
<span data-ttu-id="7fd31-118">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="7fd31-118">**Library:** None</span></span>  
<span data-ttu-id="7fd31-119">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7fd31-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7fd31-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="7fd31-120">See also</span></span>

- [<span data-ttu-id="7fd31-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="7fd31-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="7fd31-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="7fd31-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
