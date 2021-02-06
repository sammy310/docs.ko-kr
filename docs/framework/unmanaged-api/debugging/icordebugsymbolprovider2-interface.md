---
description: '자세히 알아보기: ICorDebugSymbolProvider2 인터페이스'
title: ICorDebugSymbolProvider2 인터페이스
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: b4eaeb29c15da979a522fb20e33a56030889d0c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659519"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="6e49d-103">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e49d-103">ICorDebugSymbolProvider2 Interface</span></span>

<span data-ttu-id="6e49d-104">[ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 인터페이스를 논리적으로 확장 하 여 추가 디버그 기호 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e49d-104">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e49d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6e49d-105">Methods</span></span>  
  
|<span data-ttu-id="6e49d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6e49d-106">Method</span></span>|<span data-ttu-id="6e49d-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e49d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e49d-108">GetFrameProps 메서드</span><span class="sxs-lookup"><span data-stu-id="6e49d-108">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="6e49d-109">메서드의 메서드 시작 상대 가상 주소 및 코드 상대 가상 주소가 지정된 부모 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6e49d-109">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="6e49d-110">GetGenericDictionaryInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="6e49d-110">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="6e49d-111">제네릭 사전 맵을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6e49d-111">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e49d-112">설명</span><span class="sxs-lookup"><span data-stu-id="6e49d-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e49d-113">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e49d-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6e49d-114">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6e49d-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e49d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e49d-115">Requirements</span></span>  

 <span data-ttu-id="6e49d-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e49d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e49d-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e49d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e49d-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e49d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e49d-119">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e49d-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e49d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e49d-120">See also</span></span>

- [<span data-ttu-id="6e49d-121">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e49d-121">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6e49d-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e49d-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6e49d-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="6e49d-123">Debugging</span></span>](index.md)
