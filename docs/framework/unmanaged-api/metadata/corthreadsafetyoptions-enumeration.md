---
description: '자세한 정보: CorThreadSafetyOptions 열거형'
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
ms.openlocfilehash: 7915bcf5e7b71fa84ea83642467c1600cd38712d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707321"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="5770e-103">CorThreadSafetyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="5770e-103">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="5770e-104">스레드 안정성 옵션을 선택하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5770e-104">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="5770e-105">구문</span><span class="sxs-lookup"><span data-stu-id="5770e-105">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="5770e-106">구성원</span><span class="sxs-lookup"><span data-stu-id="5770e-106">Members</span></span>

|<span data-ttu-id="5770e-107">멤버</span><span class="sxs-lookup"><span data-stu-id="5770e-107">Member</span></span>|<span data-ttu-id="5770e-108">설명</span><span class="sxs-lookup"><span data-stu-id="5770e-108">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="5770e-109">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="5770e-109">Default value.</span></span> <span data-ttu-id="5770e-110">`MDThreadSafetyOff`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5770e-110">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="5770e-111">판독기/작성기 잠금을 설정할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5770e-111">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="5770e-112">판독기/작성기 잠금을 설정할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5770e-112">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="5770e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5770e-113">Requirements</span></span>

<span data-ttu-id="5770e-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5770e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5770e-115">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="5770e-115">**Header:** CorHdr.h</span></span>

<span data-ttu-id="5770e-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5770e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5770e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5770e-117">See also</span></span>

- [<span data-ttu-id="5770e-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="5770e-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
