---
title: 'IXCLRDataMethodDefinition:: EndEnumInstances 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7271c9594a679af205c404f59ff6731821aa0acf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420996"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="cb915-102">IXCLRDataMethodDefinition:: EndEnumInstances 메서드</span><span class="sxs-lookup"><span data-stu-id="cb915-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="cb915-103">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb915-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cb915-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb915-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="cb915-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb915-105">Parameters</span></span>

`handle`\
<span data-ttu-id="cb915-106">제한이 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="cb915-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb915-107">설명</span><span class="sxs-lookup"><span data-stu-id="cb915-107">Remarks</span></span>

<span data-ttu-id="cb915-108">제공 된 메서드는 인터페이스의 일부 `IXCLRDataMethodDefinition` 이며 가상 메서드 테이블의 일곱 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb915-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb915-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb915-109">Requirements</span></span>

<span data-ttu-id="cb915-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb915-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cb915-111">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="cb915-111">**Header:** None</span></span>  
<span data-ttu-id="cb915-112">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="cb915-112">**Library:** None</span></span>  
<span data-ttu-id="cb915-113">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cb915-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cb915-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb915-114">See also</span></span>

- [<span data-ttu-id="cb915-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="cb915-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="cb915-116">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb915-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
