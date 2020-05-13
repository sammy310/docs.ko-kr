---
title: ICorDebugSymbolProvider2 인터페이스
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: e6712dca776bf4c20ce7fc8568e94399a81beecb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379294"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="e5fb5-102">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5fb5-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="e5fb5-103">[ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 인터페이스를 논리적으로 확장 하 여 추가 디버그 기호 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fb5-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5fb5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e5fb5-104">Methods</span></span>  
  
|<span data-ttu-id="e5fb5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e5fb5-105">Method</span></span>|<span data-ttu-id="e5fb5-106">설명</span><span class="sxs-lookup"><span data-stu-id="e5fb5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5fb5-107">GetFrameProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e5fb5-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="e5fb5-108">메서드의 메서드 시작 상대 가상 주소 및 코드 상대 가상 주소가 지정된 부모 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fb5-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="e5fb5-109">GetGenericDictionaryInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="e5fb5-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="e5fb5-110">제네릭 사전 맵을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fb5-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5fb5-111">설명</span><span class="sxs-lookup"><span data-stu-id="e5fb5-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5fb5-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fb5-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e5fb5-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fb5-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5fb5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fb5-114">Requirements</span></span>  
 <span data-ttu-id="e5fb5-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5fb5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5fb5-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5fb5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5fb5-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5fb5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5fb5-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5fb5-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fb5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5fb5-119">See also</span></span>

- [<span data-ttu-id="e5fb5-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5fb5-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e5fb5-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5fb5-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e5fb5-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="e5fb5-122">Debugging</span></span>](index.md)
