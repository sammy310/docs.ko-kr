---
title: IXCLRDataProcess::StartEnumModules 메서드
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 79c4e0ed99a068d7d806d5c25580dc477aac6475
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752634"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="6412a-102">IXCLRDataProcess::StartEnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="6412a-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="6412a-103">프로세스의 모듈을 열거에 대 한 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6412a-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6412a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6412a-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="6412a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6412a-105">Parameters</span></span>

`handle`\
<span data-ttu-id="6412a-106">[out] 모듈을 열거 하는 것에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6412a-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="6412a-107">설명</span><span class="sxs-lookup"><span data-stu-id="6412a-107">Remarks</span></span>

<span data-ttu-id="6412a-108">제공 된 메서드는의 일부는 `IXCLRDataProcess` 인터페이스 및 가상 메서드 테이블의 24 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6412a-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6412a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6412a-109">Requirements</span></span>

<span data-ttu-id="6412a-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6412a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6412a-111">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="6412a-111">**Header:** None</span></span>  
<span data-ttu-id="6412a-112">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="6412a-112">**Library:** None</span></span>  
<span data-ttu-id="6412a-113">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6412a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6412a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6412a-114">See also</span></span>

- [<span data-ttu-id="6412a-115">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="6412a-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6412a-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="6412a-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="6412a-117">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6412a-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
