---
description: '자세히 알아보기: IXCLRDataProcess:: EnumModule 메서드'
title: 'IXCLRDataProcess:: EnumModule 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 33b15da6939a0fb78a4eeafcf75e1a2b2f0d0ab1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800684"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="facdc-103">IXCLRDataProcess:: EnumModule 메서드</span><span class="sxs-lookup"><span data-stu-id="facdc-103">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="facdc-104">이 프로세스의 모듈을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="facdc-104">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="facdc-105">구문</span><span class="sxs-lookup"><span data-stu-id="facdc-105">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="facdc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="facdc-106">Parameters</span></span>

`handle`\
<span data-ttu-id="facdc-107">[in, out] 모듈을 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="facdc-107">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="facdc-108">제한이 열거 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="facdc-108">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="facdc-109">설명</span><span class="sxs-lookup"><span data-stu-id="facdc-109">Remarks</span></span>

<span data-ttu-id="facdc-110">제공 된 메서드는 인터페이스의 일부 `IXCLRDataProcess` 이며 가상 메서드 테이블의 25 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="facdc-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="facdc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="facdc-111">Requirements</span></span>

<span data-ttu-id="facdc-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="facdc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="facdc-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="facdc-113">**Header:** None</span></span>  
<span data-ttu-id="facdc-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="facdc-114">**Library:** None</span></span>  
<span data-ttu-id="facdc-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="facdc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="facdc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="facdc-116">See also</span></span>

- [<span data-ttu-id="facdc-117">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="facdc-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="facdc-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="facdc-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="facdc-119">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="facdc-119">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="facdc-120">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="facdc-120">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
