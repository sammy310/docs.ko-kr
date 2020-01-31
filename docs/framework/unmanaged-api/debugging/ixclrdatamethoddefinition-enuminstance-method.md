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
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790437"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="b8e0b-102">IXCLRDataMethodDefinition:: EnumInstance 메서드</span><span class="sxs-lookup"><span data-stu-id="b8e0b-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="b8e0b-103">이 메서드 정의의 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e0b-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b8e0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8e0b-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="b8e0b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8e0b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="b8e0b-106">[in, out] 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e0b-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="b8e0b-107">제한이 열거 된 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e0b-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8e0b-108">주의</span><span class="sxs-lookup"><span data-stu-id="b8e0b-108">Remarks</span></span>

<span data-ttu-id="b8e0b-109">제공 된 메서드는 `IXCLRDataMethodDefinition` 인터페이스의 일부 이며 가상 메서드 테이블의 네 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e0b-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8e0b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8e0b-110">Requirements</span></span>

<span data-ttu-id="b8e0b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e0b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b8e0b-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b8e0b-112">**Header:** None</span></span>  
<span data-ttu-id="b8e0b-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b8e0b-113">**Library:** None</span></span>  
<span data-ttu-id="b8e0b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e0b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b8e0b-115">참조</span><span class="sxs-lookup"><span data-stu-id="b8e0b-115">See also</span></span>

- [<span data-ttu-id="b8e0b-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="b8e0b-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b8e0b-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="b8e0b-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="b8e0b-118">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8e0b-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="b8e0b-119">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8e0b-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
