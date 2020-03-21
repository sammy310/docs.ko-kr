---
title: IXCLR데이터 모듈::GetMethod정의토큰 방법
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
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176671"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="21776-102">IXCLR데이터 모듈::GetMethod정의토큰 방법</span><span class="sxs-lookup"><span data-stu-id="21776-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="21776-103">지정된 메타데이터 토큰에 해당하는 메서드 정의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21776-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="21776-104">구문</span><span class="sxs-lookup"><span data-stu-id="21776-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="21776-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21776-105">Parameters</span></span>

`token`\
<span data-ttu-id="21776-106">【인】 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="21776-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="21776-107">【아웃】 메서드 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="21776-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="21776-108">설명</span><span class="sxs-lookup"><span data-stu-id="21776-108">Remarks</span></span>

<span data-ttu-id="21776-109">제공된 메서드는 `IXCLRDataModule` 인터페이스의 일부이며 가상 메서드 테이블의 25번째 슬롯에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="21776-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="21776-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21776-110">Requirements</span></span>

<span data-ttu-id="21776-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21776-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="21776-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="21776-112">**Header:** None</span></span>  
<span data-ttu-id="21776-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="21776-113">**Library:** None</span></span>  
<span data-ttu-id="21776-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="21776-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="21776-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21776-115">See also</span></span>

- [<span data-ttu-id="21776-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="21776-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="21776-117">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21776-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
