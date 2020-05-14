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
ms.openlocfilehash: 84e0ad392c5fee8377115427482d80543454fff3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397200"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="42ce2-102">IXCLRDataMethodDefinition:: StartEnumInstances 메서드</span><span class="sxs-lookup"><span data-stu-id="42ce2-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="42ce2-103">지정 된에 대 한 메서드 인스턴스의 열거형 핸들을 제공 `IXCLRDataAppDomain` 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ce2-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="42ce2-104">구문</span><span class="sxs-lookup"><span data-stu-id="42ce2-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="42ce2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42ce2-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="42ce2-106">진행 열거를 위한 AppDomain입니다.</span><span class="sxs-lookup"><span data-stu-id="42ce2-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="42ce2-107">제한이 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="42ce2-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="42ce2-108">설명</span><span class="sxs-lookup"><span data-stu-id="42ce2-108">Remarks</span></span>

<span data-ttu-id="42ce2-109">제공 된 메서드는 인터페이스의 일부 `IXCLRDataMethodDefinition` 이며 가상 메서드 테이블의 5 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ce2-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="42ce2-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42ce2-110">Requirements</span></span>

<span data-ttu-id="42ce2-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42ce2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="42ce2-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="42ce2-112">**Header:** None</span></span>  
<span data-ttu-id="42ce2-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="42ce2-113">**Library:** None</span></span>  
<span data-ttu-id="42ce2-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42ce2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="42ce2-115">참조</span><span class="sxs-lookup"><span data-stu-id="42ce2-115">See also</span></span>

- [<span data-ttu-id="42ce2-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="42ce2-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="42ce2-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="42ce2-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="42ce2-118">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42ce2-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
