---
title: 'IXCLRDataProcess:: EndEnumModules 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9a7a23e53f5c2bc7d643046830cf335fec780f11
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420840"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="04610-102">IXCLRDataProcess:: EndEnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="04610-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="04610-103">모듈 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="04610-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="04610-104">구문</span><span class="sxs-lookup"><span data-stu-id="04610-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="04610-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04610-105">Parameters</span></span>

`handle`\
<span data-ttu-id="04610-106">제한이 모듈을 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="04610-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="04610-107">설명</span><span class="sxs-lookup"><span data-stu-id="04610-107">Remarks</span></span>

<span data-ttu-id="04610-108">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataProcess` 가상 메서드 테이블의 26 일 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="04610-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="04610-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04610-109">Requirements</span></span>

<span data-ttu-id="04610-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04610-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="04610-111">**헤더:** None **라이브러리:** 없음 **.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04610-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="04610-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04610-112">See also</span></span>

- [<span data-ttu-id="04610-113">디버깅</span><span class="sxs-lookup"><span data-stu-id="04610-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="04610-114">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04610-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
