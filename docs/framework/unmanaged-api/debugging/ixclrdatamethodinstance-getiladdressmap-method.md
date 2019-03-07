---
title: IXCLRDataMethodInstance::GetILAddressMap 메서드
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e88897342bf18111ebd4914948ab45085c35ea08
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484123"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="18148-102">IXCLRDataMethodInstance::GetILAddressMap 메서드</span><span class="sxs-lookup"><span data-stu-id="18148-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="18148-103">IL을 주소 매핑 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18148-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="18148-104">구문</span><span class="sxs-lookup"><span data-stu-id="18148-104">Syntax</span></span>

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="18148-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18148-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="18148-106">[in] 제공 된 맵 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="18148-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="18148-107">[out] 메서드는 맵 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="18148-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="18148-108">[out, size_is(mapLen)] 맵 항목을 저장 하기 위한 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="18148-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="18148-109">설명</span><span class="sxs-lookup"><span data-stu-id="18148-109">Remarks</span></span>

<span data-ttu-id="18148-110">제공 된 메서드는의 일부는 `IXCLRDataMethodInstance` 인터페이스 및 가상 메서드 테이블의 14 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="18148-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="18148-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18148-111">Requirements</span></span>

<span data-ttu-id="18148-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18148-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="18148-113">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="18148-113">**Header:** None</span></span>  
<span data-ttu-id="18148-114">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="18148-114">**Library:** None</span></span>  
<span data-ttu-id="18148-115">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18148-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="18148-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="18148-116">See also</span></span>

- [<span data-ttu-id="18148-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="18148-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="18148-118">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18148-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
