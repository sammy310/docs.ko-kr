---
title: IXCLRDataMethodDefinition::StartEnumInstances 메서드
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
ms.openlocfilehash: 89473f2a6a3da73ee5d172a3700bdb4d624278ff
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756288"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="e5fc5-102">IXCLRDataMethodDefinition::StartEnumInstances 메서드</span><span class="sxs-lookup"><span data-stu-id="e5fc5-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="e5fc5-103">에 대 한 메서드 인스턴스의 열거형에 대 한 핸들을 제공 된 지정 `IXCLRDataAppDomain`합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fc5-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e5fc5-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5fc5-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="e5fc5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5fc5-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="e5fc5-106">[in] 열거형에 대 한 AppDomain 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fc5-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="e5fc5-107">[out] 인스턴스를 열거 하는 것에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="e5fc5-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5fc5-108">설명</span><span class="sxs-lookup"><span data-stu-id="e5fc5-108">Remarks</span></span>

<span data-ttu-id="e5fc5-109">제공 된 메서드는의 일부는 `IXCLRDataMethodDefinition` 인터페이스 및 가상 메서드 테이블의 세 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fc5-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e5fc5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fc5-110">Requirements</span></span>

<span data-ttu-id="e5fc5-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5fc5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e5fc5-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="e5fc5-112">**Header:** None</span></span>  
<span data-ttu-id="e5fc5-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="e5fc5-113">**Library:** None</span></span>  
<span data-ttu-id="e5fc5-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e5fc5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e5fc5-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="e5fc5-115">See also</span></span>

- [<span data-ttu-id="e5fc5-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="e5fc5-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="e5fc5-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="e5fc5-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="e5fc5-118">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5fc5-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
