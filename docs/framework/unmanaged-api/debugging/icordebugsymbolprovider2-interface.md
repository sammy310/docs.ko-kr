---
title: ICorDebugSymbolProvider2 인터페이스
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b787302902779695c48df6e02e2ee00b28f44cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142469"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="93d37-102">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93d37-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="93d37-103">논리적으로 확장 합니다 [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) 추가 디버그 기호 정보를 검색 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="93d37-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93d37-104">메서드</span><span class="sxs-lookup"><span data-stu-id="93d37-104">Methods</span></span>  
  
|<span data-ttu-id="93d37-105">메서드</span><span class="sxs-lookup"><span data-stu-id="93d37-105">Method</span></span>|<span data-ttu-id="93d37-106">설명</span><span class="sxs-lookup"><span data-stu-id="93d37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93d37-107">GetFrameProps 메서드</span><span class="sxs-lookup"><span data-stu-id="93d37-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="93d37-108">메서드의 메서드 시작 상대 가상 주소 및 코드 상대 가상 주소가 지정된 부모 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="93d37-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="93d37-109">GetGenericDictionaryInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="93d37-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="93d37-110">제네릭 사전 맵을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="93d37-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93d37-111">설명</span><span class="sxs-lookup"><span data-stu-id="93d37-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93d37-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d37-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="93d37-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="93d37-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93d37-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93d37-114">Requirements</span></span>  
 <span data-ttu-id="93d37-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="93d37-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93d37-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93d37-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93d37-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93d37-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93d37-118">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93d37-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d37-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="93d37-119">See also</span></span>

- [<span data-ttu-id="93d37-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93d37-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="93d37-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93d37-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="93d37-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="93d37-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
