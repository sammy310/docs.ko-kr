---
description: '자세히 알아보기: IXCLRDataProcess:: EndEnumModules 메서드'
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
ms.openlocfilehash: 454d4fa3616f9ba8312dc3d1ac02c228625aa488
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800710"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="9947f-103">IXCLRDataProcess:: EndEnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="9947f-103">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="9947f-104">모듈 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9947f-104">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9947f-105">구문</span><span class="sxs-lookup"><span data-stu-id="9947f-105">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="9947f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9947f-106">Parameters</span></span>

`handle`\
<span data-ttu-id="9947f-107">제한이 모듈을 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="9947f-107">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="9947f-108">설명</span><span class="sxs-lookup"><span data-stu-id="9947f-108">Remarks</span></span>

<span data-ttu-id="9947f-109">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataProcess` 가상 메서드 테이블의 26 일 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9947f-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9947f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9947f-110">Requirements</span></span>

<span data-ttu-id="9947f-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9947f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="9947f-112">**헤더:** None **라이브러리:** 없음 **.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9947f-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9947f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9947f-113">See also</span></span>

- [<span data-ttu-id="9947f-114">디버깅</span><span class="sxs-lookup"><span data-stu-id="9947f-114">Debugging</span></span>](index.md)
- [<span data-ttu-id="9947f-115">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9947f-115">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
