---
title: ICorProfilerInfo7 인터페이스
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 0e9f76717aeff27e863245faac241927e7495076
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495491"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="147e4-102">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="147e4-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="147e4-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="147e4-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="147e4-104">새로 정의 된 메타 데이터를 모듈에 적용 하 고 메모리 내 기호 스트림에 대 한 액세스를 제공 하는 메서드를 제공 하는 [ICorProfilerInfo6](icorprofilerinfo6-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="147e4-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="147e4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="147e4-105">Methods</span></span>  
  
|<span data-ttu-id="147e4-106">방법</span><span class="sxs-lookup"><span data-stu-id="147e4-106">Method</span></span>|<span data-ttu-id="147e4-107">설명</span><span class="sxs-lookup"><span data-stu-id="147e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="147e4-108">ApplyMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="147e4-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="147e4-109">메서드에 의해 새로 정의 된 메타 데이터를 `IMetadataEmit::Define*` 지정 된 모듈에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="147e4-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="147e4-110">GetInMemorySymbolsLength 메서드</span><span class="sxs-lookup"><span data-stu-id="147e4-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="147e4-111">메모리 내 기호 스트림의 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="147e4-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="147e4-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="147e4-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="147e4-113">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="147e4-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="147e4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="147e4-114">Requirements</span></span>  
 <span data-ttu-id="147e4-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="147e4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="147e4-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="147e4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="147e4-117">**.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="147e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="147e4-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="147e4-118">See also</span></span>

- [<span data-ttu-id="147e4-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="147e4-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
