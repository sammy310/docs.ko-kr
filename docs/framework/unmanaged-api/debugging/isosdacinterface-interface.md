---
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
ms.openlocfilehash: 94349a3f7b18c8ce29bb3a71cb9d10ee4eac8036
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790475"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="da2cd-102">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da2cd-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="da2cd-103">`SOS`의 데이터에 액세스 하는 도우미 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cd-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="da2cd-104">메서드</span><span class="sxs-lookup"><span data-stu-id="da2cd-104">Methods</span></span>

| <span data-ttu-id="da2cd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="da2cd-105">Method</span></span>                                                                                                               | <span data-ttu-id="da2cd-106">설명</span><span class="sxs-lookup"><span data-stu-id="da2cd-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="da2cd-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="da2cd-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="da2cd-108">지정 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="da2cd-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="da2cd-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="da2cd-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="da2cd-110">지정 된 기본 명령 주소를 포함 하는 메서드에 해당 하는 MethodDesc의 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cd-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="da2cd-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="da2cd-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="da2cd-112">지정 된 주소에서 로드 된 모듈에 해당 하는 데이터를 인출 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cd-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="da2cd-113">주의</span><span class="sxs-lookup"><span data-stu-id="da2cd-113">Remarks</span></span>

<span data-ttu-id="da2cd-114">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da2cd-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="da2cd-115">그러나 일반적인 COM 메커니즘을 통해 가져올 수 있는 GUID `436f00f2-b42a-4b9f-870c-e73db66ae930`를 사용 하 여 `IUnknown`에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="da2cd-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="da2cd-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da2cd-116">Requirements</span></span>

<span data-ttu-id="da2cd-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da2cd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="da2cd-118">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="da2cd-118">**Header:** None</span></span>  
<span data-ttu-id="da2cd-119">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="da2cd-119">**Library:** None</span></span>  
<span data-ttu-id="da2cd-120">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da2cd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="da2cd-121">참조</span><span class="sxs-lookup"><span data-stu-id="da2cd-121">See also</span></span>

- [<span data-ttu-id="da2cd-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="da2cd-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="da2cd-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da2cd-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
