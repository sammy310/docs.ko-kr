---
title: 'IXCLRDataProcess:: GetAppDomainByUniqueId 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: bb02ffed09cbcc31e653bfd3165050c247908c5d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420788"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="2a3a2-102">IXCLRDataProcess:: GetAppDomainByUniqueId 메서드</span><span class="sxs-lookup"><span data-stu-id="2a3a2-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="2a3a2-103">`AppDomain`프로세스의 고유 식별자를 기반으로 하는를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a3a2-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2a3a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a3a2-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="2a3a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a3a2-105">Parameters</span></span>

`id`\
<span data-ttu-id="2a3a2-106">진행 AppDomain의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2a3a2-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="2a3a2-107">제한이 AppDomain</span><span class="sxs-lookup"><span data-stu-id="2a3a2-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="2a3a2-108">설명</span><span class="sxs-lookup"><span data-stu-id="2a3a2-108">Remarks</span></span>

<span data-ttu-id="2a3a2-109">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataProcess` 가상 메서드 테이블의 20 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3a2-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="2a3a2-110">반환 된는 `IXCLRDataAppDomain*` 다른 api와의 상호 작용에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a3a2-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a3a2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a3a2-111">Requirements</span></span>

<span data-ttu-id="2a3a2-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a3a2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="2a3a2-113">**헤더:** None **라이브러리:** 없음 **.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3a2-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2a3a2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a3a2-114">See also</span></span>

- [<span data-ttu-id="2a3a2-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="2a3a2-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="2a3a2-116">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3a2-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
