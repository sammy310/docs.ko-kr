---
title: ISOSDacInterface::GetMethodDescData 메서드
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
ms.openlocfilehash: 4e32facc65162c4deb853cd507a00126e5f786e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352596"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="456ad-102">ISOSDacInterface::GetMethodDescData 메서드</span><span class="sxs-lookup"><span data-stu-id="456ad-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="456ad-103">지정된 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="456ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="456ad-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="456ad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="456ad-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="456ad-106">[in] 주소는 MethodDesc입니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="456ad-107">[in] 메서드의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="456ad-108">[out] 내부 Api에서 반환 되는 MethodDesc와 연결 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="456ad-109">[out] 되돌린된 rejit 버전 수입니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="456ad-110">[out] 내부 Api에서 반환 된 되돌린된 rejit 버전과 연결 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="456ad-111">[out] 되돌린된 ReJit 버전과 연결 된 데이터를 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="456ad-112">설명</span><span class="sxs-lookup"><span data-stu-id="456ad-112">Remarks</span></span>

<span data-ttu-id="456ad-113">제공 된 메서드는의 일부는 `ISOSDacInterface` 인터페이스 및 가상 메서드 테이블의 20 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="456ad-114">사용할 수 있으려면 [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) 64 비트 부호 없는 정수로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="456ad-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="456ad-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="456ad-115">Requirements</span></span>

<span data-ttu-id="456ad-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="456ad-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="456ad-117">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="456ad-117">**Header:** None</span></span>  
<span data-ttu-id="456ad-118">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="456ad-118">**Library:** None</span></span>  
<span data-ttu-id="456ad-119">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="456ad-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="456ad-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="456ad-120">See also</span></span>

- [<span data-ttu-id="456ad-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="456ad-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="456ad-122">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="456ad-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)