---
description: '자세히 알아보기: ISOSDacInterface:: GetMethodDescData 메서드'
title: 'ISOSDacInterface:: GetMethodDescData 메서드'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a1284aa4d810ed9d6db7ad3c1b471702b1dad54d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790427"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="eac79-103">ISOSDacInterface:: GetMethodDescData 메서드</span><span class="sxs-lookup"><span data-stu-id="eac79-103">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="eac79-104">지정 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-104">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="eac79-105">구문</span><span class="sxs-lookup"><span data-stu-id="eac79-105">Syntax</span></span>

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="eac79-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eac79-106">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="eac79-107">진행 MethodDesc의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-107">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="eac79-108">진행 메서드의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-108">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="eac79-109">제한이 내부 Api에서 반환 되는 MethodDesc와 연결 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-109">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="eac79-110">제한이 되돌린 rejit 버전의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-110">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="eac79-111">제한이 내부 Api에서 반환 된 대로 되돌린 rejit 버전과 연결 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-111">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="eac79-112">제한이 되돌린 ReJit 버전과 연결 된 데이터를 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-112">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="eac79-113">설명</span><span class="sxs-lookup"><span data-stu-id="eac79-113">Remarks</span></span>

<span data-ttu-id="eac79-114">제공 된 메서드는 인터페이스의 일부 `ISOSDacInterface` 이며 가상 메서드 테이블의 21 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-114">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="eac79-115">이를 사용 하려면를 [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) 64 비트 부호 없는 정수로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac79-115">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="eac79-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eac79-116">Requirements</span></span>

<span data-ttu-id="eac79-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eac79-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="eac79-118">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="eac79-118">**Header:** None</span></span>  
<span data-ttu-id="eac79-119">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="eac79-119">**Library:** None</span></span>  
<span data-ttu-id="eac79-120">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eac79-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="eac79-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eac79-121">See also</span></span>

- [<span data-ttu-id="eac79-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="eac79-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="eac79-123">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eac79-123">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
