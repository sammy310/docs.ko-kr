---
title: IXCLRDataProcess::EndEnumModules 메서드
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
ms.openlocfilehash: de30384b4c12c4fcac3eafe580484685f8a43fa4
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611434"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="b9f04-102">IXCLRDataProcess::EndEnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="b9f04-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="b9f04-103">모듈 열거 하는 동안 사용 되는 내부 반복기 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f04-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b9f04-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9f04-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="b9f04-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9f04-105">Parameters</span></span>

`handle`\
<span data-ttu-id="b9f04-106">[out] 모듈을 열거 하는 것에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="b9f04-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9f04-107">설명</span><span class="sxs-lookup"><span data-stu-id="b9f04-107">Remarks</span></span>

<span data-ttu-id="b9f04-108">제공 된 메서드는의 일부는 `IXCLRDataProcess` 인터페이스 및 가상 메서드 테이블의 26 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f04-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9f04-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9f04-109">Requirements</span></span>

<span data-ttu-id="b9f04-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9f04-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="b9f04-111">**헤더:** None **라이브러리:** None **.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f04-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b9f04-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="b9f04-112">See also</span></span>

- [<span data-ttu-id="b9f04-113">디버깅</span><span class="sxs-lookup"><span data-stu-id="b9f04-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="b9f04-114">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9f04-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
