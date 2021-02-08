---
description: '자세히 알아보기: IXCLRDataMethodInstance:: GetILAddressMap 메서드'
title: 'IXCLRDataMethodInstance:: GetILAddressMap 메서드'
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
ms.openlocfilehash: ddddf593c3c18f2b4cd1682b5d6f7c8ff1985ac6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800814"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="36828-103">IXCLRDataMethodInstance:: GetILAddressMap 메서드</span><span class="sxs-lookup"><span data-stu-id="36828-103">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="36828-104">매핑 정보를 처리 하는 IL을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="36828-104">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="36828-105">구문</span><span class="sxs-lookup"><span data-stu-id="36828-105">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="36828-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36828-106">Parameters</span></span>

`mapLen`\
<span data-ttu-id="36828-107">진행 제공 된 맵 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="36828-107">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="36828-108">제한이 메서드에 필요한 맵 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="36828-108">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="36828-109">[out, size_is (mapLen)] 맵 항목을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="36828-109">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="36828-110">설명</span><span class="sxs-lookup"><span data-stu-id="36828-110">Remarks</span></span>

<span data-ttu-id="36828-111">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataMethodInstance` 가상 메서드 테이블의 15 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="36828-111">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="36828-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36828-112">Requirements</span></span>

<span data-ttu-id="36828-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36828-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="36828-114">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="36828-114">**Header:** None</span></span>  
<span data-ttu-id="36828-115">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="36828-115">**Library:** None</span></span>  
<span data-ttu-id="36828-116">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36828-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="36828-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36828-117">See also</span></span>

- [<span data-ttu-id="36828-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="36828-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="36828-119">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36828-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
