---
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
ms.openlocfilehash: ae1ef2a3c8cf9e042ab9ab233ed993f8e36b2fce
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420944"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="9f403-102">IXCLRDataMethodDefinition:: EnumInstance 메서드</span><span class="sxs-lookup"><span data-stu-id="9f403-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="9f403-103">이 메서드 정의의 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f403-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9f403-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f403-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="9f403-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9f403-105">Parameters</span></span>

`handle`\
<span data-ttu-id="9f403-106">[in, out] 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="9f403-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="9f403-107">제한이 열거 된 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f403-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f403-108">설명</span><span class="sxs-lookup"><span data-stu-id="9f403-108">Remarks</span></span>

<span data-ttu-id="9f403-109">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataMethodDefinition` 가상 메서드 테이블의 6 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f403-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9f403-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f403-110">Requirements</span></span>

<span data-ttu-id="9f403-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f403-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9f403-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="9f403-112">**Header:** None</span></span>  
<span data-ttu-id="9f403-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="9f403-113">**Library:** None</span></span>  
<span data-ttu-id="9f403-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9f403-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9f403-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f403-115">See also</span></span>

- [<span data-ttu-id="9f403-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="9f403-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9f403-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="9f403-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="9f403-118">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f403-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="9f403-119">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f403-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
