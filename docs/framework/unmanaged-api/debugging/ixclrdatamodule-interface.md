---
description: '자세히 알아보기: IXCLRDataModule 인터페이스'
title: IXCLRDataModule 인터페이스
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 403d4dd3db64f2855347562da7217a3562985c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800749"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="a586b-103">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a586b-103">IXCLRDataModule Interface</span></span>

<span data-ttu-id="a586b-104">로드 된 모듈에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a586b-104">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="a586b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a586b-105">Methods</span></span>

| <span data-ttu-id="a586b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a586b-106">Method</span></span>                                                                                                                                | <span data-ttu-id="a586b-107">설명</span><span class="sxs-lookup"><span data-stu-id="a586b-107">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="a586b-108">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="a586b-108">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="a586b-109">지정 된 메타 데이터 토큰에 해당 하는 메서드 정의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a586b-109">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="a586b-110">요청</span><span class="sxs-lookup"><span data-stu-id="a586b-110">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="a586b-111">모듈의 데이터에 지정 된 버퍼를 채우도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a586b-111">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="a586b-112">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="a586b-112">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="a586b-113">모듈의 버전 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a586b-113">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="a586b-114">설명</span><span class="sxs-lookup"><span data-stu-id="a586b-114">Remarks</span></span>

<span data-ttu-id="a586b-115">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a586b-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a586b-116">그러나 `IUnknown` `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a586b-116">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a586b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a586b-117">Requirements</span></span>

<span data-ttu-id="a586b-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a586b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a586b-119">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="a586b-119">**Header:** None</span></span>  
<span data-ttu-id="a586b-120">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="a586b-120">**Library:** None</span></span>  
<span data-ttu-id="a586b-121">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a586b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a586b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a586b-122">See also</span></span>

- [<span data-ttu-id="a586b-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="a586b-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="a586b-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a586b-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
