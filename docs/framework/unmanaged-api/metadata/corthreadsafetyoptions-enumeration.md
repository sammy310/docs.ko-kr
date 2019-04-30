---
title: CorThreadSafetyOptions 열거형
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d71d2a5b3007d4e877900443af426a9643b29125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045229"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="a6702-102">CorThreadSafetyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="a6702-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="a6702-103">스레드 안정성 옵션을 선택하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6702-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="a6702-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6702-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="a6702-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a6702-105">Members</span></span>

|<span data-ttu-id="a6702-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a6702-106">Member</span></span>|<span data-ttu-id="a6702-107">설명</span><span class="sxs-lookup"><span data-stu-id="a6702-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="a6702-108">기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a6702-108">Default value.</span></span> <span data-ttu-id="a6702-109">`MDThreadSafetyOff`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a6702-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="a6702-110">판독기/기록기 잠금을 설정할 수 없습니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6702-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="a6702-111">판독기/기록기 잠금을 설정할 수 있도록 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6702-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="a6702-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6702-112">Requirements</span></span>

<span data-ttu-id="a6702-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6702-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a6702-114">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a6702-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="a6702-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6702-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a6702-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a6702-116">See also</span></span>

- [<span data-ttu-id="a6702-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="a6702-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
