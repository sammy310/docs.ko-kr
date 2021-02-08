---
description: '자세히 알아보기: IXCLRDataMethodInstance:: GetRepresentativeEntryAddress 메서드'
title: 'IXCLRDataMethodInstance:: GetRepresentativeEntryAddress 메서드'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 21cc6c50ab460c0e3a3a92c11fcfe51d4a2a4606
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800801"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="34e5c-103">IXCLRDataMethodInstance:: GetRepresentativeEntryAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="34e5c-103">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="34e5c-104">메서드에 대 한 모든 가능한 진입점의 네이티브 컴파일에 대 한 가장 대표적인 진입점 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34e5c-104">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="34e5c-105">구문</span><span class="sxs-lookup"><span data-stu-id="34e5c-105">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="34e5c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34e5c-106">Parameters</span></span>

`addr`\
<span data-ttu-id="34e5c-107">제한이 메서드에 대 한 가장 대표적인 기본 진입점의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="34e5c-107">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="34e5c-108">설명</span><span class="sxs-lookup"><span data-stu-id="34e5c-108">Remarks</span></span>

<span data-ttu-id="34e5c-109">제공 된 메서드는 [ `IXCLRDataMethodInstance` 인터페이스](ixclrdatamethodinstance-interface.md) 의 일부 이며 가상 메서드 테이블의 20 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="34e5c-109">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="34e5c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34e5c-110">Requirements</span></span>

<span data-ttu-id="34e5c-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34e5c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="34e5c-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="34e5c-112">**Header:** None</span></span>  
<span data-ttu-id="34e5c-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="34e5c-113">**Library:** None</span></span>  
<span data-ttu-id="34e5c-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34e5c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="34e5c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34e5c-115">See also</span></span>

- [<span data-ttu-id="34e5c-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="34e5c-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="34e5c-117">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34e5c-117">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
