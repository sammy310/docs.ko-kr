---
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
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420931"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="d67da-102">IXCLRDataMethodDefinition:: StartEnumInstances 메서드</span><span class="sxs-lookup"><span data-stu-id="d67da-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="d67da-103">지정 된에 대 한 메서드 인스턴스의 열거형 핸들을 제공 `IXCLRDataAppDomain` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d67da-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d67da-104">구문</span><span class="sxs-lookup"><span data-stu-id="d67da-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="d67da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d67da-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="d67da-106">진행 열거를 위한 AppDomain입니다.</span><span class="sxs-lookup"><span data-stu-id="d67da-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="d67da-107">제한이 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="d67da-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="d67da-108">설명</span><span class="sxs-lookup"><span data-stu-id="d67da-108">Remarks</span></span>

<span data-ttu-id="d67da-109">제공 된 메서드는 인터페이스의 일부 `IXCLRDataMethodDefinition` 이며 가상 메서드 테이블의 5 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d67da-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d67da-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d67da-110">Requirements</span></span>

<span data-ttu-id="d67da-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d67da-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d67da-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="d67da-112">**Header:** None</span></span>  
<span data-ttu-id="d67da-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="d67da-113">**Library:** None</span></span>  
<span data-ttu-id="d67da-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d67da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d67da-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d67da-115">See also</span></span>

- [<span data-ttu-id="d67da-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="d67da-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="d67da-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="d67da-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="d67da-118">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d67da-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
