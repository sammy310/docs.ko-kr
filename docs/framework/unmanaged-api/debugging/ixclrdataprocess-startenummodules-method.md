---
description: '자세히 알아보기: IXCLRDataProcess:: StartEnumModules 메서드'
title: 'IXCLRDataProcess:: StartEnumModules 메서드'
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
ms.openlocfilehash: 2e90c646ee8815ec10ce0bbd7538f13d7b5dcf8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800584"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="841c5-103">IXCLRDataProcess:: StartEnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="841c5-103">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="841c5-104">프로세스의 모듈을 열거 하는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="841c5-104">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="841c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="841c5-105">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="841c5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="841c5-106">Parameters</span></span>

`handle`\
<span data-ttu-id="841c5-107">제한이 모듈을 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="841c5-107">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="841c5-108">설명</span><span class="sxs-lookup"><span data-stu-id="841c5-108">Remarks</span></span>

<span data-ttu-id="841c5-109">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataProcess` 가상 메서드 테이블의 24 일 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="841c5-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="841c5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="841c5-110">Requirements</span></span>

<span data-ttu-id="841c5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="841c5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="841c5-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="841c5-112">**Header:** None</span></span>  
<span data-ttu-id="841c5-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="841c5-113">**Library:** None</span></span>  
<span data-ttu-id="841c5-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="841c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="841c5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="841c5-115">See also</span></span>

- [<span data-ttu-id="841c5-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="841c5-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="841c5-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="841c5-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="841c5-118">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="841c5-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
