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
ms.openlocfilehash: 3b7050e92af6fc58b45837840b2796a5deac955c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375339"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="6033d-102">IXCLRDataProcess::EndEnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="6033d-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="6033d-103">모듈 열거 하는 동안 사용 되는 내부 반복기 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6033d-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6033d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6033d-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="6033d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6033d-105">Parameters</span></span>

`handle`\
<span data-ttu-id="6033d-106">[out] 모듈을 열거 하는 것에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6033d-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="6033d-107">설명</span><span class="sxs-lookup"><span data-stu-id="6033d-107">Remarks</span></span>

<span data-ttu-id="6033d-108">제공 된 메서드는의 일부는 `IXCLRDataProcess` 인터페이스 및 가상 메서드 테이블의 26 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6033d-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6033d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6033d-109">Requirements</span></span>

<span data-ttu-id="6033d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6033d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="6033d-111">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="6033d-111">**Header:** None</span></span>   
<span data-ttu-id="6033d-112">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="6033d-112">**Library:** None</span></span>   
<span data-ttu-id="6033d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6033d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="6033d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6033d-114">See also</span></span>

- [<span data-ttu-id="6033d-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="6033d-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="6033d-116">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6033d-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
