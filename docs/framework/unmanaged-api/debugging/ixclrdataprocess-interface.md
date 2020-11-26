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
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245356"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="418d6-102">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="418d6-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="418d6-103">프로세스에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="418d6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="418d6-104">Methods</span></span>

| <span data-ttu-id="418d6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="418d6-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="418d6-106">Description</span><span class="sxs-lookup"><span data-stu-id="418d6-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="418d6-107">GetRuntimeNameByAddress</span><span class="sxs-lookup"><span data-stu-id="418d6-107">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="418d6-108">지정 된 주소에 대 한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-108">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="418d6-109">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="418d6-109">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="418d6-110">`AppDomain`프로세스의 고유 id로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-110">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="418d6-111">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="418d6-111">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="418d6-112">프로세스의 모듈을 열거 하는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-112">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="418d6-113">EnumModule</span><span class="sxs-lookup"><span data-stu-id="418d6-113">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="418d6-114">이 프로세스의 모듈을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-114">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="418d6-115">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="418d6-115">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="418d6-116">모듈 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-116">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="418d6-117">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="418d6-117">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="418d6-118">지정 된 주소에서 시작 하는의 메서드 인스턴스를 열거 하는 핸들을 제공 합니다 `AppDomain` .</span><span class="sxs-lookup"><span data-stu-id="418d6-118">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="418d6-119">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="418d6-119">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="418d6-120">주소 오프셋에서 시작 하 여이 프로세스의 메서드 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-120">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="418d6-121">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="418d6-121">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="418d6-122">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-122">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="418d6-123">설명</span><span class="sxs-lookup"><span data-stu-id="418d6-123">Remarks</span></span>

<span data-ttu-id="418d6-124">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-124">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="418d6-125">그러나 `IUnknown` `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="418d6-125">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="418d6-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="418d6-126">Requirements</span></span>

<span data-ttu-id="418d6-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418d6-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="418d6-128">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="418d6-128">**Header:** None</span></span>  
<span data-ttu-id="418d6-129">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="418d6-129">**Library:** None</span></span>  
<span data-ttu-id="418d6-130">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="418d6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="418d6-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="418d6-131">See also</span></span>

- [<span data-ttu-id="418d6-132">디버깅</span><span class="sxs-lookup"><span data-stu-id="418d6-132">Debugging</span></span>](index.md)
- [<span data-ttu-id="418d6-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="418d6-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
