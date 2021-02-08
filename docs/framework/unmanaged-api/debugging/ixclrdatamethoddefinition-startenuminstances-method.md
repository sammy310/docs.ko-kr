---
description: '자세히 알아보기: IXCLRDataMethodDefinition:: StartEnumInstances 메서드'
title: 'IXCLRDataMethodDefinition:: StartEnumInstances 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 74de6360c90766cfec17e6b88a495fe2a70858b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800827"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="3c886-103">IXCLRDataMethodDefinition:: StartEnumInstances 메서드</span><span class="sxs-lookup"><span data-stu-id="3c886-103">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="3c886-104">지정 된에 대 한 메서드 인스턴스의 열거형 핸들을 제공 `IXCLRDataAppDomain` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c886-104">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3c886-105">구문</span><span class="sxs-lookup"><span data-stu-id="3c886-105">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="3c886-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c886-106">Parameters</span></span>

`appDomain`\
<span data-ttu-id="3c886-107">진행 열거를 위한 AppDomain입니다.</span><span class="sxs-lookup"><span data-stu-id="3c886-107">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="3c886-108">제한이 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="3c886-108">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c886-109">설명</span><span class="sxs-lookup"><span data-stu-id="3c886-109">Remarks</span></span>

<span data-ttu-id="3c886-110">제공 된 메서드는 인터페이스의 일부 `IXCLRDataMethodDefinition` 이며 가상 메서드 테이블의 5 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c886-110">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c886-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c886-111">Requirements</span></span>

<span data-ttu-id="3c886-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c886-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3c886-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="3c886-113">**Header:** None</span></span>  
<span data-ttu-id="3c886-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="3c886-114">**Library:** None</span></span>  
<span data-ttu-id="3c886-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3c886-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3c886-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c886-116">See also</span></span>

- [<span data-ttu-id="3c886-117">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="3c886-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3c886-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="3c886-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="3c886-119">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c886-119">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
