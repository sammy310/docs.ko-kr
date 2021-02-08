---
description: '자세히 알아보기: IXCLRDataProcess 인터페이스'
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
ms.openlocfilehash: b611491e5c9a5957c07a305a3f395b67ad208649
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800645"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="1bd69-103">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1bd69-103">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="1bd69-104">프로세스에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-104">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="1bd69-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1bd69-105">Methods</span></span>

| <span data-ttu-id="1bd69-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1bd69-106">Method</span></span>                                                                                                                                               | <span data-ttu-id="1bd69-107">설명</span><span class="sxs-lookup"><span data-stu-id="1bd69-107">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="1bd69-108">GetRuntimeNameByAddress</span><span class="sxs-lookup"><span data-stu-id="1bd69-108">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="1bd69-109">지정 된 주소에 대 한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-109">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="1bd69-110">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="1bd69-110">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="1bd69-111">`AppDomain`프로세스의 고유 id로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-111">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="1bd69-112">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="1bd69-112">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="1bd69-113">프로세스의 모듈을 열거 하는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-113">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="1bd69-114">EnumModule</span><span class="sxs-lookup"><span data-stu-id="1bd69-114">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="1bd69-115">이 프로세스의 모듈을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-115">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="1bd69-116">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="1bd69-116">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="1bd69-117">모듈 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-117">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="1bd69-118">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="1bd69-118">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="1bd69-119">지정 된 주소에서 시작 하는의 메서드 인스턴스를 열거 하는 핸들을 제공 합니다 `AppDomain` .</span><span class="sxs-lookup"><span data-stu-id="1bd69-119">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="1bd69-120">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="1bd69-120">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="1bd69-121">주소 오프셋에서 시작 하 여이 프로세스의 메서드 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-121">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="1bd69-122">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="1bd69-122">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="1bd69-123">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-123">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="1bd69-124">설명</span><span class="sxs-lookup"><span data-stu-id="1bd69-124">Remarks</span></span>

<span data-ttu-id="1bd69-125">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-125">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1bd69-126">그러나 `IUnknown` `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-126">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bd69-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1bd69-127">Requirements</span></span>

<span data-ttu-id="1bd69-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bd69-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="1bd69-129">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="1bd69-129">**Header:** None</span></span>  
<span data-ttu-id="1bd69-130">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="1bd69-130">**Library:** None</span></span>  
<span data-ttu-id="1bd69-131">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd69-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1bd69-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bd69-132">See also</span></span>

- [<span data-ttu-id="1bd69-133">디버깅</span><span class="sxs-lookup"><span data-stu-id="1bd69-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="1bd69-134">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1bd69-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
