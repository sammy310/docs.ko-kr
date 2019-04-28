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
ms.openlocfilehash: f62cbdc4b3e73f0c27492f7ed20b35378654d399
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775506"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="09c15-102">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09c15-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="09c15-103">메서드 인스턴스에 대 한 정보를 쿼리 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c15-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="09c15-104">메서드</span><span class="sxs-lookup"><span data-stu-id="09c15-104">Methods</span></span>

| <span data-ttu-id="09c15-105">메서드</span><span class="sxs-lookup"><span data-stu-id="09c15-105">Method</span></span>                                                                                                                  | <span data-ttu-id="09c15-106">설명</span><span class="sxs-lookup"><span data-stu-id="09c15-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="09c15-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="09c15-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="09c15-108">IL을 주소 매핑 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09c15-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="09c15-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="09c15-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="09c15-110">모든 가능한 진입점 메서드에 대 한 네이티브 컴파일에 대 한 가장 대표적인 진입점 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09c15-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="09c15-111">설명</span><span class="sxs-lookup"><span data-stu-id="09c15-111">Remarks</span></span>

<span data-ttu-id="09c15-112">이 인터페이스는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09c15-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="09c15-113">그러나 COM 인터페이스에서 파생 되는 것 `IUnknown` GUID를 사용 하 여 `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` 일반적인 COM 메커니즘을 통해 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c15-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="09c15-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09c15-114">Requirements</span></span>

<span data-ttu-id="09c15-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09c15-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="09c15-116">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="09c15-116">**Header:** None</span></span>  
<span data-ttu-id="09c15-117">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="09c15-117">**Library:** None</span></span>  
<span data-ttu-id="09c15-118">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="09c15-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="09c15-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="09c15-119">See also</span></span>

- [<span data-ttu-id="09c15-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="09c15-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="09c15-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09c15-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
