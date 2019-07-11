---
title: IXCLRDataProcess::EnumModule 메서드
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
ms.openlocfilehash: 40ab90a3218d4309cda709004a191e9440fe505d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769580"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="c430e-102">IXCLRDataProcess::EnumModule 메서드</span><span class="sxs-lookup"><span data-stu-id="c430e-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="c430e-103">이 프로세스의 모듈을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c430e-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c430e-104">구문</span><span class="sxs-lookup"><span data-stu-id="c430e-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="c430e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c430e-105">Parameters</span></span>

`handle`\
<span data-ttu-id="c430e-106">[out에서] 모듈을 열거 하는 것에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="c430e-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="c430e-107">[out] 열거 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="c430e-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="c430e-108">설명</span><span class="sxs-lookup"><span data-stu-id="c430e-108">Remarks</span></span>

<span data-ttu-id="c430e-109">제공 된 메서드는의 일부는 `IXCLRDataProcess` 인터페이스 및 가상 메서드 테이블의 25 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c430e-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c430e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c430e-110">Requirements</span></span>

<span data-ttu-id="c430e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c430e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c430e-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="c430e-112">**Header:** None</span></span>  
<span data-ttu-id="c430e-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="c430e-113">**Library:** None</span></span>  
<span data-ttu-id="c430e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c430e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c430e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="c430e-115">See also</span></span>

- [<span data-ttu-id="c430e-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="c430e-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="c430e-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="c430e-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="c430e-118">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c430e-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="c430e-119">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c430e-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
