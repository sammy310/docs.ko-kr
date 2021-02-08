---
description: '자세히 알아보기: IXCLRDataMethodDefinition:: EndEnumInstances 메서드'
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
ms.openlocfilehash: bfdcb9046b4983e6686410bf2ceadf7119b89e74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790375"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="61920-103">IXCLRDataMethodDefinition:: EndEnumInstances 메서드</span><span class="sxs-lookup"><span data-stu-id="61920-103">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="61920-104">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="61920-104">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="61920-105">구문</span><span class="sxs-lookup"><span data-stu-id="61920-105">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="61920-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61920-106">Parameters</span></span>

`handle`\
<span data-ttu-id="61920-107">제한이 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="61920-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="61920-108">설명</span><span class="sxs-lookup"><span data-stu-id="61920-108">Remarks</span></span>

<span data-ttu-id="61920-109">제공 된 메서드는 인터페이스의 일부 `IXCLRDataMethodDefinition` 이며 가상 메서드 테이블의 일곱 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="61920-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="61920-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61920-110">Requirements</span></span>

<span data-ttu-id="61920-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61920-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="61920-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="61920-112">**Header:** None</span></span>  
<span data-ttu-id="61920-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="61920-113">**Library:** None</span></span>  
<span data-ttu-id="61920-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="61920-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="61920-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61920-115">See also</span></span>

- [<span data-ttu-id="61920-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="61920-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="61920-117">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61920-117">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
