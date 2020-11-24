---
title: ICorDebugSymbolProvider2 인터페이스
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: 3bef03e9e85224058bc17e1f0ce8746e98aa30f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688343"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="91859-102">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91859-102">ICorDebugSymbolProvider2 Interface</span></span>

<span data-ttu-id="91859-103">[ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 인터페이스를 논리적으로 확장 하 여 추가 디버그 기호 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="91859-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91859-104">메서드</span><span class="sxs-lookup"><span data-stu-id="91859-104">Methods</span></span>  
  
|<span data-ttu-id="91859-105">메서드</span><span class="sxs-lookup"><span data-stu-id="91859-105">Method</span></span>|<span data-ttu-id="91859-106">설명</span><span class="sxs-lookup"><span data-stu-id="91859-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91859-107">GetFrameProps 메서드</span><span class="sxs-lookup"><span data-stu-id="91859-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="91859-108">메서드의 메서드 시작 상대 가상 주소 및 코드 상대 가상 주소가 지정된 부모 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91859-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="91859-109">GetGenericDictionaryInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="91859-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="91859-110">제네릭 사전 맵을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="91859-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91859-111">설명</span><span class="sxs-lookup"><span data-stu-id="91859-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91859-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91859-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="91859-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="91859-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91859-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91859-114">Requirements</span></span>  

 <span data-ttu-id="91859-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91859-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91859-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91859-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91859-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91859-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91859-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91859-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91859-119">참조</span><span class="sxs-lookup"><span data-stu-id="91859-119">See also</span></span>

- [<span data-ttu-id="91859-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91859-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="91859-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91859-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="91859-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="91859-122">Debugging</span></span>](index.md)
