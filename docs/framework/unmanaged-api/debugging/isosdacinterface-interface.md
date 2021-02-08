---
description: '자세히 알아보기: ISOSDacInterface 인터페이스'
title: ISOSDacInterface 인터페이스
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ddb99b7c6fca6870024f04933861d01e4b31ea9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790401"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="89e4f-103">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89e4f-103">ISOSDacInterface Interface</span></span>

<span data-ttu-id="89e4f-104">에서 데이터에 액세스 하는 도우미 메서드를 제공 `SOS` 합니다.</span><span class="sxs-lookup"><span data-stu-id="89e4f-104">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="89e4f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="89e4f-105">Methods</span></span>

| <span data-ttu-id="89e4f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="89e4f-106">Method</span></span>                                                                                                               | <span data-ttu-id="89e4f-107">설명</span><span class="sxs-lookup"><span data-stu-id="89e4f-107">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="89e4f-108">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="89e4f-108">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="89e4f-109">지정 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89e4f-109">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="89e4f-110">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="89e4f-110">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="89e4f-111">지정 된 기본 명령 주소를 포함 하는 메서드에 해당 하는 MethodDesc의 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="89e4f-111">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="89e4f-112">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="89e4f-112">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="89e4f-113">지정 된 주소에서 로드 된 모듈에 해당 하는 데이터를 인출 합니다.</span><span class="sxs-lookup"><span data-stu-id="89e4f-113">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="89e4f-114">설명</span><span class="sxs-lookup"><span data-stu-id="89e4f-114">Remarks</span></span>

<span data-ttu-id="89e4f-115">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89e4f-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="89e4f-116">그러나 `IUnknown` `436f00f2-b42a-4b9f-870c-e73db66ae930` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="89e4f-116">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="89e4f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89e4f-117">Requirements</span></span>

<span data-ttu-id="89e4f-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89e4f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="89e4f-119">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="89e4f-119">**Header:** None</span></span>  
<span data-ttu-id="89e4f-120">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="89e4f-120">**Library:** None</span></span>  
<span data-ttu-id="89e4f-121">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="89e4f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="89e4f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89e4f-122">See also</span></span>

- [<span data-ttu-id="89e4f-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="89e4f-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="89e4f-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89e4f-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
