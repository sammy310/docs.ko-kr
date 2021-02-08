---
description: 'IXCLRDataMethodDefinition:: EnumInstance 메서드에 대해 자세히 알아보세요.'
title: 'IXCLRDataMethodDefinition:: EnumInstance 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4038dc4706b8362acaf9c13abd9c7326cce376a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790362"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="25c04-103">IXCLRDataMethodDefinition:: EnumInstance 메서드</span><span class="sxs-lookup"><span data-stu-id="25c04-103">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="25c04-104">이 메서드 정의의 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c04-104">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="25c04-105">구문</span><span class="sxs-lookup"><span data-stu-id="25c04-105">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="25c04-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25c04-106">Parameters</span></span>

`handle`\
<span data-ttu-id="25c04-107">[in, out] 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="25c04-107">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="25c04-108">제한이 열거 된 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="25c04-108">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="25c04-109">설명</span><span class="sxs-lookup"><span data-stu-id="25c04-109">Remarks</span></span>

<span data-ttu-id="25c04-110">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataMethodDefinition` 가상 메서드 테이블의 6 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c04-110">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="25c04-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25c04-111">Requirements</span></span>

<span data-ttu-id="25c04-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25c04-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="25c04-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="25c04-113">**Header:** None</span></span>  
<span data-ttu-id="25c04-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="25c04-114">**Library:** None</span></span>  
<span data-ttu-id="25c04-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="25c04-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="25c04-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25c04-116">See also</span></span>

- [<span data-ttu-id="25c04-117">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="25c04-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="25c04-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="25c04-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="25c04-119">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25c04-119">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="25c04-120">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25c04-120">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
