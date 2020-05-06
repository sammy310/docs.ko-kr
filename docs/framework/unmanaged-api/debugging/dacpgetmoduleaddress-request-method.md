---
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
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860845"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="02adb-102">DacpGetModuleAddress::Request 메서드</span><span class="sxs-lookup"><span data-stu-id="02adb-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="02adb-103">지정 된 런타임 구조체에서 구조체를 채우도록 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="02adb-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="02adb-104">구문</span><span class="sxs-lookup"><span data-stu-id="02adb-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="02adb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02adb-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="02adb-106">진행 초기값 데이터 모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02adb-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="02adb-107">설명</span><span class="sxs-lookup"><span data-stu-id="02adb-107">Remarks</span></span>

<span data-ttu-id="02adb-108">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02adb-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="02adb-109">이를 사용 하는 가장 쉬운 방법은 구현을 모방 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02adb-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="02adb-110">다음 매개 변수를 사용 하 여 `Request` `IXCLRDataModule*` 매개 변수에 대해 메서드를 호출 하 여 가져온 값을 반환 합니다.`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="02adb-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="02adb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02adb-111">Requirements</span></span>

<span data-ttu-id="02adb-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02adb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="02adb-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="02adb-113">**Header:** None\</span></span>
<span data-ttu-id="02adb-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="02adb-114">**Library:** None\</span></span>
<span data-ttu-id="02adb-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="02adb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="02adb-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02adb-116">See also</span></span>

- [<span data-ttu-id="02adb-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="02adb-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="02adb-118">DacpGetModuleAddress 구조체</span><span class="sxs-lookup"><span data-stu-id="02adb-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
