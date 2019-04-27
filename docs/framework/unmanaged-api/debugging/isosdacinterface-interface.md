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
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922150"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="ac871-102">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac871-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="ac871-103">데이터에 액세스할 도우미 메서드를 제공 `SOS`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac871-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="ac871-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ac871-104">Methods</span></span>

| <span data-ttu-id="ac871-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ac871-105">Method</span></span>                                                                                                               | <span data-ttu-id="ac871-106">설명</span><span class="sxs-lookup"><span data-stu-id="ac871-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="ac871-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="ac871-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="ac871-108">지정된 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ac871-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="ac871-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="ac871-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="ac871-110">특정된 네이티브 명령 주소를 포함 하는 메서드를 해당 MethodDesc의 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac871-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="ac871-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="ac871-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="ac871-112">주어진된 주소에 로드 된 모듈에 해당 데이터를 인출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac871-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ac871-113">설명</span><span class="sxs-lookup"><span data-stu-id="ac871-113">Remarks</span></span>

<span data-ttu-id="ac871-114">이 인터페이스는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac871-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ac871-115">그러나 COM 인터페이스에서 파생 되는 것 `IUnknown` GUID를 사용 하 여 `436f00f2-b42a-4b9f-870c-e73db66ae930` 일반적인 COM 메커니즘을 통해 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac871-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac871-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac871-116">Requirements</span></span>

<span data-ttu-id="ac871-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ac871-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ac871-118">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="ac871-118">**Header:** None</span></span>  
<span data-ttu-id="ac871-119">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="ac871-119">**Library:** None</span></span>  
<span data-ttu-id="ac871-120">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ac871-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ac871-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac871-121">See also</span></span>

- [<span data-ttu-id="ac871-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="ac871-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ac871-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac871-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
