---
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
ms.openlocfilehash: 5caadcfe091393a8ff79106d57a50a532c349829
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420779"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="d05bc-102">IXCLRDataProcess:: EnumModule 메서드</span><span class="sxs-lookup"><span data-stu-id="d05bc-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="d05bc-103">이 프로세스의 모듈을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05bc-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d05bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="d05bc-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="d05bc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d05bc-105">Parameters</span></span>

`handle`\
<span data-ttu-id="d05bc-106">[in, out] 모듈을 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="d05bc-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="d05bc-107">제한이 열거 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="d05bc-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="d05bc-108">설명</span><span class="sxs-lookup"><span data-stu-id="d05bc-108">Remarks</span></span>

<span data-ttu-id="d05bc-109">제공 된 메서드는 인터페이스의 일부 `IXCLRDataProcess` 이며 가상 메서드 테이블의 25 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05bc-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d05bc-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d05bc-110">Requirements</span></span>

<span data-ttu-id="d05bc-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d05bc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d05bc-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="d05bc-112">**Header:** None</span></span>  
<span data-ttu-id="d05bc-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="d05bc-113">**Library:** None</span></span>  
<span data-ttu-id="d05bc-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d05bc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d05bc-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d05bc-115">See also</span></span>

- [<span data-ttu-id="d05bc-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="d05bc-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="d05bc-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="d05bc-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="d05bc-118">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d05bc-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="d05bc-119">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d05bc-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
