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
ms.openlocfilehash: 727005437289b4bc66ab90f280b80a79f4db06db
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359317"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="bfe24-102">IXCLRDataModule::GetMethodDefinitionByToken 메서드</span><span class="sxs-lookup"><span data-stu-id="bfe24-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="bfe24-103">지정 된 메타 데이터 토큰에 해당 하는 메서드 정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfe24-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bfe24-104">구문</span><span class="sxs-lookup"><span data-stu-id="bfe24-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="bfe24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bfe24-105">Parameters</span></span>

`token`\
<span data-ttu-id="bfe24-106">[in] 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe24-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="bfe24-107">[out] 메서드 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe24-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="bfe24-108">설명</span><span class="sxs-lookup"><span data-stu-id="bfe24-108">Remarks</span></span>

<span data-ttu-id="bfe24-109">제공 된 메서드는의 일부는 `IXCLRDataModule` 인터페이스 및 가상 메서드 테이블의 25 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe24-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bfe24-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfe24-110">Requirements</span></span>

<span data-ttu-id="bfe24-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfe24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bfe24-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="bfe24-112">**Header:** None</span></span>  
<span data-ttu-id="bfe24-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="bfe24-113">**Library:** None</span></span>  
<span data-ttu-id="bfe24-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bfe24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="bfe24-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bfe24-115">See also</span></span>

- [<span data-ttu-id="bfe24-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="bfe24-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="bfe24-117">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfe24-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
