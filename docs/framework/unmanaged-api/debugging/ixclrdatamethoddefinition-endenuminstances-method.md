---
title: IXCLRDataMethodDefinition::EndEnumInstances 메서드
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
ms.openlocfilehash: 3d9e3ca31eddff9d08607c4d6d37ca76139bf5d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756313"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="ea892-102">IXCLRDataMethodDefinition::EndEnumInstances 메서드</span><span class="sxs-lookup"><span data-stu-id="ea892-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="ea892-103">인스턴스 열거 하는 동안 사용 되는 내부 반복기 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea892-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ea892-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea892-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="ea892-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea892-105">Parameters</span></span>

`handle`\
<span data-ttu-id="ea892-106">[out] 인스턴스를 열거 하는 것에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="ea892-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea892-107">설명</span><span class="sxs-lookup"><span data-stu-id="ea892-107">Remarks</span></span>

<span data-ttu-id="ea892-108">제공 된 메서드는의 일부는 `IXCLRDataMethodDefinition` 인터페이스 및 가상 메서드 테이블의 다섯 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea892-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea892-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea892-109">Requirements</span></span>

<span data-ttu-id="ea892-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea892-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ea892-111">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="ea892-111">**Header:** None</span></span>  
<span data-ttu-id="ea892-112">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="ea892-112">**Library:** None</span></span>  
<span data-ttu-id="ea892-113">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea892-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ea892-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea892-114">See also</span></span>

- [<span data-ttu-id="ea892-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="ea892-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ea892-116">IXCLRDataMethodDefinition 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea892-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
