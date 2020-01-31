---
title: IXCLRDataMethodInstance 인터페이스
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790417"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="c1eb9-102">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1eb9-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="c1eb9-103">메서드 인스턴스에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eb9-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="c1eb9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c1eb9-104">Methods</span></span>

| <span data-ttu-id="c1eb9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c1eb9-105">Method</span></span>                                                                                                                  | <span data-ttu-id="c1eb9-106">설명</span><span class="sxs-lookup"><span data-stu-id="c1eb9-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="c1eb9-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="c1eb9-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="c1eb9-108">매핑 정보를 처리 하는 IL을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1eb9-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="c1eb9-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="c1eb9-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="c1eb9-110">메서드에 대 한 모든 가능한 진입점의 네이티브 컴파일에 대 한 가장 대표적인 진입점 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1eb9-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c1eb9-111">주의</span><span class="sxs-lookup"><span data-stu-id="c1eb9-111">Remarks</span></span>

<span data-ttu-id="c1eb9-112">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eb9-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c1eb9-113">그러나 일반적인 COM 메커니즘을 통해 가져올 수 있는 GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5`를 사용 하 여 `IUnknown`에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1eb9-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1eb9-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1eb9-114">Requirements</span></span>

<span data-ttu-id="c1eb9-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1eb9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c1eb9-116">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="c1eb9-116">**Header:** None</span></span>  
<span data-ttu-id="c1eb9-117">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="c1eb9-117">**Library:** None</span></span>  
<span data-ttu-id="c1eb9-118">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c1eb9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c1eb9-119">참조</span><span class="sxs-lookup"><span data-stu-id="c1eb9-119">See also</span></span>

- [<span data-ttu-id="c1eb9-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="c1eb9-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="c1eb9-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1eb9-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
