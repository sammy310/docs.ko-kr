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
ms.openlocfilehash: 5d27ba2de9ff6ed184b6ddf50a517d0dae7715f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723053"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="88ff1-102">DacpModuleData 구조체</span><span class="sxs-lookup"><span data-stu-id="88ff1-102">DacpModuleData Structure</span></span>

<span data-ttu-id="88ff1-103">모듈의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ff1-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="88ff1-104">구문</span><span class="sxs-lookup"><span data-stu-id="88ff1-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="88ff1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="88ff1-105">Members</span></span>

| <span data-ttu-id="88ff1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="88ff1-106">Member</span></span>    | <span data-ttu-id="88ff1-107">설명</span><span class="sxs-lookup"><span data-stu-id="88ff1-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="88ff1-108">모듈 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="88ff1-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="88ff1-109">PE (이식 가능한 실행) 파일에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="88ff1-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="88ff1-110">로드 된 이미지의 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="88ff1-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="88ff1-111">런타임에서 사용 하는 추가 모듈 정보에 대 한 페이로드 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="88ff1-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="88ff1-112">설명</span><span class="sxs-lookup"><span data-stu-id="88ff1-112">Remarks</span></span>

<span data-ttu-id="88ff1-113">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88ff1-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="88ff1-114">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ff1-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="88ff1-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88ff1-115">Requirements</span></span>

<span data-ttu-id="88ff1-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88ff1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="88ff1-117">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="88ff1-117">**Header:** None</span></span>  
<span data-ttu-id="88ff1-118">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="88ff1-118">**Library:** None</span></span>  
<span data-ttu-id="88ff1-119">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="88ff1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="88ff1-120">참조</span><span class="sxs-lookup"><span data-stu-id="88ff1-120">See also</span></span>

- [<span data-ttu-id="88ff1-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="88ff1-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="88ff1-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="88ff1-122">Debugging Structures</span></span>](debugging-structures.md)
