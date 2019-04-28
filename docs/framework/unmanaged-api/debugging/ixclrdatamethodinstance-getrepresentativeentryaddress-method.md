---
title: IXCLRDataMethodInstance::GetRepresentativeEntryAddress 메서드
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
ms.openlocfilehash: 6f204e2ed9cb1409d53432355467bb11946f8809
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775534"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="1215c-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="1215c-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="1215c-103">모든 가능한 진입점 메서드에 대 한 네이티브 컴파일에 대 한 가장 대표적인 진입점 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1215c-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1215c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1215c-104">Syntax</span></span>

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="1215c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1215c-105">Parameters</span></span>

`addr`\
<span data-ttu-id="1215c-106">[out] 가장 대표적인 네이티브 진입점의 메서드에 대 한 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1215c-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="1215c-107">설명</span><span class="sxs-lookup"><span data-stu-id="1215c-107">Remarks</span></span>

<span data-ttu-id="1215c-108">제공 된 메서드는의 일부를 [ `IXCLRDataMethodInstance` 인터페이스](ixclrdatamethodinstance-interface.md) 가상 메서드 테이블의 19 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1215c-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1215c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1215c-109">Requirements</span></span>

<span data-ttu-id="1215c-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1215c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1215c-111">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="1215c-111">**Header:** None</span></span>  
<span data-ttu-id="1215c-112">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="1215c-112">**Library:** None</span></span>  
<span data-ttu-id="1215c-113">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1215c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1215c-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="1215c-114">See also</span></span>

- [<span data-ttu-id="1215c-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="1215c-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="1215c-116">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1215c-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
