---
description: '자세히 알아보기: IXCLRDataModule:: GetMethodDefinitionByToken 메서드'
title: 'IXCLRDataModule:: GetMethodDefinitionByToken 메서드'
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
ms.openlocfilehash: 1eb1187d09183bfff97324a8032d23cbf471f580
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800775"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="e674a-103">IXCLRDataModule:: GetMethodDefinitionByToken 메서드</span><span class="sxs-lookup"><span data-stu-id="e674a-103">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="e674a-104">지정 된 메타 데이터 토큰에 해당 하는 메서드 정의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e674a-104">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e674a-105">구문</span><span class="sxs-lookup"><span data-stu-id="e674a-105">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="e674a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e674a-106">Parameters</span></span>

`token`\
<span data-ttu-id="e674a-107">진행 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e674a-107">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="e674a-108">제한이 메서드 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="e674a-108">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="e674a-109">설명</span><span class="sxs-lookup"><span data-stu-id="e674a-109">Remarks</span></span>

<span data-ttu-id="e674a-110">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataModule` 가상 메서드 테이블의 26 일 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e674a-110">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e674a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e674a-111">Requirements</span></span>

<span data-ttu-id="e674a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e674a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e674a-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="e674a-113">**Header:** None</span></span>  
<span data-ttu-id="e674a-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="e674a-114">**Library:** None</span></span>  
<span data-ttu-id="e674a-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e674a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e674a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e674a-116">See also</span></span>

- [<span data-ttu-id="e674a-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="e674a-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="e674a-118">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e674a-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
