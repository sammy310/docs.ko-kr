---
title: IXCLRDataProcess 인터페이스
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420762"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="19960-102">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19960-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="19960-103">프로세스에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19960-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="19960-104">메서드</span><span class="sxs-lookup"><span data-stu-id="19960-104">Methods</span></span>

| <span data-ttu-id="19960-105">메서드</span><span class="sxs-lookup"><span data-stu-id="19960-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="19960-106">설명</span><span class="sxs-lookup"><span data-stu-id="19960-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="19960-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="19960-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="19960-108">`AppDomain`프로세스의 고유 id로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19960-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="19960-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="19960-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="19960-110">프로세스의 모듈을 열거 하는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19960-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="19960-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="19960-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="19960-112">이 프로세스의 모듈을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="19960-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="19960-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="19960-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="19960-114">모듈 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="19960-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="19960-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="19960-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="19960-116">지정 된 주소에서 시작 하는의 메서드 인스턴스를 열거 하는 핸들을 제공 합니다 `AppDomain` .</span><span class="sxs-lookup"><span data-stu-id="19960-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="19960-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="19960-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="19960-118">주소 오프셋에서 시작 하 여이 프로세스의 메서드 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="19960-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="19960-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="19960-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="19960-120">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="19960-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="19960-121">설명</span><span class="sxs-lookup"><span data-stu-id="19960-121">Remarks</span></span>

<span data-ttu-id="19960-122">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19960-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="19960-123">그러나 `IUnknown` `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="19960-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="19960-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19960-124">Requirements</span></span>

<span data-ttu-id="19960-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19960-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="19960-126">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="19960-126">**Header:** None</span></span>  
<span data-ttu-id="19960-127">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="19960-127">**Library:** None</span></span>  
<span data-ttu-id="19960-128">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="19960-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="19960-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19960-129">See also</span></span>

- [<span data-ttu-id="19960-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="19960-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="19960-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19960-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
