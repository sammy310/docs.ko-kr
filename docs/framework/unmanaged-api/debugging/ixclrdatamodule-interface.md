---
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
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790401"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="6c37d-102">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c37d-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="6c37d-103">로드 된 모듈에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c37d-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="6c37d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6c37d-104">Methods</span></span>

| <span data-ttu-id="6c37d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6c37d-105">Method</span></span>                                                                                                                                | <span data-ttu-id="6c37d-106">설명</span><span class="sxs-lookup"><span data-stu-id="6c37d-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6c37d-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="6c37d-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="6c37d-108">지정 된 메타 데이터 토큰에 해당 하는 메서드 정의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c37d-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="6c37d-109">요청</span><span class="sxs-lookup"><span data-stu-id="6c37d-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="6c37d-110">모듈의 데이터에 지정 된 버퍼를 채우도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c37d-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="6c37d-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="6c37d-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="6c37d-112">모듈의 버전 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c37d-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="6c37d-113">주의</span><span class="sxs-lookup"><span data-stu-id="6c37d-113">Remarks</span></span>

<span data-ttu-id="6c37d-114">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c37d-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6c37d-115">그러나 일반적인 COM 메커니즘을 통해 가져올 수 있는 GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2`를 사용 하 여 `IUnknown`에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6c37d-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c37d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c37d-116">Requirements</span></span>

<span data-ttu-id="6c37d-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c37d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6c37d-118">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="6c37d-118">**Header:** None</span></span>  
<span data-ttu-id="6c37d-119">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="6c37d-119">**Library:** None</span></span>  
<span data-ttu-id="6c37d-120">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c37d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c37d-121">참조</span><span class="sxs-lookup"><span data-stu-id="6c37d-121">See also</span></span>

- [<span data-ttu-id="6c37d-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="6c37d-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="6c37d-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c37d-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
