---
title: DacpGetModuleAddress 구조체
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e460264e2393858c028ba51aec4a4f2c01649994
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860830"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="ef121-102">DacpGetModuleAddress 구조체</span><span class="sxs-lookup"><span data-stu-id="ef121-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="ef121-103">모듈 주소 요청에 대 한 컨테이너를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef121-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ef121-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef121-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="ef121-105">구성원</span><span class="sxs-lookup"><span data-stu-id="ef121-105">Members</span></span>

| <span data-ttu-id="ef121-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ef121-106">Member</span></span>      | <span data-ttu-id="ef121-107">Description</span><span class="sxs-lookup"><span data-stu-id="ef121-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="ef121-108">모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef121-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="ef121-109">메서드</span><span class="sxs-lookup"><span data-stu-id="ef121-109">Methods</span></span>

| <span data-ttu-id="ef121-110">메서드</span><span class="sxs-lookup"><span data-stu-id="ef121-110">Method</span></span>                                                                                               | <span data-ttu-id="ef121-111">Description</span><span class="sxs-lookup"><span data-stu-id="ef121-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="ef121-112">요청</span><span class="sxs-lookup"><span data-stu-id="ef121-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="ef121-113">지정 된 런타임 구조체에서 구조체를 채우도록 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef121-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ef121-114">설명</span><span class="sxs-lookup"><span data-stu-id="ef121-114">Remarks</span></span>

<span data-ttu-id="ef121-115">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef121-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ef121-116">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다 `CLRDATA_ADDRESS` . 여기서은 64 비트의 부호 없는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef121-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="ef121-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef121-117">Requirements</span></span>
<span data-ttu-id="ef121-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef121-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ef121-119">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="ef121-119">**Header:** None</span></span>  
<span data-ttu-id="ef121-120">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="ef121-120">**Library:** None</span></span>  
<span data-ttu-id="ef121-121">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ef121-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ef121-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef121-122">See also</span></span>

- [<span data-ttu-id="ef121-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="ef121-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="ef121-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="ef121-124">Debugging Structures</span></span>](debugging-structures.md)
