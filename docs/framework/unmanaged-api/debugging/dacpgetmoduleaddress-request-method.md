---
description: '자세히 알아보기: DacpGetModuleAddress:: Request 메서드'
title: DacpGetModuleAddress::Request 메서드
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4cdec9cf6b9bd818ce1137fb5b2c691532fab94e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801503"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="7ad3e-103">DacpGetModuleAddress::Request 메서드</span><span class="sxs-lookup"><span data-stu-id="7ad3e-103">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="7ad3e-104">지정 된 런타임 구조체에서 구조체를 채우도록 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3e-104">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7ad3e-105">구문</span><span class="sxs-lookup"><span data-stu-id="7ad3e-105">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="7ad3e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ad3e-106">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="7ad3e-107">진행 초기값 데이터 모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3e-107">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ad3e-108">설명</span><span class="sxs-lookup"><span data-stu-id="7ad3e-108">Remarks</span></span>

<span data-ttu-id="7ad3e-109">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3e-109">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7ad3e-110">이를 사용 하는 가장 쉬운 방법은 구현을 모방 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3e-110">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="7ad3e-111">`Request` `IXCLRDataModule*` 다음 매개 변수를 사용 하 여 매개 변수에 대해 메서드를 호출 하 여 가져온 값을 반환 합니다.`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="7ad3e-111">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="7ad3e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ad3e-112">Requirements</span></span>

<span data-ttu-id="7ad3e-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ad3e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="7ad3e-114">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="7ad3e-114">**Header:** None\</span></span>
<span data-ttu-id="7ad3e-115">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="7ad3e-115">**Library:** None\</span></span>
<span data-ttu-id="7ad3e-116">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7ad3e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7ad3e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ad3e-117">See also</span></span>

- [<span data-ttu-id="7ad3e-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="7ad3e-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="7ad3e-119">DacpGetModuleAddress 구조체</span><span class="sxs-lookup"><span data-stu-id="7ad3e-119">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
