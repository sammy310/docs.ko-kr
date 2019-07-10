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
ms.openlocfilehash: 07ad83da2bc608e3c5925664a68eec4a548860e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739222"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="107f2-102">DacpGetModuleAddress::Request 메서드</span><span class="sxs-lookup"><span data-stu-id="107f2-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="107f2-103">지정 된 런타임 구조에서 구조를 채우는 데 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="107f2-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="107f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="107f2-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="107f2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="107f2-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="107f2-106">[in] 초기값 데이터 모듈에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="107f2-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="107f2-107">설명</span><span class="sxs-lookup"><span data-stu-id="107f2-107">Remarks</span></span>

<span data-ttu-id="107f2-108">이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="107f2-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="107f2-109">를 사용 하려면 구현을 모방 하는 가장 쉬운 방법은:</span><span class="sxs-lookup"><span data-stu-id="107f2-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="107f2-110">호출에서 얻은 값을 반환 합니다 `Request` 메서드는 `IXCLRDataModule*` 다음 매개 변수를 사용 하 여 매개 변수: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="107f2-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="107f2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="107f2-111">Requirements</span></span>

<span data-ttu-id="107f2-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="107f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="107f2-113">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="107f2-113">**Header:** None</span></span>     
<span data-ttu-id="107f2-114">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="107f2-114">**Library:** None</span></span>  
<span data-ttu-id="107f2-115">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="107f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="107f2-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="107f2-116">See also</span></span>

- [<span data-ttu-id="107f2-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="107f2-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="107f2-118">DacpGetModuleAddress 인터페이스</span><span class="sxs-lookup"><span data-stu-id="107f2-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
