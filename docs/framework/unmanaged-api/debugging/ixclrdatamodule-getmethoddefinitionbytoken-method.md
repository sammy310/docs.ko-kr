---
title: IXCLRDataModule::GetMethodDefinitionByToken 메서드
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 2c0cf56f108396226b7c7399f6da75e5f47d36f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744677"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="bf512-102">IXCLRDataModule::GetMethodDefinitionByToken 메서드</span><span class="sxs-lookup"><span data-stu-id="bf512-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="bf512-103">지정 된 메타 데이터 토큰에 해당 하는 메서드 정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bf512-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bf512-104">구문</span><span class="sxs-lookup"><span data-stu-id="bf512-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="bf512-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf512-105">Parameters</span></span>

`token`\
<span data-ttu-id="bf512-106">[in] 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bf512-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="bf512-107">[out] 메서드 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="bf512-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf512-108">설명</span><span class="sxs-lookup"><span data-stu-id="bf512-108">Remarks</span></span>

<span data-ttu-id="bf512-109">제공 된 메서드는의 일부는 `IXCLRDataModule` 인터페이스 및 가상 메서드 테이블의 25 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf512-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf512-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf512-110">Requirements</span></span>

<span data-ttu-id="bf512-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf512-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bf512-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="bf512-112">**Header:** None</span></span>  
<span data-ttu-id="bf512-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="bf512-113">**Library:** None</span></span>  
<span data-ttu-id="bf512-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf512-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="bf512-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bf512-115">See also</span></span>

- [<span data-ttu-id="bf512-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="bf512-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="bf512-117">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf512-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
