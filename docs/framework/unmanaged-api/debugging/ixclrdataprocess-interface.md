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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178366"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="3df0c-102">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3df0c-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="3df0c-103">프로세스에 대한 정보를 쿼리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="3df0c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3df0c-104">Methods</span></span>

| <span data-ttu-id="3df0c-105">방법</span><span class="sxs-lookup"><span data-stu-id="3df0c-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="3df0c-106">Description</span><span class="sxs-lookup"><span data-stu-id="3df0c-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="3df0c-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="3df0c-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="3df0c-108">고유 `AppDomain` ID로 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="3df0c-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="3df0c-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="3df0c-110">프로세스모듈을 등록하는 핸들을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="3df0c-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="3df0c-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="3df0c-112">이 프로세스의 모듈을 개과시합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="3df0c-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="3df0c-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="3df0c-114">모듈 열거 중에 사용되는 내부 거처에서 사용하는 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="3df0c-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="3df0c-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="3df0c-116">지정된 주소에서 `AppDomain` 시작하는 메서드 인스턴스를 등록하는 핸들을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="3df0c-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="3df0c-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="3df0c-118">주소 오프셋에서 시작하는 이 프로세스의 메서드 인스턴스를 모두보대해서는</span><span class="sxs-lookup"><span data-stu-id="3df0c-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="3df0c-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="3df0c-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="3df0c-120">인스턴스 열거 중에 사용되는 내부 거처에서 사용하는 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="3df0c-121">설명</span><span class="sxs-lookup"><span data-stu-id="3df0c-121">Remarks</span></span>

<span data-ttu-id="3df0c-122">이 인터페이스는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3df0c-123">그러나 일반적인 COM 메커니즘을 통해 얻을 `IUnknown` 수 `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 있는 GUID를 사용하여 파생되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="3df0c-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3df0c-124">Requirements</span></span>

<span data-ttu-id="3df0c-125">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3df0c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="3df0c-126">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="3df0c-126">**Header:** None</span></span>  
<span data-ttu-id="3df0c-127">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="3df0c-127">**Library:** None</span></span>  
<span data-ttu-id="3df0c-128">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3df0c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3df0c-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3df0c-129">See also</span></span>

- [<span data-ttu-id="3df0c-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="3df0c-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="3df0c-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3df0c-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
