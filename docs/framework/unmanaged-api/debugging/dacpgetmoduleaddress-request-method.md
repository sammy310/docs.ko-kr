---
title: DacpGetModuleAddress::요청 방법
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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179209"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="94583-102">DacpGetModuleAddress::요청 방법</span><span class="sxs-lookup"><span data-stu-id="94583-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="94583-103">지정된 런타임 구조에서 구조를 채우는 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="94583-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="94583-104">구문</span><span class="sxs-lookup"><span data-stu-id="94583-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="94583-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94583-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="94583-106">【인】 시드 데이터 모듈에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94583-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="94583-107">설명</span><span class="sxs-lookup"><span data-stu-id="94583-107">Remarks</span></span>

<span data-ttu-id="94583-108">이 구조는 런타임 내에 있으며 헤더 나 라이브러리 파일을 통해 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94583-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="94583-109">이를 사용하는 가장 쉬운 방법은 구현을 모방하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94583-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="94583-110">다음 매개 변수를 사용하여 `Request` 매개 `IXCLRDataModule*` 변수에서 메서드를 호출하여 얻은 값을 반환합니다.`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="94583-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="94583-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94583-111">Requirements</span></span>

<span data-ttu-id="94583-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94583-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="94583-113">**헤더:** 라이브러리 **없음:** 없음</span><span class="sxs-lookup"><span data-stu-id="94583-113">**Header:** None **Library:** None</span></span>  
<span data-ttu-id="94583-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="94583-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="94583-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94583-115">See also</span></span>

- [<span data-ttu-id="94583-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="94583-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="94583-117">DacpGet모듈주소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94583-117">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
