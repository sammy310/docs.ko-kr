---
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
ms.openlocfilehash: d546cda5c68732e75550a3de286089f7df261c91
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420905"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="31206-102">IXCLRDataMethodInstance:: GetRepresentativeEntryAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="31206-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="31206-103">메서드에 대 한 모든 가능한 진입점의 네이티브 컴파일에 대 한 가장 대표적인 진입점 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31206-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="31206-104">구문</span><span class="sxs-lookup"><span data-stu-id="31206-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="31206-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="31206-105">Parameters</span></span>

`addr`\
<span data-ttu-id="31206-106">제한이 메서드에 대 한 가장 대표적인 기본 진입점의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="31206-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="31206-107">설명</span><span class="sxs-lookup"><span data-stu-id="31206-107">Remarks</span></span>

<span data-ttu-id="31206-108">제공 된 메서드는 [ `IXCLRDataMethodInstance` 인터페이스](ixclrdatamethodinstance-interface.md) 의 일부 이며 가상 메서드 테이블의 20 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="31206-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="31206-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31206-109">Requirements</span></span>

<span data-ttu-id="31206-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31206-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="31206-111">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="31206-111">**Header:** None</span></span>  
<span data-ttu-id="31206-112">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="31206-112">**Library:** None</span></span>  
<span data-ttu-id="31206-113">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="31206-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="31206-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31206-114">See also</span></span>

- [<span data-ttu-id="31206-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="31206-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="31206-116">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31206-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
